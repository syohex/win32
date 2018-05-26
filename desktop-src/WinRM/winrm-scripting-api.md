---
title: WinRM Scripting API
description: Windows Remote Management scripting objects are implemented as a layer above the WS-Management Protocol.
audience: developer
author: REDMOND\\markl
manager: REDMOND\\markl
ms.assetid: bd642669-554f-40ab-bd40-235013afa077
ms.prod: windows-server-dev
ms.technology: windows-remote-management
ms.tgt_platform: multiple
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
---

# WinRM Scripting API

Windows Remote Management scripting objects are implemented as a layer above the [WS-Management Protocol](ws-management-protocol.md). The scripting objects enable you to obtain data or manage [*resources*](windows-remote-management-glossary.md#winrm-gloss-resource) on local and remote computers.

## WS-Management Objects

Each scripting object has a corresponding C++ interface. For more information, see [WinRM C++ API](winrm-c---api.md) and [Scripting in Windows Remote Management](scripting-in-windows-remote-management.md).

The following objects are provided by the WinRM Scripting API.

<dl> <dt>

<span id="ConnectionOptions"></span><span id="connectionoptions"></span><span id="CONNECTIONOPTIONS"></span>[**ConnectionOptions**](connectionoptions.md)
</dt> <dd>

Defines the user name and password used for remote connections. The user name and password are passed when calling the [**CreateConnectionOptions**](wsman-createconnectionoptions.md) method. For more information, see [Obtaining Data from a Remote Computer](obtaining-data-from-a-remote-computer.md). The corresponding C++ interface is [**IWSManConnectionOptions**](/windows/win32/WSManDisp/nn-wsmandisp-iwsmanconnectionoptions?branch=master).

</dd> <dt>

<span id="Enumerator"></span><span id="enumerator"></span><span id="ENUMERATOR"></span>[**Enumerator**](enumerator.md)
</dt> <dd>

Represents a collection of results returned from enumerating a resource. For more information, see [Enumerating or Listing All the Instances of a Resource](enumerating-or-listing-all-instances-of-a-resource.md). The corresponding C++ interface is [**IWSManEnumerator**](/windows/win32/WSManDisp/nn-wsmandisp-iwsmanenumerator?branch=master).

</dd> <dt>

<span id="ResourceLocator"></span><span id="resourcelocator"></span><span id="RESOURCELOCATOR"></span>[**ResourceLocator**](resourcelocator.md)
</dt> <dd>

Supplies the path to a resource. You can use a [**ResourceLocator**](resourcelocator.md) object instead of a [*resource URI*](windows-remote-management-glossary.md#winrm-gloss-resource-uri) in [**Session**](session.md) object operations, such as [**Session.Get**](session-get.md), [**Session.Put**](session-put.md), or [**Session.Enumerate**](session-enumerate.md). The corresponding C++ interface is [**IWSManResourceLocator**](/windows/win32/WSManDisp/nn-wsmandisp-iwsmanresourcelocator?branch=master).

</dd> <dt>

<span id="Session"></span><span id="session"></span><span id="SESSION"></span>[**Session**](session.md)
</dt> <dd>

Defines the network operations and properties available for the session, such as [**Session.Get**](session-get.md), [**Session.Enumerate**](session-enumerate.md), [**Session.Invoke**](session-invoke.md). For more information, see [Obtaining Data from the Local Computer](obtaining-data-from-the-local-computer.md). The corresponding C++ interface is [**IWSManSession**](/windows/win32/WSManDisp/nn-wsmandisp-iwsmansession?branch=master).

</dd> <dt>

<span id="WSMan"></span><span id="wsman"></span><span id="WSMAN"></span>[**WSMan**](wsman.md)
</dt> <dd>

Provides methods and properties used to create a new session or manage an established session. For more information see, [Using Windows Remote Management](using-windows-remote-management.md). The corresponding C++ interfaces are [**IWSMan**](/windows/win32/WSManDisp/nn-wsmandisp-iwsman?branch=master) and [**IWSManEx**](/windows/win32/WSManDisp/nn-wsmandisp-iwsmanex?branch=master).

</dd> </dl>

## Related topics

<dl> <dt>

[About Windows Remote Management](about-windows-remote-management.md)
</dt> <dt>

[Using Windows Remote Management](using-windows-remote-management.md)
</dt> <dt>

[Scripting in Windows Remote Management](scripting-in-windows-remote-management.md)
</dt> <dt>

[Windows Remote Management Reference](windows-remote-management-reference.md)
</dt> </dl>

 

 



