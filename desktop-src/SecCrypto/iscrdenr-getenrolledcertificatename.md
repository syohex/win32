---
Description: Retrieves the name of the certificate resulting from an earlier successful call to ISCrdEnrenroll.
ms.assetid: e33b217a-b717-49bd-b0f3-3ba9229a0696
title: ISCrdEnrgetEnrolledCertificateName method
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# ISCrdEnr::getEnrolledCertificateName method

The **getEnrolledCertificateName** method retrieves the name of the certificate resulting from an earlier successful call to [**ISCrdEnr::enroll**](/windows/win32/certenroll/?branch=master).

This method can also be used to display the certificate in a dialog box. This method calls the [*CryptoAPI*](security.c_gly#-security-cryptoapi-gly) function [**CertGetNameString**](/windows/win32/Wincrypt/nf-wincrypt-certgetnamestringa?branch=master).

## Syntax


```C++
HRESULT getEnrolledCertificateName(
  [in]  DWORD     dwFlags,
  [out] BSTR *pBstrCertName
);
```

<span codelanguage="VisualBasic"></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th>VB</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><pre><code>SCrdEnr.getEnrolledCertificateName( _
  ByVal dwFlags, _
  ByRef pBstrCertName _
)</code></pre></td>
</tr>
</tbody>
</table>



## Parameters

<dl> <dt>

*dwFlags* \[in\]
</dt> <dd>

A value that determines whether the certificate is displayed in a dialog box. If this value is SCARD\_ENROLL\_NO\_DISPLAY\_CERT (defined as 0x01), the enrolled certificate is not displayed; any other values cause the enrolled certificate to be displayed in the **Certificate** dialog box.

</dd> <dt>

*pBstrCertName* \[out\]
</dt> <dd>

A pointer to a string that returns the retrieved certificate name.

</dd> </dl>

## Return value

### C++

If the method succeeds, the method returns S\_OK.

If the method fails, it returns an **HRESULT** value that indicates the error. For a list of common error codes, see [Common HRESULT Values](common-hresult-values.md).

### VB

A string that represents the retrieved certificate name.

## Remarks

Because this method operates on an existing certificate, you must have successfully called [**IScrdEnr::enroll**](/windows/win32/certenroll/?branch=master) before you can call **getEnrolledCertificateName**.

The **getEnrolledCertificateName** method calls the [**CertGetNameString**](/windows/win32/Wincrypt/nf-wincrypt-certgetnamestringa?branch=master) function to retrieve the certificate name according to the sequence described for the CERT\_NAME\_SIMPLE\_DISPLAY\_TYPE value of **CertGetNameString**'s *dwType* parameter.

## Requirements



|                                     |                                                                                         |
|-------------------------------------|-----------------------------------------------------------------------------------------|
| Minimum supported client<br/> | None supported<br/>                                                               |
| Minimum supported server<br/> | Windows Server 2003 \[desktop apps only\]<br/>                                    |
| DLL<br/>                      | <dl> <dt>Scrdenrl.dll</dt> </dl> |
| IID<br/>                      | IID\_ISCrdEnr is defined as 753988a1-1357-436d-9cf5-f089bdd67d64<br/>             |



## See also

<dl> <dt>

[**ISCrdEnr**](iscrdenr.md)
</dt> <dt>

[**ISCrdEnr::enroll**](/windows/win32/certenroll/?branch=master)
</dt> </dl>

 

 



