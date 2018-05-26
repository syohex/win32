---
title: IsLoadBalancingServer method of the Win32\_TSGatewayLoadBalancer class
description: Determines whether the Remote Desktop Gateway (RD Gateway) server can perform load balancing.
audience: developer
author: REDMOND\\markl
manager: REDMOND\\markl
ms.assetid: ae1a91c1-0b8b-4bd0-83f9-41c973247f27
ms.prod: windows-server-dev
ms.technology: remote-desktop-services
ms.tgt_platform: multiple
keywords:
- IsLoadBalancingServer method Remote Desktop Services
- IsLoadBalancingServer method Remote Desktop Services , Win32_TSGatewayLoadBalancer class
- Win32_TSGatewayLoadBalancer class Remote Desktop Services , IsLoadBalancingServer method
topic_type:
- apiref
api_name:
- Win32_TSGatewayLoadBalancer.IsLoadBalancingServer
api_location:
- AagWmi.dll
api_type:
- COM
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
---

# IsLoadBalancingServer method of the Win32\_TSGatewayLoadBalancer class

Determines whether the Remote Desktop Gateway (RD Gateway) server can perform load balancing.

## Syntax


```mof
uint32 IsLoadBalancingServer(
  [out] boolean LoadBalancing
);
```



## Parameters

<dl> <dt>

*LoadBalancing* \[out\]
</dt> <dd>

**TRUE** if the server can perform load balancing, and **FALSE** otherwise.

</dd> </dl>

## Return value

If the method succeeds, it returns zero. If the method is unsuccessful, it returns a nonzero value. For a list of error codes, see [Remote Desktop Services WMI Provider Error Codes](terminal-services-wmi-provider-error-codes.md).

## Remarks

You must be a member of the Administrators group to call this method.

Managed Object Format (MOF) files contain the definitions for Windows Management Instrumentation (WMI) classes. MOF files are not installed as part of the Microsoft Windows Software Development Kit (SDK). They are installed on the server when you add the associated role by using the Server Manager. For more information about MOF files, see [Managed Object Format (MOF)](https://msdn.microsoft.com/library/aa823192).

## Requirements



|                                     |                                                                                          |
|-------------------------------------|------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | None supported<br/>                                                                |
| Minimum supported server<br/> | Windows Server 2008<br/>                                                           |
| Namespace<br/>                | Root\\CIMv2\\TerminalServices<br/>                                                 |
| MOF<br/>                      | <dl> <dt>TSGateway.mof</dt> </dl> |
| DLL<br/>                      | <dl> <dt>AagWmi.dll</dt> </dl>    |



## See also

<dl> <dt>

[**Win32\_TSGatewayLoadBalancer**](win32-tsgatewayloadbalancer.md)
</dt> </dl>

 

 




