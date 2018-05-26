---
Description: Closes the specified shim database.
ms.assetid: e4480860-8055-4134-b6ed-926c010d462f
title: SdbCloseDatabase function
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# SdbCloseDatabase function

Closes the specified shim database.

## Syntax


```C++
void WINAPI SdbCloseDatabase(
  _Inout_ PDB pdb
);
```



## Parameters

<dl> <dt>

*pdb* \[in, out\]
</dt> <dd>

A handle to the shim database. This parameter cannot be **NULL**.

</dd> </dl>

## Return value

This function does not return a value.

## Requirements



|                                     |                                                                                        |
|-------------------------------------|----------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows Vista \[desktop apps only\]<br/>                                         |
| Minimum supported server<br/> | Windows Server 2008 \[desktop apps only\]<br/>                                   |
| DLL<br/>                      | <dl> <dt>Apphelp.dll</dt> </dl> |



## See also

<dl> <dt>

[**SdbOpenDatabase**](sdbopendatabase.md)
</dt> </dl>

 

 



