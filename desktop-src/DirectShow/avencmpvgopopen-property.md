---
Description: Specifies whether the encoder produces open groups of pictures (GOPs) or closed GOPs. This property applies to MPEG video encoders.
ms.assetid: 424751cd-65d2-4cab-9f7b-cad50c09c767
title: AVEncMPVGOPOpen property
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# AVEncMPVGOPOpen property

Specifies whether the encoder produces open groups of pictures (GOPs) or closed GOPs. This property applies to MPEG video encoders.

This property is read/write.

## Data type

**VARIANT\_BOOL** (**VT\_BOOL**)

## Property GUID

**CODECAPI\_AVEncMPVGOPOpen**

## Property value



| Value          | Description |
|----------------|-------------|
| VARIANT\_FALSE | Closed GOPs |
| VARIANT\_TRUE  | Open GOPs   |



 

## Remarks

An open GOP contains delta frames that reference frames from the previous GOP. A closed GOP does not contain any delta frames that reference the previous GOP.

## Requirements



|                                     |                                                                                       |
|-------------------------------------|---------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows 2000 Professional \[desktop apps \| UWP apps\]<br/>                     |
| Minimum supported server<br/> | Windows 2000 Server \[desktop apps \| UWP apps\]<br/>                           |
| Header<br/>                   | <dl> <dt>Codecapi.h</dt> </dl> |



## See also

<dl> <dt>

[Codec API Properties](codec-api-properties.md)
</dt> <dt>

[**ICodecAPI Interface**](/windows/win32/Strmif/nn-strmif-icodecapi?branch=master)
</dt> </dl>

 

 



