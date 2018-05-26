---
title: DRM\_ActionAllowed\_CollaborativePlay
description: The DRM\_ActionAllowed\_CollaborativePlay attribute indicates whether the license allows the content to be played collaboratively.
ms.assetid: 111e8fa7-ef5a-483a-b930-8a8e5b4d120a
keywords:
- DRM_ActionAllowed_CollaborativePlay windows Media Format
topic_type:
- apiref
api_name:
- DRM_ActionAllowed_CollaborativePlay
api_type:
- NA
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# DRM\_ActionAllowed\_CollaborativePlay

The **DRM\_ActionAllowed\_CollaborativePlay** attribute indicates whether the license allows the content to be played collaboratively.

## Global Constant

g\_wszWMDRM\_ActionAllowed\_CollaborativePlay

## Data Type

**WMT\_TYPE\_BOOL**

## Remarks

The collaborative play right applies to playing protected content as part of a collaborative session using peer-to-peer services. For example, users of MSN Messenger 2004 can play protected content in a MusicMix session. This right can only be used to contribute a protected file to a single session at one time, and all users participating in the session must be online to render the content.

This is a read-only property that is retrieved using [**IWMDRMReader::GetDRMProperty**](/windows/win32/Wmsdkidl/nf-wmsdkidl-iwmdrmreader-getdrmproperty?branch=master).

## See also

<dl> <dt>

[**DRM Properties**](drm-properties.md)
</dt> </dl>

 

 



