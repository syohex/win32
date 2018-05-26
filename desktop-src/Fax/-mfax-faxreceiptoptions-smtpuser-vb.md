---
Description: The SMTPUser property is a null-terminated string that contains the Simple Mail Transport Protocol (SMTP) user name used for authenticated connections.
ms.assetid: 4b08801f-7ac6-4a03-90e3-f9330d4e0a57
title: FaxReceiptOptions.SMTPUser property
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# FaxReceiptOptions.SMTPUser property

The **SMTPUser** property is a null-terminated string that contains the Simple Mail Transport Protocol (SMTP) user name used for authenticated connections.

This property is read/write.

## Syntax


```VB
Property SMTPUser As String
```



## Property value

A **String** that specifies or receives the SMTP user name used for authenticated connections. The string is null-terminated.

## Remarks

To read or to write to this property, a user must have the [****farQUERY\_CONFIG****](/windows/previous-versions/FaxComex/ne-faxcomex-fax_access_rights_enum?branch=master) access right.

## Requirements



|                                     |                                                                                         |
|-------------------------------------|-----------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows XP \[desktop apps only\]<br/>                                             |
| Minimum supported server<br/> | Windows Server 2003 \[desktop apps only\]<br/>                                    |
| Header<br/>                   | <dl> <dt>FaxComex.h</dt> </dl>   |
| DLL<br/>                      | <dl> <dt>Fxscomex.dll</dt> </dl> |



## See also

<dl> <dt>

[**FaxReceiptOptions**](-mfax-faxreceiptoptions.md)
</dt> <dt>

[**IFaxReceiptOptions**](/windows/previous-versions/FaxComex/nn-faxcomex-ifaxreceiptoptions?branch=master)
</dt> </dl>

 

 



