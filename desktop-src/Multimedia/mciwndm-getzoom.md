---
title: MCIWNDM\_GETZOOM message
description: The MCIWNDM\_GETZOOM message retrieves the current zoom value used by an MCI device. You can send this message explicitly or by using the MCIWndGetZoom macro.
ms.assetid: 92db8df2-515a-4616-a0f5-245d466ba379
keywords:
- MCIWNDM_GETZOOM message Windows Multimedia
topic_type:
- apiref
api_name:
- MCIWNDM_GETZOOM
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

# MCIWNDM\_GETZOOM message

The **MCIWNDM\_GETZOOM** message retrieves the current zoom value used by an MCI device. You can send this message explicitly or by using the [**MCIWndGetZoom**](/windows/win32/Vfw/nf-vfw-mciwndgetzoom?branch=master) macro.


```C++
MCIWNDM_GETZOOM 
wParam = 0; 
lParam = 0; 
```



## Return Value

Returns the most recent values used with [**MCIWNDM\_SETZOOM**](mciwndm-setzoom.md).

## Remarks

A return value of 100 indicates the image is not zoomed. A value of 200 indicates the image is enlarged to twice its original size. A value of 50 indicates the image is reduced to half its original size.

## Requirements



|                                     |                                                                                  |
|-------------------------------------|----------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows 2000 Professional \[desktop apps only\]<br/>                       |
| Minimum supported server<br/> | Windows 2000 Server \[desktop apps only\]<br/>                             |
| Header<br/>                   | <dl> <dt>Vfw.h</dt> </dl> |



## See also

<dl> <dt>

[**MCIWndGetZoom**](/windows/win32/Vfw/nf-vfw-mciwndgetzoom?branch=master)
</dt> <dt>

[**MCIWNDM\_SETZOOM**](mciwndm-setzoom.md)
</dt> </dl>

 

 




