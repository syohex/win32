---
title: On Attribute (Shadow)(VML)
description: On Attribute (Shadow)(VML)
ms.assetid: 234fe63e-8a4a-4067-9d05-a8990d1cee5c
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# On Attribute (Shadow)(VML)

This topic describes VML, a feature that is deprecated as of Windows Internet Explorer 9. Webpages and applications that rely on VML should be [migrated to SVG](http://go.microsoft.com/fwlink/p/?LinkID=236964) or other widely supported standards.

> [!Note]  
> As of December 2011, this topic has been archived. As a result, it is no longer actively maintained. For more information, see [Archived Content](https://msdn.microsoft.com/library/hh772377). For information, recommendations, and guidance regarding the current version of Windows Internet Explorer, see [Internet Explorer Developer Center](http://go.microsoft.com/fwlink/p/?linkid=204313).

 

Determines whether a shadow will be displayed. Read/write. **VgTriState**.

**Applies To**

[Shadow](msdn-online-vml-shadow-element.md)

**Tag Syntax**

&lt;v: *element* on=" *expression* "&gt;

**Script Syntax**

*element* .on="*expression*"

*expression*=*element*.on

**Remarks**

If **True**, the shadow will be displayed. The default value is **False**.

*VML Standard Attribute*

**Example**

The shadow will be displayed.


```HTML
   <v:shape id="rect01"
   coordorigin="0 0" coordsize="200 200"
   strokecolor="red" fillcolor="red"
   style="top:20;left:20;width:30;height:30"
   path="m 1,1 l 1,200, 200,200, 200,1 x e">
   <v:shadow on="True"/>
   </v:shape>
```



[Show Me](http://samples.msdn.microsoft.com/workshop/samples/vml/shape/shadow/x_shadow.md)

 

 



