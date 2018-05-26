---
Description: D3DXSHPRTSPLITMESHVERTDATA structure
ms.assetid: 8799a680-bf5f-42cc-91aa-1a6aed164ca5
title: D3DXSHPRTSPLITMESHVERTDATA structure
ms.date: 05/31/2018
ms.topic: structure
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# D3DXSHPRTSPLITMESHVERTDATA structure

## Syntax


```C++
typedef struct D3DXSHPRTSPLITMESHVERTDATA {
  UINT uVertRemap;
  UINT uSubCluster;
  UINT ucVertStatus;
} D3DXSHPRTSPLITMESHVERTDATA, *LPD3DXSHPRTSPLITMESHVERTDATA;
```



## Members

<dl> <dt>

**uVertRemap**
</dt> <dd>

Type: **[**UINT**](winprog.windows_data_types)**

</dd> <dd>

Vertex in original mesh this corresponds to.

</dd> <dt>

**uSubCluster**
</dt> <dd>

Type: **[**UINT**](winprog.windows_data_types)**

</dd> <dd>

Cluster index, relative to the supercluster.

</dd> <dt>

**ucVertStatus**
</dt> <dd>

Type: **[**UINT**](winprog.windows_data_types)**

</dd> <dd>

1 if vertex has valid data, 0 if it is "full".

</dd> </dl>

## Remarks

Allocated in [**D3DXSHPRTCompSplitMeshSC**](d3dxshprtcompsplitmeshsc.md).

## Requirements



|                   |                                                                                        |
|-------------------|----------------------------------------------------------------------------------------|
| Header<br/> | <dl> <dt>D3dx9mesh.h</dt> </dl> |



## See also

<dl> <dt>

[D3DX Structures](dx9-graphics-reference-d3dx-structures.md)
</dt> </dl>

 

 



