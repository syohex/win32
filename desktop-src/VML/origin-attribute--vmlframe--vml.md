---
title: Origin Attribute (VMLFrame)(VML)
description: Origin Attribute (VMLFrame)(VML)
ms.assetid: 317c027e-5054-4543-ad98-2c21d1cf7154
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Origin Attribute (VMLFrame)(VML)

This topic describes VML, a feature that is deprecated as of Windows Internet Explorer 9. Webpages and applications that rely on VML should be [migrated to SVG](http://go.microsoft.com/fwlink/p/?LinkID=236964) or other widely supported standards.

> [!Note]  
> As of December 2011, this topic has been archived. As a result, it is no longer actively maintained. For more information, see [Archived Content](https://msdn.microsoft.com/library/hh772377). For information, recommendations, and guidance regarding the current version of Windows Internet Explorer, see [Internet Explorer Developer Center](http://go.microsoft.com/fwlink/p/?linkid=204313).

 

Defines the origin of the clipping region of the frame. Read/write. **VgVector2D**.

**Applies To**

[VMLFrame](msdn-online-vml-vmlframe-element.md)

**Tag Syntax**

&lt;v: *element* origin=" *expression* "&gt;

**Script Syntax**

*element* .origin="*expression*"

*expression*=*element*.origin

**Remarks**

The default value is 0,0. Note that **Origin** only works if [Clip](msdn-online-vml-clip-attribute.md) is **True**. In this attribute, the origin is defined as the upper left corner of the frame.

*VML Standard Attribute*

**Example**

The origin of the clipping region is 100pt,100pt.


```HTML
   <v:vmlframe id="frame01" clip="True"
   origin="100pt,100pt" size="50pt,50pt"
   src="external.vml#shape01"
   style='top:160pt; left:100pt; width:50pt; height:50pt'
   </v:vmlframe>
```



 

 



