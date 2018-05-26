---
Description: Proxy function for the SetColorContexts method.
ms.assetid: 985ae179-df59-42a0-9987-5dd863512e57
title: IWICBitmapFrameEncode\_SetColorContexts\_Proxy function
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# IWICBitmapFrameEncode\_SetColorContexts\_Proxy function

Proxy function for the [**SetColorContexts**](/windows/win32/Wincodec/nf-wincodec-iwicbitmapframeencode-setcolorcontexts?branch=master) method.

## Syntax


```C++
HRESULT IWICBitmapFrameEncode_SetColorContexts_Proxy(
  _In_ IWICBitmapFrameEncode *THIS_PTR,
  _In_ UINT                  cCount,
  _In_ IWICColorContext      **ppIColorContext
);
```



## Parameters

<dl> <dt>

*THIS\_PTR* \[in\]
</dt> <dd>

Type: **[**IWICBitmapFrameEncode**](/windows/win32/Wincodec/nn-wincodec-iwicbitmapframeencode?branch=master)\***

Pointer to this [**IWICBitmapFrameEncode**](/windows/win32/Wincodec/nn-wincodec-iwicbitmapframeencode?branch=master) object.

</dd> <dt>

*cCount* \[in\]
</dt> <dd>

Type: **UINT**

The number of [**IWICColorContext**](/windows/win32/Wincodec/nn-wincodec-iwiccolorcontext?branch=master) profiles to set.

</dd> <dt>

*ppIColorContext* \[in\]
</dt> <dd>

Type: **[**IWICColorContext**](/windows/win32/Wincodec/nn-wincodec-iwiccolorcontext?branch=master)\*\***

A pointer to an [**IWICColorContext**](/windows/win32/Wincodec/nn-wincodec-iwiccolorcontext?branch=master) pointer containing the color contexts profiles to set to the frame.

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



 

 



