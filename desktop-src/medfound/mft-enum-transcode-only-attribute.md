---
Description: Specifies whether a decoder is optimized for transcoding rather than for playback.
ms.assetid: 0e05cb05-87a8-4174-a3c6-a0a0c7765024
title: MFT\_ENUM\_TRANSCODE\_ONLY\_ATTRIBUTE attribute
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# MFT\_ENUM\_TRANSCODE\_ONLY\_ATTRIBUTE attribute

Specifies whether a decoder is optimized for transcoding rather than for playback.

Currently, this attribute applies only to hardware-based decoders that use the AVStream mini-driver. The attribute is stored in the registry under the decoder's capabilities information. For more information, see the documentation for [**IGetCapabilitiesKey**](dshow.igetcapabilitieskey).

Applications typically do not use this attribute.

## Data type

**REG\_DWORD**

## Remarks

If this registry entry is present and equal to 1, the [**MFTEnumEx**](/windows/win32/mfapi/nf-mfapi-mftenumex?branch=master) function skips the decoder unless the caller specified the **MFT\_ENUM\_FLAG\_TRANSCODE\_ONLY** flag in **MFTEnumEx**.

The GUID constant for this attribute is exported from mfuuid.lib.

## Requirements



|                                     |                                                                                          |
|-------------------------------------|------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows 7 \[desktop apps \| UWP apps\]<br/>                                        |
| Minimum supported server<br/> | Windows Server 2008 R2 \[desktop apps \| UWP apps\]<br/>                           |
| Header<br/>                   | <dl> <dt>Mftransform.h</dt> </dl> |



## See also

<dl> <dt>

[Alphabetical List of Media Foundation Attributes](alphabetical-list-of-media-foundation-attributes.md)
</dt> <dt>

[**MFTEnumEx**](/windows/win32/mfapi/nf-mfapi-mftenumex?branch=master)
</dt> </dl>

 

 



