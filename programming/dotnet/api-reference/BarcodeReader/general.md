---
layout: default-layout
title: Dynamsoft Barcode Reader .NET API Reference - BarcodeReader General Methods
description: This page shows BarcodeReader general methods of Dynamsoft Barcode Reader for .NET SDK.
keywords: GetVersion, general methods, BarcodeReader, api reference, .Net
needAutoGenerateSidebar: true
---

# General Methods

  | Method               | Description |
  |----------------------|-------------|
  | [`GetVersion`](#getversion) | Get version information of SDK.|
  | [`TransformCoordinates`](#transformcoordinates) | Transform the coordinates of a point based on the given transformation matrix. |

## GetVersion

Get version information of SDK.

```csharp
string Dynamsoft.DBR.BarcodeReader.GetVersion()
```

**Return Value**  
The version info string. 

**Code Snippet**  
```csharp
BarcodeReader reader = new BarcodeReader();
string version = reader.GetVersion();
```

## TransformCoordinates

Transform the coordinates of a point based on the given transformation matrix.

```csharp
static Point Dynamsoft.DBR.BarcodeReader.TransformCoordinates(Point originalPoint, double[] transformationMatrix)
```

**Parameters**  

`[in] originalPoint` : The original point that needs to be transformed.
`[in] transformationMatrix` : The 3x3 matrix used for coordinate transformation.

**Return Value**  

The point after transformation.

**Code Snippet**  

```csharp
//get originalPoint and transformationMatrix from LocalizationResult
Point targetPoint = BarcodeReader.TransformCoordinates(originalPoint, transformationMatrix);
```
