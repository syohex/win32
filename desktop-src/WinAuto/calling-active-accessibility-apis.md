---
title: Calling Active Accessibility APIs
description: Microsoft Active Accessibility provides application programming interfaces (APIs) for both clients and servers.
ms.assetid: c40441d2-7294-4c76-8b42-08ed66eccb7e
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Calling Active Accessibility APIs

Microsoft Active Accessibility provides application programming interfaces (APIs) for both clients and servers. Most are implemented in the Microsoft Active Accessibility dynamic-link library, Oleacc.dll, but [**NotifyWinEvent**](/windows/win32/Winuser/nf-winuser-notifywinevent?branch=master), [**SetWinEventHook**](/windows/win32/Winuser/nf-winuser-setwineventhook?branch=master), and [**UnhookWinEvent**](/windows/win32/Winuser/nf-winuser-unhookwinevent?branch=master) are implemented in user32.dll, which is a core component of the Microsoft Windows operating system.

Computers running Windows 95 or Microsoft Windows NT 4.0 do not have Oleacc.dll and the correct version of user32.dll installed because Microsoft Active Accessibility was incorporated in stages into succeeding versions of Windows. As a result, applications that run on these platforms explicitly link to Oleacc.dll at run time using the [**LoadLibrary**](https://msdn.microsoft.com/library/windows/desktop/ms684175) function instead of relying on import libraries. Active Accessibility 1.3 supports Windows 95 and Microsoft Windows NT 4.0. Earlier versions of Windows are not supported by Microsoft Active Accessibility.

Server applications use the [**GetProcAddress**](https://msdn.microsoft.com/library/windows/desktop/ms683212) function to retrieve the address of an Microsoft Active Accessibility function and then make the call through a function pointer. If calling a function that was implemented in Oleacc.dll, server applications use the handle returned from [**LoadLibrary**](https://msdn.microsoft.com/library/windows/desktop/ms684175) in the call to **GetProcAddress**. If calling a function defined in user32.dll, server applications call [**GetModuleHandle**](https://msdn.microsoft.com/library/windows/desktop/ms683199) specifying "USER32" and use the returned module handle in the call to **GetProcAddress**.

For example, if an application uses [**NotifyWinEvent**](/windows/win32/Winuser/nf-winuser-notifywinevent?branch=master), it calls [**GetProcAddress**](https://msdn.microsoft.com/library/windows/desktop/ms683212) using the module handle of user32.dll to get the address of the function. If the call is successful (meaning that this version of Windows supports Microsoft Active Accessibility), then the application sets a flag that indicates that it is safe to call **NotifyWinEvent**. The address received from **GetProcAddress** is stored in a function pointer variable and used throughout the code.

 

 



