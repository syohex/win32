---
Description: Retrieves an IP route to the specified remote address.
ms.assetid: 419427b0-199f-4d52-806b-d1e1f98f28c0
title: Find method of the MSFT\_NetRoute class
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Find method of the MSFT\_NetRoute class

Retrieves an IP route to the specified remote address.

## Syntax


```mof
uint32 Find(
  [in]  uint32             InterfaceIndex,
  [in]  string             LocalIPAddress,
  [in]  string             RemoteIPAddress,
  [out] CIM_ManagedElement CmdletOutput[]
);
```



## Parameters

<dl> <dt>

*InterfaceIndex* \[in\]
</dt> <dd>

The interface index of the route.

</dd> <dt>

*LocalIPAddress* \[in\]
</dt> <dd>

The local IP address of the route.

</dd> <dt>

*RemoteIPAddress* \[in\]
</dt> <dd>

The remote address of the route.

</dd> <dt>

*CmdletOutput* \[out\]
</dt> <dd>

The [**CIM\_ManagedElement**](https://msdn.microsoft.com/library/mt432218) object that receives the route.

</dd> </dl>

## Requirements



|                                     |                                                                                         |
|-------------------------------------|-----------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows 8.1<br/>                                                                  |
| Minimum supported server<br/> | Windows Server 2012 R2<br/>                                                       |
| Namespace<br/>                | Root\\standardcimv2<br/>                                                          |
| MOF<br/>                      | <dl> <dt>NetTCPIP.Mof</dt> </dl> |
| DLL<br/>                      | <dl> <dt>NetTCPIP.dll</dt> </dl> |



## See also

<dl> <dt>

[**MSFT\_NetRoute**](msft-netroute.md)
</dt> </dl>

 

 



