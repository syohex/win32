---
Description: The Clear method deletes all items from the collection.
ms.assetid: 4350ae43-16be-4cf2-816d-719349b12654
title: IPortableDeviceValuesClear method
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# IPortableDeviceValues::Clear method

The **Clear** method deletes all items from the collection.

## Syntax


```C++
HRESULT Clear();
```



## Parameters

This method has no parameters.

## Return value

The method returns an **HRESULT**. Possible values include, but are not limited to, those in the following table.



| Return code                                                                          | Description                      |
|--------------------------------------------------------------------------------------|----------------------------------|
| <dl> <dt>**S\_OK**</dt> </dl> | The method succeeded.<br/> |



 

## Remarks

This method frees the memory for all dynamically allocated items in the collection. For interfaces, it calls **Release**.

## Requirements



|                    |                                                                                                    |
|--------------------|----------------------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>PortableDeviceTypes.h</dt> </dl>   |
| Library<br/> | <dl> <dt>PortableDeviceGUIDs.lib</dt> </dl> |



## See also

<dl> <dt>

[**IPortableDeviceValues Interface**](iportabledevicevalues.md)
</dt> </dl>

 

 



