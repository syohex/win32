---
Description: Schannel uses CryptoAPI for cryptographic operations such as storing public/private keys.
ms.assetid: 5ad9a171-5f69-4035-aac5-ae8d27d0abfb
title: Schannel and CryptoAPI
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Schannel and CryptoAPI

Schannel uses [CryptoAPI](security.cryptography_essentials) for cryptographic operations such as storing [*public/private keys*](security.p_gly#-security-public-private-key-pair-gly).

The following topics provide detailed information about how Schannel makes use of CryptoAPI.



| Topic                                                                   | Description                                                                                                          |
|-------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------|
| [Certificate Stores](certificate-stores.md)<br/>                 | Both client and server certificates must be stored in a certificate store.<br/>                                |
| [CryptoAPI 2.0 Private Keys](cryptoapi-2-0-private-keys.md)<br/> | Schannel credentials are represented internally as [**CERT\_CONTEXT**](security.cert_context) structures.<br/> |



 

 

 



