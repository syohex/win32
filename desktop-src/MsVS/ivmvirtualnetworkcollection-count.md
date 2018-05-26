---
title: IVMVirtualNetworkCollection Count property
description: The Count property contains the number of virtual networks in this collection.
ms.assetid: e5981c05-1bdd-4692-b87d-9fb75be6fd5d
keywords:
- Count property Virtual Server
- Count property Virtual Server , IVMVirtualNetworkCollection interface
- IVMVirtualNetworkCollection interface Virtual Server , Count property
- Count property Virtual Server , IVMVirtualNetworkCollection interface
- IVMVirtualNetworkCollection interface Virtual Server , Count property
topic_type:
- apiref
api_name:
- IVMVirtualNetworkCollection.Count
- IVMVirtualNetworkCollection.get_Count
- IVMVirtualNetworkCollection.Count
api_location:
- VsComInterfaces.h
api_type:
- COM
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# IVMVirtualNetworkCollection::Count property

The **Count** property contains the number of virtual networks in this collection.

This property is read-only.

## Syntax


```C++
HRESULT get_Count(
  [out] long *count
);
```

<span codelanguage="VisualBasic"></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th>VB</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><pre><code>IVMVirtualNetworkCollection.Count( _
  ByRef count _
)</code></pre></td>
</tr>
</tbody>
</table>



## Property value

The number of virtual networks in this collection.

This property value is read-only.

## Error codes



| Name                                                                                          | Meaning                                       |
|-----------------------------------------------------------------------------------------------|-----------------------------------------------|
| <dl> <dt>S\_OK</dt> </dl>              | The operation was successful.<br/>      |
| <dl> <dt> E\_POINTER</dt> </dl>        | The *count* parameter is **NULL**.<br/> |
| <dl> <dt>DISP\_E\_EXCEPTION</dt> </dl> | An unexpected error has occurred.<br/>  |



## Requirements



|                     |                                                                                                   |
|---------------------|---------------------------------------------------------------------------------------------------|
| Product<br/>  | Microsoft Virtual Server 2005 onWindows Server 2003<br/>                                    |
| Download<br/> | Microsoft Virtual Server 2005 R2 SP1 Update onWindows Server 2008orWindows Server 2003<br/> |
| Header<br/>   | <dl> <dt>VsComInterfaces.h</dt> </dl>      |



## See also

<dl> <dt>

[**IVMVirtualNetworkCollection**](ivmvirtualnetworkcollection.md)
</dt> </dl>

 

 




