---
Description: The IsEqualObject function checks if two interfaces are on the same object.
ms.assetid: 51325e05-5a7f-4a80-a12e-2e7dedc028e2
title: IsEqualObject function
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# IsEqualObject function

The `IsEqualObject` function checks if two interfaces are on the same object.

## Syntax


```C++
BOOL WINAPI IsEqualObject(
   IUnknown *pFirst,
   IUnknown *pSecond
);
```



## Parameters

<dl> <dt>

*pFirst* 
</dt> <dd>

Pointer to one interface.

</dd> <dt>

*pSecond* 
</dt> <dd>

Pointer to the other interface.

</dd> </dl>

## Return value

Returns **TRUE** if the interfaces are both on the same object, or **FALSE** otherwise.

## Requirements



|                    |                                                                                                                                                                                            |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>Wxutil.h (include Streams.h)</dt> </dl>                                                                                    |
| Library<br/> | <dl> <dt>Strmbase.lib (retail builds); </dt> <dt>Strmbasd.lib (debug builds)</dt> </dl> |



## See also

<dl> <dt>

[Miscellaneous Helper Functions](miscellaneous-helper-functions.md)
</dt> </dl>

 

 



