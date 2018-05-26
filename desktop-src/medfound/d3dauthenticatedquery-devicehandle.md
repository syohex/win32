---
Description: Returns a handle to the device that is associated with this authenticated channel.
ms.assetid: 948eac1a-640a-47fd-b538-1de3ea5d8f0b
title: D3DAUTHENTICATEDQUERY\_DEVICEHANDLE
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# D3DAUTHENTICATEDQUERY\_DEVICEHANDLE

Returns a handle to the device that is associated with this authenticated channel. You can use this handle to verify whether two authenticated channels are communicating with the same device.



|             |                                                                                                                |
|-------------|----------------------------------------------------------------------------------------------------------------|
| Query GUID  | **D3DAUTHENTICATEDQUERY\_DEVICEHANDLE**                                                                        |
| Input data  | [**D3DAUTHENTICATEDCHANNEL\_QUERY\_INPUT**](d3dauthenticatedchannel-query-input.md)                           |
| Return data | [**D3DAUTHENTICATEDCHANNEL\_QUERYDEVICEHANDLE\_OUTPUT**](d3dauthenticatedchannel-querydevicehandle-output.md) |



 

## Remarks

This query is valid for all channel types.

## Requirements



|                                     |                                                                                        |
|-------------------------------------|----------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows 7 \[desktop apps only\]<br/>                                             |
| Minimum supported server<br/> | Windows Server 2008 R2 \[desktop apps only\]<br/>                                |
| Header<br/>                   | <dl> <dt>D3d9types.h</dt> </dl> |



## See also

<dl> <dt>

[Content Protection Queries](content-protection-queries.md)
</dt> <dt>

[GPU-Based Content Protection](gpu-based-content-protection.md)
</dt> <dt>

[**IDirect3DAuthenticatedChannel9::Query**](/windows/win32/d3d9/nf-d3d9-idirect3dauthenticatedchannel9-query?branch=master)
</dt> </dl>

 

 



