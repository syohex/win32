---
Description: Retrieves the number of type-information interfaces provided by an object.
ms.assetid: e16bc324-bb49-4df2-afeb-2c2cd1620693
title: CMediaEvent.GetTypeInfoCount method
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# CMediaEvent.GetTypeInfoCount method

Retrieves the number of type-information interfaces provided by an object.

## Syntax


```C++
HRESULT GetTypeInfoCount(
   UINT *pctinfo
);
```



## Parameters

<dl> <dt>

*pctinfo* 
</dt> <dd>

Pointer to number of type-information interfaces that the object provides. If the object provides type information, this number is 1; otherwise, the number is 0.

</dd> </dl>

## Return value

Returns E\_POINTER if *pctinfo* is invalid; otherwise, returns S\_OK.

## Requirements



|                    |                                                                                                                                                                                            |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>Ctlutil.h (include Streams.h)</dt> </dl>                                                                                   |
| Library<br/> | <dl> <dt>Strmbase.lib (retail builds); </dt> <dt>Strmbasd.lib (debug builds)</dt> </dl> |



## See also

<dl> <dt>

[**CMediaEvent Class**](cmediaevent.md)
</dt> </dl>

 

 



