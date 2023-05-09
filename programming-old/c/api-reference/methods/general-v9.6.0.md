---
layout: default-layout
title: General Functions - Dynamsoft Barcode Reader SDK C Edition API Reference
description: This page shows the general functions of Dynamsoft Barcode Reader SDK C Edition.
keywords: DBR_GetErrorString, DBR_GetVersion, general functions, api reference, c
needAutoGenerateSidebar: true
permalink: /programming/c/api-reference/methods/general-v9.6.0.html
---

# General Functions

  | Function               | Description |
  |----------------------|-------------|
  | [`DBR_GetErrorString`](#dbr_geterrorstring) | Get error message by error code. |
  | [`DBR_GetVersion`](#dbr_getversion) | Get version information of SDK. |
  | [`DBR_TransformCoordinates`](#dbr_transformcoordinates) | Transform the coordinate based on the given transformation matrix. |

## DBR_GetErrorString

Get error message by error code.

```c
DBR_API const char* DBR_GetErrorString (int errorCode)	
```   
   
**Parameters**  

`[in]	errorCode` The error code.
 

**Return Value**  

The error message.

**Code Snippet**  

```c
char errorBuf[512];
DBR_InitLicense("YOUR-LICENSE-KEY", errorBuf, 512);
void* barcodeReader = DBR_CreateInstance();
int errorCode = DBR_DecodeFile(barcodeReader, "C:\\Program Files (x86)\\Dynamsoft\\{Version number}\\Images\\AllSupportedBarcodeTypes.tif", "");
const char* errorString = DBR_GetErrorString(errorCode);
DBR_DestroyInstance(barcodeReader);
```



## DBR_GetVersion

Get version information of SDK.

```c
DBR_API const char* DBR_GetVersion ()
```   

**Return Value**  
The version information string.

**Code Snippet**  

```c
const char* versionInfo = DBR_GetVersion();
```

## DBR_TransformCoordinates

Transform the coordinates of a point based on the given transformation matrix.

```c
DBR_API DBRPoint DBR_TransformCoordinates(DBRPoint originalPoint, double transformationMatrix[9])
```

**Parameters**  

`[in] originalPoint` : The original point that needs to be transformed.  
`[in] transformationMatrix` : The 3x3 matrix used for coordinate transformation.

**Return Value**  

The point after transformation.

**Code Snippet**  

```c
//get originalPoint and transformationMatrix from LocalizationResult
DBRPoint targetPoint = DBR_TransformCoordinates(originalPoint, transformationMatrix);
```
