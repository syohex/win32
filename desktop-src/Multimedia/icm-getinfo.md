---
title: ICM\_GETINFO message
description: The ICM\_GETINFO message queries a video compression driver to return a description of itself in an ICINFO structure.
ms.assetid: 8029f247-9777-4a34-9e84-908482094493
keywords:
- ICM_GETINFO message Windows Multimedia
topic_type:
- apiref
api_name:
- ICM_GETINFO
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

# ICM\_GETINFO message

The **ICM\_GETINFO** message queries a video compression driver to return a description of itself in an [**ICINFO**](/windows/win32/Vfw/ns-vfw-icinfo?branch=master) structure.


```C++
ICM_GETINFO 
wParam = (DWORD) (LPVOID) lpicinfo; 
lParam = sizeof(ICINFO); 
```



## Parameters

<dl> <dt>

<span id="lpicinfo"></span><span id="LPICINFO"></span>*lpicinfo*
</dt> <dd>

Pointer to an **ICINFO** structure to contain information.

</dd> <dt>

<span id="lParam"></span><span id="lparam"></span><span id="LPARAM"></span>*lParam*
</dt> <dd>

Size, in bytes, of **ICINFO**.

</dd> </dl>

## Return Value

Returns the size, in bytes, of [**ICINFO**](/windows/win32/Vfw/ns-vfw-icinfo?branch=master) or zero if an error occurs..

## Remarks

Typically, applications send this message to display a list of the installed compressors.

The driver should fill all members of the [**ICINFO**](/windows/win32/Vfw/ns-vfw-icinfo?branch=master) structure except **szDriver**.

## Requirements



|                                     |                                                                                  |
|-------------------------------------|----------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows 2000 Professional \[desktop apps only\]<br/>                       |
| Minimum supported server<br/> | Windows 2000 Server \[desktop apps only\]<br/>                             |
| Header<br/>                   | <dl> <dt>Vfw.h</dt> </dl> |



## See also

<dl> <dt>

[Video Compression Manager](video-compression-manager.md)
</dt> <dt>

[Video Compression Messages](video-compression-messages.md)
</dt> </dl>

 

 




