---
Description: The RecordFrameLateness method records how timely the rendering occurred and gathers statistics for the property page.
ms.assetid: 9d4b90d7-b529-40cc-a0fd-6635163fb7dd
title: CBaseVideoRenderer.RecordFrameLateness method
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# CBaseVideoRenderer.RecordFrameLateness method

The `RecordFrameLateness` method records how timely the rendering occurred and gathers statistics for the property page.

## Syntax


```C++
virtual void RecordFrameLateness(
   int trLate,
   int trFrame
);
```



## Parameters

<dl> <dt>

*trLate* 
</dt> <dd>

Value indicating how late the sample was beyond its due time, in reference time units.

</dd> <dt>

*trFrame* 
</dt> <dd>

Interframe time, in reference time units.

</dd> </dl>

## Return value

This method does not return a value.

## Requirements



|                    |                                                                                                                                                                                            |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>Renbase.h (include Streams.h)</dt> </dl>                                                                                   |
| Library<br/> | <dl> <dt>Strmbase.lib (retail builds); </dt> <dt>Strmbasd.lib (debug builds)</dt> </dl> |



## See also

<dl> <dt>

[**CBaseVideoRenderer Class**](cbasevideorenderer.md)
</dt> </dl>

 

 



