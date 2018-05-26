---
title: ID3DX11EffectSamplerVariable GetSampler method
description: Get a pointer to a sampler interface.
ms.assetid: ac2a05f1-e3ca-4ebf-b655-34133c4e50ac
keywords:
- GetSampler method Direct3D 11
- GetSampler method Direct3D 11 , ID3DX11EffectSamplerVariable interface
- ID3DX11EffectSamplerVariable interface Direct3D 11 , GetSampler method
topic_type:
- apiref
api_name:
- ID3DX11EffectSamplerVariable.GetSampler
api_location:
- N/A
- N/A.dll
api_type:
- COM
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# ID3DX11EffectSamplerVariable::GetSampler method

Get a pointer to a sampler interface.

## Syntax


```C++
HRESULT GetSampler(
   UINT               Index,
   ID3D11SamplerState **ppSampler
);
```



## Parameters

<dl> <dt>

*Index* 
</dt> <dd>

Type: **[**UINT**](https://msdn.microsoft.com/library/windows/desktop/aa383751)**

Index into an array of sampler interfaces. If there is only one sampler interface, use 0.

</dd> <dt>

*ppSampler* 
</dt> <dd>

Type: **[**ID3D11SamplerState**](/windows/win32/D3D11/nn-d3d11-id3d11samplerstate?branch=master)\*\***

The address of a pointer to a sampler interface (see [**ID3D11SamplerState**](/windows/win32/D3D11/nn-d3d11-id3d11samplerstate?branch=master)).

</dd> </dl>

## Return value

Type: **[**HRESULT**](455d07e9-52c3-4efb-a9dc-2955cbfd38cc)**

Returns one of the following [Direct3D 11 Return Codes](d3d11-graphics-reference-returnvalues.md).

## Remarks

> [!Note]  
> The DirectX SDK does not supply any compiled binaries for effects. You must use Effects 11 source to build your effects-type application. For more information about using Effects 11 source, see [Differences Between Effects 10 and Effects 11](d3d11-graphics-programming-guide-effects-differences.md).

 

## Requirements



|                    |                                                                                                                                              |
|--------------------|----------------------------------------------------------------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>D3dx11effect.h</dt> </dl>                                                    |
| Library<br/> | <dl> <dt>N/A (An Effects 11 library is available online as shared source.)</dt> </dl> |



## See also

<dl> <dt>

[ID3DX11EffectSamplerVariable](id3dx11effectsamplervariable.md)
</dt> </dl>

 

 




