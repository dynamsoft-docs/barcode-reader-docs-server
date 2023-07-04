---
layout: default-layout
title: CBarcodeReader General Methods - Dynamsoft Barcode Reader SDK C++ Edition API Reference
description: This page shows CBarcodeReader general methods of Dynamsoft Barcode Reader SDK C++ Edition.
keywords: GetErrorString, GetVersion, general methods, CBarcodeReader, api reference, c++
needAutoGenerateSidebar: true
permalink: /programming/cplusplus/api-reference/cbarcodereader-methods/general-v9.4.0.html
---

# General Methods

  | Method               | Description |
  |----------------------|-------------|
  | [`GetErrorString`](#geterrorstring) | Get error message by error code.|
  | [`GetVersion`](#getversion) | Get version information of SDK.|






  
## GetErrorString

Get error message by error code.

```cpp
static const char* dynamsoft::dbr::CBarcodeReader::GetErrorString (const int iErrorCode)
```

**Parameters**  
`[in] iErrorCode`	Error code.

**Return Value**  
The error message.

**Code Snippet**  
```cpp
char errorBuf[512];
dynamsoft::dbr::CBarcodeReader::InitLicense("YOUR-LICENSE-KEY", errorBuf, 512);
CBarcodeReader* reader = new CBarcodeReader();
int errorCode = reader->DecodeFile("C:\\Program Files (x86)\\Dynamsoft\\{Version number}\\Images\\AllSupportedBarcodeTypes.tif", "");
const char* errorString = dynamsoft::dbr::CBarcodeReader::GetErrorString(errorCode);
delete reader;
```







## GetVersion

Get version information of SDK.

```cpp
static const char* dynamsoft::dbr::CBarcodeReader::GetVersion ()
```

**Return Value**  
The version information string.

**Code Snippet**  
```cpp
const char* versionInfo = dynamsoft::dbr::CBarcodeReader::GetVersion();
```
