---
layout: default-layout
title: BarcodeReader General Methods - Dynamsoft Barcode Reader SDK Java Edition API Reference
description: This page shows BarcodeReader general methods of Dynamsoft Barcode Reader SDK Java Edition API Reference.
keywords: getVersion, general methods, BarcodeReader, api reference, java
needAutoGenerateSidebar: true
---

# General Methods

  | Method               | Description |
  |----------------------|-------------|
  | [`getVersion`](#getversion) | Get version information of SDK.|
  | [`transformCoordinates`](#transformcoordinates) | Transform the coordinates of a point based on the given transformation matrix. |

## getVersion

Get version information of SDK.

```java
String com.dynamsoft.dbr.BarcodeReader.getVersion()	
```

**Return Value**  
The version information string.

**Code Snippet**  
```java
BarcodeReader.initLicense("YOUR-LICENSE-KEY");
BarcodeReader reader = new BarcodeReader();
String versionInfo = reader.getVersion();
reader.destroy();
```

## TransformCoordinates

Transform the coordinates of a point based on the given transformation matrix.

```java
static Point com.dynamsoft.dbr.BarcodeReader.transformCoordinates(Point originalPoint, double[] transformationMatrix) throws BarcodeReaderException
```

**Parameters**  

`[in] originalPoint` : The original point that needs to be transformed.  
`[in] transformationMatrix` : The 3x3 matrix used for coordinate transformation.

**Return Value**  

The point after transformation.

**Exception**  
[`BarcodeReaderException`](../class/BarcodeReaderException.md)

**Code Snippet**  

```java
//get originalPoint and transformationMatrix from LocalizationResult
Point targetPoint = BarcodeReader.transformCoordinates(originalPoint, transformationMatrix);
```
