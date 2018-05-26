---
Description: Demonstrates the use of Function Discovery API.
ms.assetid: b67e9b53-1c4f-41bf-85bd-d901f3859e92
title: Function Discovery Sample
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Function Discovery Sample

\[Function Discovery is available for use in the following versions of Windows: Windows Server 2012, Windows 8, Windows Server 2008 R2, Windows 7, Windows Server 2008, and Windows Vista. It may be altered or unavailable in subsequent versions.\]

The Function Discovery sample demonstrates the use of Function Discovery API. The source code for the sample can be found in the SDK installation location under C:\\Program Files\\Microsoft SDKs\\Windows\\&lt;version number&gt;\\Samples\\winbase\\DeviceFoundation\\FunctionDiscovery\\Client. The Windows Vista SDK is available from the [Download Center](http://go.microsoft.com/fwlink/p/?linkid=102968).

The Function Discovery sample performs the following tasks:

-   Queries the PnP provider for function instances. The [**IFunctionDiscovery::CreateInstanceCollectionQuery**](/windows/win32/FunctionDiscoveryAPI/nf-functiondiscoveryapi-ifunctiondiscovery-createinstancecollectionquery?branch=master) and [**IFunctionInstanceCollectionQuery::Execute**](/windows/win32/FunctionDiscoveryAPI/nf-functiondiscoveryapi-ifunctioninstancecollectionquery-execute?branch=master) methods are used.
-   Displays the list of PnP devices available on the machine. The [**GetCount**](/windows/win32/FunctionDiscoveryAPI/nf-functiondiscoveryapi-ifunctioninstancecollection-getcount?branch=master) and [**Item**](/windows/win32/FunctionDiscoveryAPI/nf-functiondiscoveryapi-ifunctioninstancecollection-item?branch=master) methods of the [**IFunctionInstanceCollection**](/windows/win32/FunctionDiscoveryAPI/nn-functiondiscoveryapi-ifunctioninstancecollection?branch=master) interface are used.
-   Displays the metadata associated with the device. The [**IFunctionInstance::OpenPropertyStore**](/windows/win32/FunctionDiscoveryAPI/nf-functiondiscoveryapi-ifunctioninstance-openpropertystore?branch=master) method is used.
-   Handles PnP notifications. The [**OnUpdate**](ifunctiondiscoverynotification-onupdate-method.md), [**OnError**](ifunctiondiscoverynotification-onerror.md), and [**OnEvent**](ifunctiondiscoverynotification-onevent.md) methods of the [**IFunctionDiscoveryNotification**](/windows/win32/FunctionDiscoveryNotification/nn-functiondiscoveryapi-ifunctiondiscoverynotification?branch=master) interface are implemented.

## Related topics

<dl> <dt>

[Using Function Discovery](using-function-discovery.md)
</dt> <dt>

[Using Function Discovery Providers](using-function-discovery-providers.md)
</dt> <dt>

[Function Discovery Provider Sample](function-discovery-provider-sample.md)
</dt> </dl>

 

 


