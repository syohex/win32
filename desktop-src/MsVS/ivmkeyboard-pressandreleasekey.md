---
title: IVMKeyboard PressAndReleaseKey method
description: The PressAndReleaseKey method simulates the given key being pressed down and then released inside the virtual machine.
ms.assetid: 4fa9c343-0cdc-4139-b0e2-63d3ee78fb02
keywords:
- PressAndReleaseKey method Virtual Server
- PressAndReleaseKey method Virtual Server , IVMKeyboard interface
- IVMKeyboard interface Virtual Server , PressAndReleaseKey method
- PressAndReleaseKey method Virtual Server , VMKeyboard interface
- VMKeyboard interface Virtual Server , PressAndReleaseKey method
topic_type:
- apiref
api_name:
- IVMKeyboard.PressAndReleaseKey
- VMKeyboard.PressAndReleaseKey
api_location:
- VsComInterfaces.h
api_type:
- COM
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# IVMKeyboard::PressAndReleaseKey method

The **PressAndReleaseKey** method simulates the given key being pressed down and then released inside the virtual machine.

## Syntax


```C++
HRESULT PressAndReleaseKey(
  [in] BSTR key
);
```



## Parameters

<dl> <dt>

*key* \[in\]
</dt> <dd>

The key code for the key to be pressed and released inside the virtual machine.

</dd> </dl>

## Return value

This method can return one of these values.



| Return code                                                                                         | Description                                                                 |
|-----------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------|
| <dl> <dt> **S\_OK** </dt> </dl>              | The operation was successful.<br/>                                    |
| <dl> <dt> **E\_POINTER**</dt> </dl>          | The *key* parameter is **NULL**.<br/>                                 |
| <dl> <dt> **E\_INVALIDARG**</dt> </dl>       | The given text string is empty, or contains an invalid key code.<br/> |
| <dl> <dt> **DISP\_E\_EXCEPTION** </dt> </dl> | An unexpected error occurred.<br/>                                    |



 

## Requirements



|                     |                                                                                                   |
|---------------------|---------------------------------------------------------------------------------------------------|
| Product<br/>  | Microsoft Virtual Server 2005 onWindows Server 2003<br/>                                    |
| Download<br/> | Microsoft Virtual Server 2005 R2 SP1 Update onWindows Server 2008orWindows Server 2003<br/> |
| Header<br/>   | <dl> <dt>VsComInterfaces.h</dt> </dl>      |



## See also

<dl> <dt>

[**IVMKeyboard**](ivmkeyboard.md)
</dt> </dl>

 

 




