---
title: IMimeBody GetDisplayName method
description: Gets the display name for the body. If a display name is set, MimeOLE generates a display name based on the content of the body.
ms.assetid: 3a476099-1881-4bb4-982c-dd70d26f673d
keywords:
- GetDisplayName method Windows Mail (formerly Outlook Express)
- GetDisplayName method Windows Mail (formerly Outlook Express) , IMimeBody interface
- IMimeBody interface Windows Mail (formerly Outlook Express) , GetDisplayName method
topic_type:
- apiref
api_name:
- IMimeBody.GetDisplayName
api_location:
- Inetcomm.dll
api_type:
- COM
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# IMimeBody::GetDisplayName method

Gets the display name for the body. If a display name is set, MimeOLE generates a display name based on the content of the body.

## Syntax


```C++
HRESULT GetDisplayName(
  [out] LPSTR *ppszDisplay
);
```



## Parameters

<dl> <dt>

*ppszDisplay* \[out\]
</dt> <dd>

Type: **LPSTR\***

Receives a pointer to a **LPSTR** that contains the display name. The client is responsible for freeing this pointer by calling [IMalloc::Free](http://msdn.microsoft.com/library/com/htm/cmi_m_1smd.asp).

</dd> </dl>

## Return value

Type: **HRESULT**

Returns one of the following values.



| Return code                                                                                      | Description                                                     |
|--------------------------------------------------------------------------------------------------|-----------------------------------------------------------------|
| <dl> <dt>**S\_OK**</dt> </dl>             | Indicates success.<br/>                                   |
| <dl> <dt>**E\_INVALIDARG**</dt> </dl>     | Indicates that *ppszDisplay* is **NULL**.<br/>            |
| <dl> <dt>**E\_OUTOFMEMORY**</dt> </dl>    | Indicates that an attempt to allocate memory failed.<br/> |
| <dl> <dt>**MIME\_E\_NO\_DATA**</dt> </dl> | Indicates that there is no display name.<br/>             |



 

## Requirements



|                                     |                                                                                                                |
|-------------------------------------|----------------------------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows XP \[desktop apps only\]<br/>                                                                    |
| Minimum supported server<br/> | Windows Server 2003 \[desktop apps only\]<br/>                                                           |
| Product<br/>                  | Outlook Express 6.0<br/>                                                                                 |
| Header<br/>                   | <dl> <dt>Mimeole.h</dt> </dl>                           |
| IDL<br/>                      | <dl> <dt>Mimeole.idl</dt> </dl>                         |
| DLL<br/>                      | <dl> <dt>Inetcomm.dll (version 6.0 or later)</dt> </dl> |



 

 




