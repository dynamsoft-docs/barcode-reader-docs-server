---
layout: default-layout
title: BarcodeReader General Methods - Dynamsoft Barcode Reader SDK .NET Edition API Reference
description: This page shows BarcodeReader general methods of Dynamsoft Barcode Reader SDK .NET Edition.
keywords: GetVersion, general methods, BarcodeReader, api reference, .Net
needAutoGenerateSidebar: true
permalink: /programming/dotnet/api-reference/BarcodeReader/general.html
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
BarcodeReader reader = BarcodeReader.GetInstance();
if (reader != null)
{
	string version = reader.GetVersion();
	//... add further process
    reader.Recycle();
}
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
