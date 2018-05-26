---
Description: The Metafile class, which inherits from the Image class, allows you to record a sequence of drawing commands.
ms.assetid: 062de6c2-9f82-415d-860e-2d1afd2ac027
title: Recording Metafiles
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Recording Metafiles

The [**Metafile**](/windows/win32/gdiplusheaders/nl-gdiplusheaders-metafile?branch=master) class, which inherits from the [**Image**](/windows/win32/gdiplusheaders/nl-gdiplusheaders-image?branch=master) class, allows you to record a sequence of drawing commands. The recorded commands can be stored in memory, saved to a file, or saved to a stream. Metafiles can contain vector graphics, raster images, and text.

The following example creates a [**Metafile**](/windows/win32/gdiplusheaders/nl-gdiplusheaders-metafile?branch=master) object. The code uses the **Metafile** object to record a sequence of graphics commands and then saves the recorded commands in a file named SampleMetafile.emf. Note that the **Metafile** constructor receives a device context handle, and the [**Graphics**](/windows/win32/gdiplusgraphics/nl-gdiplusgraphics-graphics?branch=master) constructor receives the address of the **Metafile** object. The recording stops (and the recorded commands are saved to the file) when the **Graphics** object goes out of scope. The last two lines of code display the metafile by creating a new **Graphics** object and passing the address of the **Metafile** object to the **DrawImage** method of that **Graphics** object. Note that the code uses the same **Metafile** object to record and to display (play back) the metafile.


```
Metafile metafile(L"SampleMetafile.emf", hdc); 
{
   Graphics graphics(&amp;metafile);
   Pen greenPen(Color(255, 0, 255, 0));
   SolidBrush solidBrush(Color(255, 0, 0, 255));

   // Add a rectangle and an ellipse to the metafile.
   graphics.DrawRectangle(&amp;greenPen, Rect(50, 10, 25, 75));
   graphics.DrawEllipse(&amp;greenPen, Rect(100, 10, 25, 75));

   // Add an ellipse (drawn with antialiasing) to the metafile.
   graphics.SetSmoothingMode(SmoothingModeHighQuality);
   graphics.DrawEllipse(&amp;greenPen, Rect(150, 10, 25, 75));

   // Add some text (drawn with antialiasing) to the metafile.
   FontFamily fontFamily(L"Arial");
   Font font(&amp;fontFamily, 24, FontStyleRegular, UnitPixel);
   
   graphics.SetTextRenderingHint(TextRenderingHintAntiAlias);
   graphics.RotateTransform(30.0f);
   graphics.DrawString(L"Smooth Text", 11, &amp;font, 
      PointF(50.0f, 50.0f), &amp;solidBrush);
} // End of recording metafile.

// Play back the metafile.
Graphics playbackGraphics(hdc);
playbackGraphics.DrawImage(&amp;metafile, 200, 100);
```



> [!Note]  
> To record a metafile, you must construct a [**Graphics**](/windows/win32/gdiplusgraphics/nl-gdiplusgraphics-graphics?branch=master) object based on a [**Metafile**](/windows/win32/gdiplusheaders/nl-gdiplusheaders-metafile?branch=master) object. The recording of the metafile ends when that **Graphics** object is deleted or goes out of scope.

 

A metafile contains its own graphics state, which is defined by the [**Graphics**](/windows/win32/gdiplusgraphics/nl-gdiplusgraphics-graphics?branch=master) object used to record the metafile. Any properties of the **Graphics** object (clip region, world transformation, smoothing mode, and the like) that you set while recording the metafile will be stored in the metafile. When you display the metafile, the drawing will be done according to those stored properties.

In the following example, assume that the smoothing mode was set to SmoothingModeNormal during the recording of the metafile. Even though the smoothing mode of the [**Graphics**](/windows/win32/gdiplusgraphics/nl-gdiplusgraphics-graphics?branch=master) object used for playback is set to SmoothingModeHighQuality, the metafile will be played according to the SmoothingModeNormal setting. It is the smoothing mode set during the recording that is important, not the smoothing mode set prior to playback.


```
graphics.SetSmoothingMode(SmoothingModeHighQuality);
graphics.DrawImage(&amp;meta, 0, 0);
```



 

 


