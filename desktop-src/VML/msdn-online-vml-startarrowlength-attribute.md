---
title: VML StartArrowLength Attribute
description: VML StartArrowLength Attribute
ms.assetid: 7c108132-4f74-41cc-bfac-123f0259e6cb
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# VML StartArrowLength Attribute

This topic describes VML, a feature that is deprecated as of Windows Internet Explorer 9. Webpages and applications that rely on VML should be [migrated to SVG](http://go.microsoft.com/fwlink/p/?LinkID=236964) or other widely supported standards.

> [!Note]  
> As of December 2011, this topic has been archived. As a result, it is no longer actively maintained. For more information, see [Archived Content](https://msdn.microsoft.com/library/hh772377). For information, recommendations, and guidance regarding the current version of Windows Internet Explorer, see [Internet Explorer Developer Center](http://go.microsoft.com/fwlink/p/?linkid=204313).

 

Defines the arrowhead length for the start of a line. Read/write. **VgArrowheadLength**.

**Applies To**

[Stroke](msdn-online-vml-stroke-element.md)

**Tag Syntax**

&lt;v: *element* startarrowlength=" *expression* "&gt;

**Script Syntax**

*element* .startarrowlength="*expression*"

*expression*=*element*.startarrowlength

**Remarks**

Values include:

-   Short
-   Medium (default)
-   Long

VML Standard Attribute

**Example**

A line is drawn with a short classic arrowhead on the start of the stroke.


```HTML
   <v:line strokecolor="red"
   strokeweight="2pt" to="100pt,20pt" from="20pt,20pt">
   <v:stroke startarrow="classic" startarrowlength="short"/>
   </v:line>
```



 

 



