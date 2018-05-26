---
Description: Proxy function for the GetMimeTypes method.
ms.assetid: 9d05624f-da08-4475-933b-faa12bec9012
title: IWICBitmapCodecInfo\_GetMimeTypes\_Proxy function
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# IWICBitmapCodecInfo\_GetMimeTypes\_Proxy function

Proxy function for the [**GetMimeTypes**](/windows/win32/Wincodec/nf-wincodec-iwicbitmapcodecinfo-getmimetypes?branch=master) method.

## Syntax


```C++
HRESULT IWICBitmapCodecInfo_GetMimeTypes_Proxy(
  _In_  IWICBitmapCodecInfo *THIS_PTR,
  _In_  UINT                cchMimeTypes,
  _Out_ WCHAR               *wzMimeTypes,
  _Out_ UINT                *pcchActual
);
```



## Parameters

<dl> <dt>

*THIS\_PTR* \[in\]
</dt> <dd>

Type: **[**IWICBitmapCodecInfo**](/windows/win32/Wincodec/nn-wincodec-iwicbitmapcodecinfo?branch=master)\***

Pointer to this [**IWICBitmapCodecInfo**](/windows/win32/Wincodec/nn-wincodec-iwicbitmapcodecinfo?branch=master) object.

</dd> <dt>

*cchMimeTypes* \[in\]
</dt> <dd>

Type: **UINT**

The size of the mime types buffer.

</dd> <dt>

*wzMimeTypes* \[out\]
</dt> <dd>

Type: **WCHAR\***

A pointer that receives the mime types associated with the codec.

</dd> <dt>

*pcchActual* \[out\]
</dt> <dd>

Type: **UINT\***

The actual buffer size needed to retrieve all mime types associated with the codec.

</dd> </dl>

## Return value

Type: **HRESULT**

If this function succeeds, it returns **S\_OK**. Otherwise, it returns an **HRESULT** error code.

## Remarks

## Requirements



|                                     |                                                                                                                                                                  |
|-------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows XP with SP2, Windows Vista \[desktop apps only\]<br/>                                                                                              |
| Minimum supported server<br/> | Windows Server 2008 \[desktop apps only\]<br/>                                                                                                             |
| DLL<br/>                      | <dl> <dt>Windowscodecs.dll; </dt> <dt>Wincodec.lib</dt> </dl> |



 

 



