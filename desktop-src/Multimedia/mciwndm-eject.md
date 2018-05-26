---
title: MCIWNDM\_EJECT message
description: The MCIWNDM\_EJECT message sends a command to an MCI device to eject its media. You can send this message explicitly or by using the MCIWndEject macro.
ms.assetid: a492f504-8b58-480e-9766-bc2878466c44
keywords:
- MCIWNDM_EJECT message Windows Multimedia
topic_type:
- apiref
api_name:
- MCIWNDM_EJECT
api_location:
- Vfw.h
api_type:
- HeaderDef
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# MCIWNDM\_EJECT message

The **MCIWNDM\_EJECT** message sends a command to an MCI device to eject its media. You can send this message explicitly or by using the [**MCIWndEject**](/windows/win32/Vfw/nf-vfw-mciwndeject?branch=master) macro.


```C++
MCIWNDM_EJECT 
wParam = 0; 
lParam = 0; 
```



## Return Value

Returns zero if successful or an error otherwise.

## Requirements



|                                     |                                                                                  |
|-------------------------------------|----------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows 2000 Professional \[desktop apps only\]<br/>                       |
| Minimum supported server<br/> | Windows 2000 Server \[desktop apps only\]<br/>                             |
| Header<br/>                   | <dl> <dt>Vfw.h</dt> </dl> |



## See also

<dl> <dt>

[**MCIWndEject**](/windows/win32/Vfw/nf-vfw-mciwndeject?branch=master)
</dt> </dl>

 

 




