---
Description: The Microsoft Windows operating system provides support for a variety of hardware devices and network time protocols using the time provider architecture.
ms.assetid: 04f523d7-7e99-4bf5-941f-ae67f4b9df0a
title: Time Provider
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Time Provider

The Microsoft Windows operating system provides support for a variety of hardware devices and network time protocols using the *time provider* architecture. Input time providers retrieve accurate time stamps from hardware or the network, and output time providers provide time stamps to other clients on the network.

Time providers are managed by the *time provider manager*. It is responsible for loading, starting, and stopping time providers as directed by the service control manager. This interface makes writing a time provider easier than writing a full service.

-   [Creating a Time Provider](creating-a-time-provider.md)
-   [Registering a Time Provider](registering-a-time-provider.md)
-   [Sample Time Provider](sample-time-provider.md)

## Related topics

<dl> <dt>

[Windows Time Service](Http://go.microsoft.com/fwlink/p/?linkid=84119)
</dt> </dl>

 

 


