---
title: RestoreProperties method of the CIM\_LogicalDevice class
description: Restores a previous configuration and state of the sensor.
audience: developer
author: REDMOND\\markl
manager: REDMOND\\markl
ms.assetid: 258b8ba8-d389-4822-8a38-635caaad1590
ms.prod: windows-server-dev
ms.technology:
- intelligent-platform-management-interface
- windows-management-instrumentation
ms.tgt_platform: multiple
keywords:
- RestoreProperties method
- RestoreProperties method, CIM_LogicalDevice class
- CIM_LogicalDevice class, RestoreProperties method
topic_type:
- apiref
api_name:
- CIM_LogicalDevice.RestoreProperties
api_location:
- IpmiPrv.dll
api_type:
- COM
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
---

# RestoreProperties method of the CIM\_LogicalDevice class

> [!Note]  
> This method is deprecated. Instead we recommend that you use the **ApplyConfiguration** property of the **CIM\_ConfigurationData** class.

 

Restores a previous configuration and state of the sensor.

This method is inherited from [**CIM\_LogicalDevice**](cim-logicaldevice.md).

## Syntax


```mof
uint32 RestoreProperties();
```



## Parameters

This method has no parameters.

## Return value

A return code that indicates whether the operation completed successfully.

<dl> <dt>


</dt> <dd>

0

The operation completed successfully.

</dd> <dt>


</dt> <dd>

1

The operation was not completed because it is not supported.

</dd> <dt>


</dt> <dd>

2 ...

The operation was not completed because an error occurred.

</dd> </dl>

## Requirements



|                                     |                                                                                        |
|-------------------------------------|----------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows Vista<br/>                                                               |
| Minimum supported server<br/> | Windows Server 2008<br/>                                                         |
| Namespace<br/>                | Root\\Hardware<br/>                                                              |
| MOF<br/>                      | <dl> <dt>IpmiPrv.mof</dt> </dl> |
| DLL<br/>                      | <dl> <dt>IpmiPrv.dll</dt> </dl> |



## See also

<dl> <dt>

[**CIM\_LogicalDevice**](cim-logicaldevice.md)
</dt> </dl>

 

 




