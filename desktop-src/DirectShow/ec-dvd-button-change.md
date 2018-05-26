---
Description: Signals that the number of DVD menu buttons has changed, or that the button selection has changed.
ms.assetid: af6c841d-ca06-4535-b418-14409fa78c81
title: EC\_DVD\_BUTTON\_CHANGE
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# EC\_DVD\_BUTTON\_CHANGE

Signals that the number of DVD menu buttons has changed, or that the button selection has changed.

## Parameters

<dl> <dt>

<span id="lParam1"></span><span id="lparam1"></span><span id="LPARAM1"></span>*lParam1*
</dt> <dd>

**DWORD** value indicating the number of available buttons.

</dd> <dt>

<span id="lParam2"></span><span id="lparam2"></span><span id="LPARAM2"></span>*lParam2*
</dt> <dd>

**DWORD** value indicating the currently selected button number. Selected button number zero implies that no button is selected.

</dd> </dl>

## Remarks

Button numbers range from 1 to 36.

The currently selected button can change automatically with a navigation command authored on the disc as well as through application control by using [**IDvdControl2**](/windows/win32/Strmif/nn-strmif-idvdcontrol2?branch=master) interface.

This event can signal any of the available button numbers. These numbers do not always correspond to button numbers used for [**IDvdControl2::SelectAndActivateButton**](/windows/win32/Strmif/nf-strmif-idvdcontrol2-selectandactivatebutton?branch=master) because that method can activate only a subset of buttons.

This event is raised in all domains.

## Requirements



|                   |                                                                                                          |
|-------------------|----------------------------------------------------------------------------------------------------------|
| Header<br/> | <dl> <dt>Dvdevcode.h (include Dshow.h)</dt> </dl> |



## See also

<dl> <dt>

[DVD Applications](dvd-applications.md)
</dt> <dt>

[DVD Event Notification Codes](dvd-notification-codes.md)
</dt> <dt>

[Event Notification in DirectShow](event-notification-in-directshow.md)
</dt> </dl>

 

 



