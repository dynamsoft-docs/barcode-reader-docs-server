---
layout: default-layout
title: CBarcodeReader General Methods - Dynamsoft Barcode Reader SDK C++ Edition API Reference
description: This page shows CBarcodeReader general methods of Dynamsoft Barcode Reader SDK C++ Edition.
keywords: GetErrorString, GetVersion, general methods, CBarcodeReader, api reference, c++
needAutoGenerateSidebar: true
permalink: /programming/cplusplus/api-reference/cbarcodereader-methods/general-v7.6.0.html
---

# C++ API Reference - CBarcodeReader General Methods

  | Method               | Description |
  |----------------------|-------------|
  | [`GetErrorString`](#geterrorstring) | Get error message by error code.|
  | [`GetVersion`](#getversion) | Get version information of SDK.|

  ---





  
## GetErrorString

Get error message by error code.

```cpp
static const char* CBarcodeReader::GetErrorString (const int iErrorCode)
```

#### Parameters
`[in] iErrorCode`	Error code.

#### Return value
The error message.

#### Code Snippet
```cpp
CBarcodeReader* reader = new CBarcodeReader();
reader->InitLicense("t0260NwAAAHV***************");
int errorCode = reader->DecodeFile("C:\\Program Files (x86)\\Dynamsoft\\{Version number}\\Images\\AllSupportedBarcodeTypes.tif", "");
const char* errorString = CBarcodeReader::GetErrorString(errorCode);
delete reader;
```







## GetVersion

Get version information of SDK.

```cpp
static const char* CBarcodeReader::GetVersion ()
```

#### Return value
The version information string.

#### Code Snippet
```cpp
const char* versionInfo = CBarcodeReader::GetVersion();
```
