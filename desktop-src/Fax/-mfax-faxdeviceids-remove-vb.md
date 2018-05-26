---
Description: The Remove method removes an item from the FaxDeviceIds collection.
ms.assetid: f9af12c5-9621-44f1-85f8-58346d42e812
title: FaxDeviceIds.Remove method
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# FaxDeviceIds.Remove method

The **Remove** method removes an item from the [**FaxDeviceIds**](-mfax-faxdeviceids.md) collection.

## Syntax


```VB
FaxDeviceIds.Remove( _
  ByVal lIndex As Long _
) As Long
```



## Parameters

<dl> <dt>

*lIndex* \[in\]
</dt> <dd>

Type: **Long**

A **Long** value that specifies the index of the item to remove from the collection. Valid values for this parameter are in the range from 1 to n, where n is the number of devices returned by a call to the [**Count**](-mfax-faxdeviceids-count-vb.md) property.

</dd> </dl>

## Remarks

> [!Note]  
> You cannot remove devices from the special **All Devices** routing group.

 

To use this method, a user must have the [****farMANAGE\_CONFIG****](/windows/previous-versions/FaxComex/ne-faxcomex-fax_access_rights_enum?branch=master) access right.

## Requirements



|                                     |                                                                                         |
|-------------------------------------|-----------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows XP \[desktop apps only\]<br/>                                             |
| Minimum supported server<br/> | Windows Server 2003 \[desktop apps only\]<br/>                                    |
| Header<br/>                   | <dl> <dt>FaxComex.h</dt> </dl>   |
| DLL<br/>                      | <dl> <dt>Fxscomex.dll</dt> </dl> |



## See also

<dl> <dt>

[Visual Basic Example](-mfax-managing-outbound-routing-groups.md)
</dt> <dt>

[**FaxDeviceIds**](-mfax-faxdeviceids.md)
</dt> <dt>

[**IFaxDeviceIds**](/windows/previous-versions/FaxComex/nn-faxcomex-ifaxdeviceids?branch=master)
</dt> </dl>

 

 



