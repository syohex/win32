---
title: Stream Prioritization
description: Stream Prioritization
ms.assetid: 6b3e9b03-62ef-422b-97ab-197d1cd15beb
keywords:
- Windows Media Format SDK,stream prioritization
- Advanced Systems Format (ASF),stream prioritization
- ASF (Advanced Systems Format),stream prioritization
- Windows Media Format SDK,priority order for streams
- Advanced Systems Format (ASF),priority order for streams
- ASF (Advanced Systems Format),priority order for streams
- streams,prioritization
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Stream Prioritization

When you create an ASF file, you can specify a priority order for its constituent streams. If you stream a prioritized file and the available bandwidth is not enough to deliver all of the streams, the reader will drop streams in reverse priority order. In this way you can guarantee that the most important streams in your file will not be dropped due to network difficulties.

Stream prioritization is configured with a stream prioritization object and added to the profile. A profile can contain only one stream prioritization object.

## Related topics

<dl> <dt>

[**ASF File Features**](asf-file-features.md)
</dt> <dt>

[**IWMProfile3::CreateNewStreamPrioritization**](/windows/win32/Wmsdkidl/nf-wmsdkidl-iwmprofile3-createnewstreamprioritization?branch=master)
</dt> <dt>

[**IWMProfile3::GetStreamPrioritization**](/windows/win32/Wmsdkidl/nf-wmsdkidl-iwmprofile3-getstreamprioritization?branch=master)
</dt> <dt>

[**IWMProfile3::RemoveStreamPrioritization**](/windows/win32/Wmsdkidl/nf-wmsdkidl-iwmprofile3-removestreamprioritization?branch=master)
</dt> <dt>

[**IWMProfile3::SetStreamPrioritization**](/windows/win32/Wmsdkidl/nf-wmsdkidl-iwmprofile3-setstreamprioritization?branch=master)
</dt> <dt>

[**IWMStreamPrioritization Interface**](/windows/win32/wmsdkidl/nn-wmsdkidl-iwmstreamprioritization?branch=master)
</dt> <dt>

[**Using Stream Prioritization**](using-stream-prioritization.md)
</dt> </dl>

 

 



