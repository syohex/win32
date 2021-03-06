---
description: The GetPrinterDriver2 function retrieves driver data for the specified printer. If the driver is not installed on the local computer, GetPrinterDriver2 installs it and displays any user interface to the specified window.
ms.assetid: 0d482d28-7668-4734-ba71-5b355c18ddec
title: GetPrinterDriver2 function (Winspool.h)
ms.topic: reference
ms.date: 05/31/2018
topic_type: 
- APIRef
- kbSyntax
api_name: 
- GetPrinterDriver2
- GetPrinterDriver2W
api_type: 
- DllExport
api_location: 
- Winspool.drv
---

# GetPrinterDriver2 function

The **GetPrinterDriver2** function retrieves driver data for the specified printer. If the driver is not installed on the local computer, **GetPrinterDriver2** installs it and displays any user interface to the specified window.

## Syntax


```C++
BOOL GetPrinterDriver2(
  _In_opt_ HWND    hWnd,
  _In_     HANDLE  hPrinter,
  _In_opt_ LPTSTR  pEnvironment,
  _In_     DWORD   Level,
  _Out_    LPBYTE  pDriverInfo,
  _In_     DWORD   cbBuf,
  _Out_    LPDWORD pcbNeeded
);
```



## Parameters

<dl> <dt>

*hWnd* \[in, optional\]
</dt> <dd>

A handle of the window that will be used as the parent window of any user interface, such as a dialog box, that the driver displays during installation. If the value of this parameter is **NULL**, the driver's user interface will still be displayed to the user during installation, but it will not have a parent window.

</dd> <dt>

*hPrinter* \[in\]
</dt> <dd>

A handle to the printer for which the driver data should be retrieved. Use the [**OpenPrinter**](openprinter.md) or [**AddPrinter**](addprinter.md) function to retrieve a printer handle.

</dd> <dt>

*pEnvironment* \[in, optional\]
</dt> <dd>

A pointer to a null-terminated string that specifies the environment (for example, Windows x86, Windows IA64, or Windows x64). If this parameter is **NULL**, the current environment of the calling application and client machine (not of the destination application and print server) is used.

</dd> <dt>

*Level* \[in\]
</dt> <dd>

The printer driver structure returned in the *pDriverInfo* buffer. This parameter can be one of the following values.



| Value                                                                                                | Meaning                                             |
|------------------------------------------------------------------------------------------------------|-----------------------------------------------------|
| <span id="1"></span><dl> <dt>**1**</dt> </dl> | [**DRIVER\_INFO\_1**](driver-info-1.md)<br/> |
| <span id="2"></span><dl> <dt>**2**</dt> </dl> | [**DRIVER\_INFO\_2**](driver-info-2.md)<br/> |
| <span id="3"></span><dl> <dt>**3**</dt> </dl> | [**DRIVER\_INFO\_3**](driver-info-3.md)<br/> |
| <span id="4"></span><dl> <dt>**4**</dt> </dl> | [**DRIVER\_INFO\_4**](driver-info-4.md)<br/> |
| <span id="5"></span><dl> <dt>**5**</dt> </dl> | [**DRIVER\_INFO\_5**](driver-info-5.md)<br/> |
| <span id="6"></span><dl> <dt>**6**</dt> </dl> | [**DRIVER\_INFO\_6**](driver-info-6.md)<br/> |
| <span id="8"></span><dl> <dt>**8**</dt> </dl> | [**DRIVER\_INFO\_8**](driver-info-8.md)<br/> |



 

</dd> <dt>

*pDriverInfo* \[out\]
</dt> <dd>

A pointer to a buffer that receives a structure containing information about the driver, as specified by *Level*. The buffer must be large enough to store the strings pointed to by the structure members.

To determine the required buffer size, call **GetPrinterDriver2** with *cbBuf* set to zero. **GetPrinterDriver2** fails, [**GetLastError**](/windows/desktop/api/errhandlingapi/nf-errhandlingapi-getlasterror) returns **ERROR\_INSUFFICIENT\_BUFFER**, and the *pcbNeeded* parameter returns the size, in bytes, of the buffer required to hold the array of structures and their data.

</dd> <dt>

*cbBuf* \[in\]
</dt> <dd>

The size, in bytes, of the array at which *pDriverInfo* points.

</dd> <dt>

*pcbNeeded* \[out\]
</dt> <dd>

A pointer to a value that receives the number of bytes copied if the function succeeds or the number of bytes required if *cbBuf* is too small.

</dd> </dl>

## Return value

If the function succeeds, the return value is a nonzero value.

If the function fails, the return value is zero. To get the return status, call [**GetLastError**](/windows/desktop/api/errhandlingapi/nf-errhandlingapi-getlasterror).

## Remarks

The [**DRIVER\_INFO\_2**](driver-info-2.md), [**DRIVER\_INFO\_3**](driver-info-3.md), [**DRIVER\_INFO\_4**](driver-info-4.md), [**DRIVER\_INFO\_5**](driver-info-5.md), [**DRIVER\_INFO\_6**](driver-info-6.md), and [**DRIVER\_INFO\_8**](driver-info-8.md) structures contain the file name or the full path and file name of the printer driver in the **pDriverPath** member. An application can use the path and file name to load a printer driver by calling the [**LoadLibrary**](/windows/desktop/api/libloaderapi/nf-libloaderapi-loadlibrarya) function and supplying the path and file name as the single argument.

The ANSI version of this function, **GetPrinterDriver2A** is not supported and returns **ERROR\_NOT\_SUPPORTED**.

## Requirements



| Requirement | Value |
|-------------------------------------|-----------------------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows Vista \[desktop apps only\]<br/>                                                            |
| Minimum supported server<br/> | Windows Server 2008 \[desktop apps only\]<br/>                                                      |
| Header<br/>                   | <dl> <dt>Winspool.h (include Windows.h)</dt> </dl> |
| Library<br/>                  | <dl> <dt>Winspool.lib</dt> </dl>                   |
| DLL<br/>                      | <dl> <dt>Winspool.drv</dt> </dl>                   |
| Unicode and ANSI names<br/>   | **GetPrinterDriver2W** (Unicode)<br/>                                                               |



## See also

<dl> <dt>

[Printing](printdocs-printing.md)
</dt> <dt>

[Print Spooler API Functions](printing-and-print-spooler-functions.md)
</dt> <dt>

[**AddPrinterDriver**](addprinterdriver.md)
</dt> <dt>

[**DRIVER\_INFO\_1**](driver-info-1.md)
</dt> <dt>

[**DRIVER\_INFO\_2**](driver-info-2.md)
</dt> <dt>

[**DRIVER\_INFO\_3**](driver-info-3.md)
</dt> <dt>

[**DRIVER\_INFO\_4**](driver-info-4.md)
</dt> <dt>

[**DRIVER\_INFO\_5**](driver-info-5.md)
</dt> <dt>

[**DRIVER\_INFO\_6**](driver-info-6.md)
</dt> <dt>

[**EnumPrinterDrivers**](enumprinterdrivers.md)
</dt> <dt>

[**GetPrinterDriver**](getprinterdriver.md)
</dt> <dt>

[**OpenPrinter**](openprinter.md)
</dt> </dl>

 

