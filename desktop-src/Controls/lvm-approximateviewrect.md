---
title: LVM\_APPROXIMATEVIEWRECT message
description: Calculates the approximate width and height required to display a given number of items. You can send this message explicitly or use the ListView\_ApproximateViewRect macro.
ms.assetid: a14331a8-217d-48c6-9489-fb90c4d31b91
keywords:
- LVM_APPROXIMATEVIEWRECT message Windows Controls
topic_type:
- apiref
api_name:
- LVM_APPROXIMATEVIEWRECT
api_location:
- Commctrl.h
api_type:
- HeaderDef
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# LVM\_APPROXIMATEVIEWRECT message

Calculates the approximate width and height required to display a given number of items. You can send this message explicitly or use the [**ListView\_ApproximateViewRect**](/windows/win32/Commctrl/nf-commctrl-listview_approximateviewrect?branch=master) macro.

## Parameters

<dl> <dt>

*wParam* 
</dt> <dd>

The number of items to be displayed in the control. If this parameter is set to -1, the message uses the total number of items in the control.

</dd> <dt>

*lParam* 
</dt> <dd>

The [**LOWORD**](https://msdn.microsoft.com/library/windows/desktop/ms632659) is the proposed x-dimension of the control, in pixels. This parameter can be set to -1 to allow the message to use the current width value.

The [**HIWORD**](https://msdn.microsoft.com/library/windows/desktop/ms632657) is the proposed y-dimension of the control, in pixels. This parameter can be set to -1 to allow the message to use the current height value.

</dd> </dl>

## Return value

Returns a **DWORD** value that holds the approximate width (in the [**LOWORD**](https://msdn.microsoft.com/library/windows/desktop/ms632659)) and height (in the [**HIWORD**](https://msdn.microsoft.com/library/windows/desktop/ms632657)) needed to display the items, in pixels.

## Remarks

Setting the size of the list-view control based on the dimensions provided by this message can optimize redraw and reduce flicker.

## Requirements



|                                     |                                                                                       |
|-------------------------------------|---------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows Vista \[desktop apps only\]<br/>                                        |
| Minimum supported server<br/> | Windows Server 2003 \[desktop apps only\]<br/>                                  |
| Header<br/>                   | <dl> <dt>Commctrl.h</dt> </dl> |



 

 




