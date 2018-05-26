---
Description: Explains how to generate, retrieve, verify, and export DSS keys and signatures.
ms.assetid: d28fe531-af4b-4b5e-ab67-47ef70f8fa5b
title: DSS Keys
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# DSS Keys

-   [Generating and Retrieving DSS Keys](#generating-and-retrieving-dss-keys)
-   [Generating DSS Signatures](#generating-dss-signatures)
-   [Verifying a DSS Signature](#verifying-a-dss-signature)
-   [Exporting DSS Keys](#exporting-dss-keys)

## Generating and Retrieving DSS Keys

DSS Keys can be generated by a call to the [**CryptGenKey**](/windows/win32/Wincrypt/nf-wincrypt-cryptgenkey?branch=master) function. The call to **CryptGenKey** requires that either AT\_SIGNATURE or CALG\_DSS\_SIGN be passed in the *Algid* argument. This call will generate the P (prime modulus), Q (prime), G (generator), X (secret exponent), and Y (public key) values from scratch and persist them in a [*key BLOB*](security.k_gly#-security-key-blob-gly) to local storage.

**To generate a DSS signature key pair**

1.  Call the [**CryptAcquireContext**](/windows/win32/Wincrypt/nf-wincrypt-cryptacquirecontexta?branch=master) function to get a handle to the Microsoft DSS Cryptographic Provider.
2.  Call [**CryptGenKey**](/windows/win32/Wincrypt/nf-wincrypt-cryptgenkey?branch=master) to generate the keys. Either AT\_SIGNATURE or CALG\_DSS\_SIGN must be passed in for the *Algid* argument and the upper 16 bits of the *dwFlags* argument must be set to the desired key size. If the upper 16 bits are zero, then the default key size of 1,024 bits will be used. A [**HCRYPTKEY**](hcryptkey.md) handle is returned in the *hKey* argument.

**To retrieve a pointer to previously generated signature keys**

1.  Call [**CryptAcquireContext**](/windows/win32/Wincrypt/nf-wincrypt-cryptacquirecontexta?branch=master) to get a handle to the Microsoft DSS Cryptographic Provider.
2.  Call the [**CryptGetUserKey**](/windows/win32/Wincrypt/nf-wincrypt-cryptgetuserkey?branch=master) function with the *dwKeySpec* argument set to either AT\_SIGNATURE or CALG\_DSS\_SIGN.

**To retrieve the P, Q, and G values**

1.  Call [**CryptAcquireContext**](/windows/win32/Wincrypt/nf-wincrypt-cryptacquirecontexta?branch=master) to get a handle to the Microsoft DSS Cryptographic Provider.
2.  Call [**CryptGetUserKey**](/windows/win32/Wincrypt/nf-wincrypt-cryptgetuserkey?branch=master) with the *dwKeySpec* argument set to either AT\_SIGNATURE or CALG\_DSS\_SIGN.
3.  Call [**CryptGetKeyParam**](/windows/win32/Wincrypt/nf-wincrypt-cryptgetkeyparam?branch=master) with the *hKey* argument set to the pointer retrieved in the previous step. The *dwParam* argument must be set to the desired flag; KP\_P, KP\_Q, or KP\_G. The value is returned in the *pbData* argument, and the length of the data is returned in the *pdwDataLen* argument. The value is returned with no header information and in [*little-endian*](security.l_gly#-security-little-endian-gly) format.

## Generating DSS Signatures

Data to be signed must first be [*hashed*](security.h_gly#-security-hash-gly) by using the [*SHA*](security.s_gly#-security-secure-hash-algorithm-gly) algorithm. After that data is hashed, a [*DSS*](security.d_gly#-security-digital-signature-standard-gly) signature is generated by calling the [**CryptSignHash**](/windows/win32/Wincrypt/nf-wincrypt-cryptsignhasha?branch=master) function.

**To generate a DSS signature**

1.  Call [**CryptAcquireContext**](/windows/win32/Wincrypt/nf-wincrypt-cryptacquirecontexta?branch=master) to get a handle to the Microsoft DSS Cryptographic Provider.
2.  Call [**CryptCreateHash**](/windows/win32/Wincrypt/nf-wincrypt-cryptcreatehash?branch=master) with the *Algid* argument set to CALG\_SHA to get a handle to a SHA hash object.
3.  Call [**CryptHashData**](/windows/win32/Wincrypt/nf-wincrypt-crypthashdata?branch=master) with the *hHash* argument set to the handle retrieved in the previous step. This creates a hash of the data and returns a handle to the hash in the *phHash* argument of the [**CryptCreateHash**](/windows/win32/Wincrypt/nf-wincrypt-cryptcreatehash?branch=master) function call.
4.  Call [**CryptSignHash**](/windows/win32/Wincrypt/nf-wincrypt-cryptsignhasha?branch=master) with the *hHash* argument set to the handle retrieved in the previous step. Either AT\_SIGNATURE or CALG\_DSS\_SIGN may be passed in the *dwKeySpec* parameter. The signature is returned to the address provided in the *pbSignature* argument, and the length of the signature is returned to the address provided in the *pdwSigLen* argument. A **NULL** pointer may be passed in the *pbSignature* argument, and, in this case, the signature is not generated, but the length of the signature is returned to the address provided in the *pdwSigLen* parameter.

## Verifying a DSS Signature

To verify a DSS signature, the DSS public key of the signer must be imported, the [*signed data*](security.s_gly#-security-signed-data-gly) must be hashed, and then the signature can be verified.

**To verify a DSS signature**

1.  Call [**CryptAcquireContext**](/windows/win32/Wincrypt/nf-wincrypt-cryptacquirecontexta?branch=master) to get a handle to the Microsoft DSS Cryptographic Provider.
2.  Call [**CryptImportKey**](/windows/win32/Wincrypt/nf-wincrypt-cryptimportkey?branch=master) to import the signer's DSS public key.
3.  Call [**CryptCreateHash**](/windows/win32/Wincrypt/nf-wincrypt-cryptcreatehash?branch=master) with the *Algid* argument set to CALG\_SHA to get a handle to a SHA hash object.
4.  Call [**CryptHashData**](/windows/win32/Wincrypt/nf-wincrypt-crypthashdata?branch=master) with the *hHash* argument set to the handle retrieved in the previous step and with *pbData* pointing to the signed data. This creates a hash of the data and returns a handle to the hash in the *phHash* argument of the [**CryptCreateHash**](/windows/win32/Wincrypt/nf-wincrypt-cryptcreatehash?branch=master) function call.
5.  Call [**CryptVerifySignature**](/windows/win32/Wincrypt/nf-wincrypt-cryptverifysignaturea?branch=master) with the following settings:

    *hHash* is set to the handle to the hash performed in the previous step.

    *pbSignature* points to the signature to be verified.

    *dwSigLen* is set to the length of the signature.

    *hPubKey* is set to the handle of the public key imported in step 2.

    *dwFlags* is set to zero.

## Exporting DSS Keys

When you send [*signed data*](security.s_gly#-security-signed-data-gly) to someone where the signature will need to be verified by the recipient, the signer's public key must be provided to the recipient and is usually sent along with the signed data. Therefore, it is necessary to be able to export the [*DSS*](security.d_gly#-security-digital-signature-standard-gly) keys in a [*key BLOB*](security.k_gly#-security-key-blob-gly) format.

**To export the DSS public key**

1.  Call [**CryptAcquireContext**](/windows/win32/Wincrypt/nf-wincrypt-cryptacquirecontexta?branch=master) to get a handle to the Microsoft DSS Cryptographic Provider.
2.  Call [**CryptGetUserKey**](/windows/win32/Wincrypt/nf-wincrypt-cryptgetuserkey?branch=master) with the *dwKeySpec* argument set to either AT\_SIGNATURE or CALG\_DSS\_SIGN.
3.  Call [**CryptExportKey**](/windows/win32/Wincrypt/nf-wincrypt-cryptexportkey?branch=master) with *hKey* set to the handle retrieved in the previous step, *dwBlobType* set to PUBLICKEYBLOB, and *dwFlags* set to zero. The DSS [*public key BLOB*](security.p_gly#-security-public-key-blob-gly) is returned in *pbData*, and the length of the [*key BLOB*](security.k_gly#-security-key-blob-gly) is returned in *pdwDataLen*. A **NULL** pointer may be passed in *pbData*, and, in this case, just the length of the DSS key BLOB will be returned. The BLOB returned when making the call to **CryptExportKey** is in the format described in [DSS Provider Key BLOBs](dss-provider-key-blobs.md).

**To export the DSS private key**

-   Follow the same procedure as for exporting a DSS public key, except that when making the call to [**CryptExportKey**](/windows/win32/Wincrypt/nf-wincrypt-cryptexportkey?branch=master), *dwBlobType* is set to PRIVATEKEYBLOB. The BLOB returned when making the call to **CryptExportKey** is in the format described in [DSS Provider Key BLOBs](dss-provider-key-blobs.md).

 

 


