---
title: XML Language Support
description: This section describe level of XML Language support in WWS.
ms.assetid: c3408c2a-6506-4a2e-8083-b4a0154a6918
keywords:
- XML Language Support Web Services for Windows
- WWSAPI
- WWS
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# XML Language Support

This section describe level of XML Language support in WWS.

## 

See the functions DownlevelLCIDToLocaleName on versions of Windows earlier than Windows Vista, and LCIDToLocalName otherwise, to convert between an LCID and an xml:lang value.

When reading, [**WsGetXmlAttribute**](/windows/win32/WebServices/nf-webservices-wsgetxmlattribute?branch=master) may be used to discover the value of an "xml:lang" attribute in scope.

When writing, [**WsWriteStartAttribute**](/windows/win32/WebServices/nf-webservices-wswritestartattribute?branch=master) may be used to write an "xml:lang" attribute.

 

 



