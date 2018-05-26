---
Description: The Microsoft Peer Distribution service supports the following structures.
ms.assetid: 26badfe6-3a5a-4c2e-9ef1-534c2e8573d0
title: Peer Distribution API Structures
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Peer Distribution API Structures

The Microsoft Peer Distribution service supports the following structures.



| Structure                                                              | Description                                                                                                                                                                                                                                                                              |
|------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [**PEERDIST\_CLIENT\_BASIC\_INFO**](/windows/win32/peerdist/ns-peerdist-_peerdist_client_basic_info?branch=master)    | Indicates whether or not there are many clients simultaneously downloading the same content.                                                                                                                                                                                             |
| [**PEERDIST\_CONTENT\_TAG**](/windows/win32/peerdist/ns-peerdist-peerdist_content_tag_tag?branch=master)                 | Contains a client supplied tag which is an input value for [**PeerDistClientOpenContent**](/windows/win32/PeerDist/nf-peerdist-peerdistclientopencontent?branch=master). The tag is associated with the content segment and is used in content management APIs, like [**PeerDistClientFlushContent**](/windows/win32/PeerDist/nf-peerdist-peerdistclientflushcontent?branch=master). |
| [**PEERDIST\_PUBLICATION\_OPTIONS**](/windows/win32/peerdist/ns-peerdist-peerdist_publication_options_tag?branch=master) | Contains publication options, including the API version information and possible option flags.                                                                                                                                                                                           |
| [**PEER\_RETRIEVAL\_OPTIONS**](/windows/win32/peerdist/ns-peerdist-peerdist_retrieval_options_tag?branch=master)         | Contains version of the content information to retrieve.                                                                                                                                                                                                                                 |
| [**PEERDIST\_STATUS\_INFO**](/windows/win32/peerdist/ns-peerdist-peerdist_status_info_tag?branch=master)                 | Contains information about the current status and capabilities of the BranchCache service on the local computer.                                                                                                                                                                         |



 

## Related topics

<dl> <dt>

[Peer Distribution API Reference](peer-distribution-api-reference.md)
</dt> </dl>

 

 


