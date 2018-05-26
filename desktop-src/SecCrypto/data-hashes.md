---
Description: A hash of a text or other string of bytes is an associated, statistically unique, fixed-length value.
ms.assetid: e54d5a3b-cae1-47dd-a565-7bf1ccef7f52
title: Data Hashes
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Data Hashes

A [*hash*](security.h_gly#-security-hash-gly) of a text or other string of bytes is an associated, statistically unique, fixed-length value. In some documents, a *hash* of a text is also called a digest; however, in this documentation the term hash will always be used. CryptoAPI functions provide a means to create a hash for any text or other string of bytes. That hash, then, can be used as a unique identifier of its associated data.

To ensure the [*integrity*](security.i_gly#-security-integrity-gly) of a text, a [*hash*](security.h_gly#-security-hash-gly) of a text can be sent to accompany the text. The receiver can then compute a hash on the data received and compare the hash computed with the hash received. If the two match, the data received must be the same as the data from which the received hash was created.

To obtain a hash value, create a hash object using [**CryptCreateHash**](/windows/win32/Wincrypt/nf-wincrypt-cryptcreatehash?branch=master). This object will accumulate the data to be verified. The data is then added to the hash object with the [**CryptHashData**](/windows/win32/Wincrypt/nf-wincrypt-crypthashdata?branch=master) function.

After the last block of data is added to the hash, the [**CryptGetHashParam**](/windows/win32/Wincrypt/nf-wincrypt-cryptgethashparam?branch=master) function is used to obtain the hash value of the data.

Better security is provided by destroying the hash object with [**CryptDestroyHash**](/windows/win32/Wincrypt/nf-wincrypt-cryptdestroyhash?branch=master) as soon as the hash value has been obtained.

 

 


