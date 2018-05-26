---
title: Accessing an Object by Using VTBL
description: Automation allows an ActiveX client to call a method or property accessor function directly, either within or across processes. This approach, called VTBL binding, does not use the IDispatch interface.
ms.assetid: feaac087-acc2-47c2-8e2c-3ea31b936da1
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Accessing an Object by Using VTBL

Automation allows an ActiveX client to call a method or property accessor function directly, either within or across processes. This approach, called *VTBL binding*, does not use the [**IDispatch**](/windows/previous-versions/oaidl/nn-oaidl-idispatch?branch=master) interface. The client obtains type information from the type library at compile time, and then calls the methods and functions directly. VTBL binding is faster than both ID binding and late binding because the access is direct, and no calls are made through [**IDispatch**](/windows/previous-versions/oaidl/nn-oaidl-idispatch?branch=master).

 

 



