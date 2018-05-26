---
title: Extending the WAB Toolbar and Context Menu Actions
description: Clients wishing to extend the WABs set of \ 0034;Actions \ 0034; on contacts (such as \ 0034;Send Mail \ 0034;) can do so by implementing the IContextMenu Interface and the IWABExtInit interfaces and then registering them with the WAB.
ms.assetid: 6c0d7101-9c73-42f3-80fa-b5d8377e0558
keywords:
- address books
- Windows Address Book (WAB),toolbars
- WAB (Windows Address Book),toolbars
- Windows Address Book (WAB),context menus
- WAB (Windows Address Book),context menus
- Windows Address Book (WAB),registering context menu extensions
- WAB (Windows Address Book),registering context menu extensions
- registering WAB context menu extensions
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Extending the WAB Toolbar and Context Menu Actions

New applications should not use this set of interfaces. These interfaces exist for backward compatibility with legacy applications. These interfaces will be unavailable in the future.

> [!Note]  
> In Windows Vista, Windows Contacts replaces Windows Address Book (WAB). For more information about this new mechanism for storing and retrieving contact information, see [Windows Contacts](_wincontacts_entry_point).

 

Clients wishing to extend the WAB's set of "Actions" on contacts (such as "Send Mail") can do so by implementing the [IContextMenu Interface](_win32_IContextMenu) and the [**IWABExtInit**](/windows/previous-versions/Wabapi/?branch=master) interfaces and then registering them with the WAB.

## Registering Your Context Menu Extension CLSID

Register your extension's DLL CLSID in the registry.


```
HKEY_CLASSES_ROOT
   CLSID
```



Then register that CLSID under the following WAB registry key.


```
HKEY_LOCAL_MACHINE
   Software
      Microsoft
         WAB
            WAB4
               ExtContext
```



Create a String Key Value under this key whose name is the full CLSID identifying your [IContextMenu Interface](_win32_IContextMenu) implementation. The Value data part of the entry will be ignored.

## Initializing the Context Menu

The WAB calls [CoCreateInstance](7295a55b-12c7-4ed0-a7a4-9ecee16afdec) with your registered CLSID and requests an [IContextMenu Interface](_win32_IContextMenu) object. It then calls [IUnknown::QueryInterface](54d5ff80-18db-43f2-b636-f93ac053146d) on the IContextMenu Interface object to get the [**IWABExtInit**](/windows/previous-versions/Wabapi/?branch=master) interface.

Prior to calling [IContextMenu::QueryContextMenu Method](_win32_IContextMenu_QueryContextMenu), the WAB calls [**Initialize**](/windows/previous-versions/Wabapi/?branch=master) and passes a pointer to a [**WABEXTDISPLAY**](/windows/previous-versions/Wabapi/ns-wabapi-_wabextdisplay?branch=master) structure. You can determine if this is a precursor to a context menu extension or a property sheet extension by looking at the **ulFlags** member of the **WABEXTDISPLAY** structure. If **ulFlags** contains the *WAB\_CONTEXT\_ADRLIST* flag, **WABEXTDISPLAY** is a precursor to an [IContextMenu Interface](_win32_IContextMenu) operation. The **lpv** member contains a pointer to an [**ADRLIST**](/windows/previous-versions/Wabdefs/ns-wabdefs-_adrlist?branch=master) whose contents correspond to the properties of all the selected items on which this Context Menu action is being performed. Each entry in the **ADRLIST** contains information about a selected item in the WAB user interface (UI).

If you want to make sure that the data passed into [**Initialize**](/windows/previous-versions/Wabapi/?branch=master) stays valid and consistent until the WAB calls [IContextMenu::InvokeCommand Method](_win32_IContextMenu_InvokeCommand), call [IUnknown::AddRef](b4316efd-73d4-4995-b898-8025a316ba63) on the **lpPropObj** member of [**WABEXTDISPLAY**](/windows/previous-versions/Wabapi/ns-wabapi-_wabextdisplay?branch=master). If you do not call IUnknown::AddRef on **lpPropObj** at the time **Initialize** is called, the data may not stay valid when IContextMenu::InvokeCommand Method is called. If you do call IUnknown::AddRef, remember to call [IUnknown::Release](4b494c6f-f0ee-4c35-ae45-ed956f40dc7a) when you have finished to prevent memory leaks.

## Populating the Context Menu and the WAB Toolbar

Use your implementation of [IContextMenu::QueryContextMenu Method](_win32_IContextMenu_QueryContextMenu) to populate the passed menu with your entry. At this point, you have information about the items the user has selected from the [**ADRLIST**](/windows/previous-versions/Wabdefs/ns-wabdefs-_adrlist?branch=master) stored in **lpv**. Use that information to decide whether you want to add or disable any of your menu items.

When the user selects your menu item, the WAB calls [IContextMenu::InvokeCommand Method](_win32_IContextMenu_InvokeCommand).

The WAB uses your [IContextMenu Interface](_win32_IContextMenu) implementation to populate its Tools menu, all of its context menus, and the Toolbar\|Actions menu item.

If the user right-clicks a Lightweight Directory Access Protocol (LDAP) search result in the WAB, the WAB creates an LDAP URL for the selected LDAP entry and passes this LDAP URL to the Context Menu extensions. This gives the context menu extensions additional information about the selected entry. In some cases, the context menu extensions can retrieve further information about the selected entry by looking up the LDAP URL. The LDAP URL is passed to the context extension by adding the WAB\_DISPLAY\_LDAPURL flag to **ulFlags** and setting **lpsz** to the LDAP URL.

## Related topics

<dl> <dt>

[Extending the WAB Property Sheets](-wab-extending-prop-sheets.md)
</dt> </dl>

 

 



