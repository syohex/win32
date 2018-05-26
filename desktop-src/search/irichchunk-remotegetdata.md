---
Description: Retrieves the PROPVARIANT and input string that represents a chunk of data. Calling this method is the same as calling GetData.
ms.assetid: 78846D1D-923F-4FEA-8BF2-B16BB1B21BB3
title: IRichChunkRemoteGetData method
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# IRichChunk::RemoteGetData method

Retrieves the [PROPVARIANT](http://msdn.microsoft.com/en-us/library/Aa380072(VS.85).aspx) and input string that represents a chunk of data. Calling this method is the same as calling [**GetData**](/windows/win32/StructuredQueryCondition/nf-structuredquerycondition-irichchunk-getdata?branch=master).

## Syntax


```C++
HRESULT RemoteGetData(
  [out] ULONG       *pFirstPos,
  [out] ULONG       *pLength,
  [out] LPWSTR      *ppsz,
  [out] PROPVARIANT *pValue
);
```



## Parameters

<dl> <dt>

*pFirstPos* \[out\]
</dt> <dd>

Receives the zero-based starting position of the range. This parameter can be **NULL**.

</dd> <dt>

*pLength* \[out\]
</dt> <dd>

Receives the length of the range. This parameter can be **NULL**.

</dd> <dt>

*ppsz* \[out\]
</dt> <dd>

Receives the associated Unicode string value, or **NULL** if not available.

</dd> <dt>

*pValue* \[out\]
</dt> <dd>

Receives the associated [PROPVARIANT](http://msdn.microsoft.com/en-us/library/Aa380072(VS.85).aspx) value, or **VT\_EMPTY** if not available. This parameter can be **NULL**.

</dd> </dl>

## Return value

If this method succeeds, it returns **S\_OK**. Otherwise, it returns an **HRESULT** error code.

## See also

<dl> <dt>

[**IRichChunk**](/windows/win32/Structuredquerycondition/nn-structuredquerycondition-irichchunk?branch=master)
</dt> </dl>

 

 


