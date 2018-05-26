---
title: MCIWNDM\_PLAYTO message
description: The MCIWNDM\_PLAYTO message plays the content of an MCI device from the current position to the specified ending location or until another command stops playback.
ms.assetid: ed940ee7-7b96-47da-99d3-6697f8a2e3d5
keywords:
- MCIWNDM_PLAYTO message Windows Multimedia
topic_type:
- apiref
api_name:
- MCIWNDM_PLAYTO
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

# MCIWNDM\_PLAYTO message

The **MCIWNDM\_PLAYTO** message plays the content of an MCI device from the current position to the specified ending location or until another command stops playback. If the specified ending location is beyond the end of the content, playback stops at the end of the content. You can send this message explicitly or by using the [**MCIWndPlayTo**](/windows/win32/Vfw/nf-vfw-mciwndplayto?branch=master) macro.


```C++
MCIWNDM_PLAYTO 
wParam = 0; 
lParam = (LPARAM) (LONG) lEnd; 
```



## Parameters

<dl> <dt>

<span id="lEnd"></span><span id="lend"></span><span id="LEND"></span>*lEnd*
</dt> <dd>

Ending location. The units for the ending location depend on the current time format.

</dd> </dl>

## Return Value

Returns zero if successful or an error otherwise.

## Remarks

This macro is defined using the [**MCIWndSeek**](/windows/win32/Vfw/nf-vfw-mciwndseek?branch=master) and [**MCIWndPlayTo**](/windows/win32/Vfw/nf-vfw-mciwndplayto?branch=master) macros, which in turn use the [MCI\_SEEK](mci-seek.md) command and the **MCIWNDM\_PLAYTO** message.

You can also specify both a starting and ending location for playback by using the [**MCIWndPlayFromTo**](/windows/win32/Vfw/nf-vfw-mciwndplayfromto?branch=master) macro.

## Requirements



|                                     |                                                                                  |
|-------------------------------------|----------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows 2000 Professional \[desktop apps only\]<br/>                       |
| Minimum supported server<br/> | Windows 2000 Server \[desktop apps only\]<br/>                             |
| Header<br/>                   | <dl> <dt>Vfw.h</dt> </dl> |



## See also

<dl> <dt>

[MCI\_SEEK](mci-seek.md)
</dt> <dt>

[**MCIWndPlayFromTo**](/windows/win32/Vfw/nf-vfw-mciwndplayfromto?branch=master)
</dt> <dt>

[**MCIWndPlayTo**](/windows/win32/Vfw/nf-vfw-mciwndplayto?branch=master)
</dt> <dt>

[**MCIWndSeek**](/windows/win32/Vfw/nf-vfw-mciwndseek?branch=master)
</dt> </dl>

 

 




