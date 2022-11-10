---
layout: default-layout
title: Dynamsoft Barcode Reader C++ API Reference - CBarcodeReader Status Retrieval Methods
description: This page shows CBarcodeReader status retrieval methods of Dynamsoft Barcode Reader for C++ Language.
keywords: GetErrorString, GetVersion, status retrieval methods, CBarcodeReader, api reference, c++
needAutoGenerateSidebar: true
---

# Status Retrieval Methods

  | Method               | Description |
  |----------------------|-------------|
  | [`GetErrorString`](#geterrorstring) | Get error message by error code.|
  | [`GetVersion`](#getversion) | Get version information of SDK.|
  | [`TransformCoordinates`](#transformcoordinates) | Transform the coordinates of a point based on the given transformation matrix. |

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

## TransformCoordinates

Transform the coordinates of a point based on the given transformation matrix.

```cpp
static DBRPoint dynamsoft::dbr::CBarcodeReader::TransformCoordinates(DBRPoint originalPoint, double transformationMatrix[9])
```

**Parameters**  

`[in] originalPoint` : The original point that needs to be transformed.
`[in] transformationMatrix` : The 3x3 matrix used for coordinate transformation.

**Return Value**  

The point after transformation.

**Code Snippet**  

```cpp
//get originalPoint and transformationMatrix from LocalizationResult
DBRPoint targetPoint = CBarcodeReader::TransformCoordinates(originalPoint, transformationMatrix);
```
