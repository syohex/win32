---
Description: Converts an array of 16-bit floats to 32-bit floats.
ms.assetid: cabb2888-76e4-403b-99ab-f7d62478bf43
title: D3DXFloat16To32Array function
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# D3DXFloat16To32Array function

Converts an array of 16-bit floats to 32-bit floats.

## Syntax


```C++
FLOAT* D3DXFloat16To32Array(
  _Inout_       FLOAT       *pOut,
  _In_    const D3DXFLOAT16 *pIn,
  _In_          UINT        n
);
```



## Parameters

<dl> <dt>

*pOut* \[in, out\]
</dt> <dd>

Type: **[**FLOAT**](winprog.windows_data_types)\***

Pointer to the array of 32-bit floats.

</dd> <dt>

*pIn* \[in\]
</dt> <dd>

Type: **const [**D3DXFLOAT16**](d3dxfloat16.md)\***

Pointer to an array of 16-bit floats.

</dd> <dt>

*n* \[in\]
</dt> <dd>

Type: **[**UINT**](winprog.windows_data_types)**

Number of elements in the array.

</dd> </dl>

## Return value

Type: **[**FLOAT**](winprog.windows_data_types)\***

Pointer to an array of 32-bit floats.

## Requirements



|                    |                                                                                        |
|--------------------|----------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>D3dx9math.h</dt> </dl> |
| Library<br/> | <dl> <dt>D3dx9.lib</dt> </dl>   |



## See also

<dl> <dt>

[Math Functions](dx9-graphics-reference-d3dx-functions-math.md)
</dt> </dl>

 

 



