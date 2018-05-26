---
Description: LSA Policy provides several functions that you can use to create, enumerate, and delete trusted domains and to set and retrieve trusted domain information.
ms.assetid: 0c7534d7-3372-49c4-992c-9b519279982d
title: Managing Trusted Domain Information
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Managing Trusted Domain Information

LSA Policy provides several functions that you can use to create, enumerate, and delete trusted domains and to set and retrieve trusted domain information.

Before you can manage trusted domain information, your application must get a handle to a [**Policy**](policy-object.md) object, as explained in [Opening a Policy Object Handle](opening-a-policy-object-handle.md).

You can enumerate the trusted domains by calling [**LsaEnumerateTrustedDomainsEx**](/windows/win32/Ntsecapi/nf-ntsecapi-lsaenumeratetrusteddomainsex?branch=master).

To retrieve information about a trusted domain, call either [**LsaQueryTrustedDomainInfo**](/windows/win32/Ntsecapi/nf-ntsecapi-lsaquerytrusteddomaininfo?branch=master) or [**LsaQueryTrustedDomainInfoByName**](/windows/win32/Ntsecapi/nf-ntsecapi-lsaquerytrusteddomaininfobyname?branch=master). Both functions return the same information; however, **LsaQueryTrustedDomainInfo** identifies the trusted domain by SID, and **LsaQueryTrustedDomainInfoByName** identifies the trusted domain by name.

To set information for a trusted domain, call either [**LsaSetTrustedDomainInformation**](/windows/win32/Ntsecapi/nf-ntsecapi-lsasettrusteddomaininformation?branch=master) or [**LsaSetTrustedDomainInfoByName**](/windows/win32/Ntsecapi/nf-ntsecapi-lsasettrusteddomaininfobyname?branch=master). As with the query functions, **LsaSetTrustedDomainInformation** identifies the trusted domain by SID, while **LsaSetTrustedDomainInfoByName** identifies the trusted domain by name.

Your application can revoke a trust relationship for a trusted domain by calling [**LsaDeleteTrustedDomain**](/windows/win32/Ntsecapi/nf-ntsecapi-lsadeletetrusteddomain?branch=master).

The following example enumerates the trusted domains for the local system.


```C++
#include <windows.h>

void EnumerateTrusts(LSA_HANDLE PolicyHandle)
{
  LSA_ENUMERATION_HANDLE hEnum=0; 
  PLSA_TRUST_INFORMATION TrustInfo = NULL;
  ULONG ulReturned = 0;               
  NTSTATUS Status = 0;
  ULONG i;
  WCHAR StringBuffer[256];

  // Enumerate the trusted domains until there are no more to return.
  do 
  {
    Status = LsaEnumerateTrustedDomains(
       PolicyHandle,         // an open policy handle
       &amp;hEnum,               // enumeration tracker
       (PVOID*)&amp;TrustInfo,   // buffer to receive data
       32000,                // recommended buffer size
       &amp;ulReturned           // number of items returned in TrustInfo
    );

    // Check the return status for errors.
    if((Status != STATUS_SUCCESS) &amp;&amp;
       (Status != STATUS_MORE_ENTRIES) &amp;&amp;
     (Status != STATUS_NO_MORE_ENTRIES))
      {
        // Handle the error.
        wprintf(L"Error occurred enumerating domains %lu\n",
        LsaNtStatusToWinError(Status));
        return;
      } 

      wprintf(L"Status %lu\n", LsaNtStatusToWinError(Status));
      // Process the trusted domain information.
      for (i=0;i<ulReturned; i++) 
      {
        // LSA_Unicode strings might not be null-terminated.
        if(TrustInfo[i].Name.Length < 256)
        {
            wcsncpy_s(StringBuffer,
                256,
                TrustInfo[i].Name.Buffer,
                TrustInfo[i].Name.Length
            );
            // Guarantee that StringBuffer is null-terminated.
            StringBuffer[TrustInfo[i].Name.Length] = NULL; 
        }
        else
        {
            fprintf(stderr, "Name too long for string buffer.\n");
            exit(1);
        }
        
        wprintf(L"Enum Trusted Domain - %ws ", StringBuffer);
      }
      // Free the buffer.
      if (TrustInfo != NULL) 
      {
        LsaFreeMemory(TrustInfo);
        TrustInfo = NULL;
      }
    } while (Status != STATUS_NO_MORE_ENTRIES);
    return;
}
```



 

 


