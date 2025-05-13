---
layout: default-layout
title: DecodedBarcodesResult Class - Dynamsoft Barcode Reader Module .NET Edition API Reference
description: Definition of DecodedBarcodesResult class in Dynamsoft Barcode Reader Module .NET Edition.
keywords: GetOriginalImageHashId, GetItemsCount, GetErrorCode, DecodedBarcodesResult, api reference
---
# DecodedBarcodesResult Class

The `DecodedBarcodesResult` class represents the result of a barcode reading process. It provides access to information about the decoded barcodes, the source image, and any errors that occurred during the barcode reading process.

## Definition

*Namespace:* Dynamsoft.DBR


```csharp
public class DecodedBarcodesResult
```

## Methods

| Method               | Description |
|----------------------|-------------|
| [`GetErrorCode`](#geterrorcode) | Gets the error code of the barcode reading result, if an error occurred. |
| [`GetErrorString`](#geterrorstring) | Gets the error message of the barcode reading result, if an error occurred. |
| [`GetItems`](#getitems) | Gets all the barcode result items. |
| [`GetOriginalImageHashId`](#getoriginalimagehashid) | Gets the hash ID of the source image. |
| [`GetOriginalImageTag`](#getoriginalimagetag) | Gets the tag of the source image. |
| [`GetRotationTransformMatrix`](#getrotationtransformmatrix) | Gets the 3x3 rotation transformation matrix of the original image relative to the rotated image.|

### GetErrorCode

Gets the error code of the barcode reading result, if an error occurred.

```csharp
int GetErrorCode()
```

**Return Value**

Returns the error code of the barcode reading result, or 0 if no error occurred.

**See Also**

[EnumErrorCode]({{ site.dcvb_dotnet_api }}core/enum-error-code.html)

### GetErrorString

Gets the error message of the barcode reading result, if an error occurred.

```csharp
string GetErrorString()
```

**Return Value**

Returns a string containing the error message of the barcode reading result, or an empty string if no error occurred.

### GetItems

Gets all the decoded barcode result items.

```csharp
BarcodeResultItem[] GetItems()
```

**Return Value**

Returns a `BarcodeResultItem` array.

**See Also**

[BarcodeResultItem]({{ site.dbr_dotnet_api }}barcode-result-item.html)

### GetOriginalImageHashId

Gets the hash ID of the source image.

```csharp
string GetOriginalImageHashId()
```

**Return Value**

Returns a string containing the hash ID of the source image.

### GetOriginalImageTag

Gets the tag of the source image.

```csharp
ImageTag GetOriginalImageTag()
```

**Return Value**

Returns an `ImageTag` object representing the tag of the source image.

**See Also**

[ImageTag]({{ site.dcvb_dotnet_api }}core/basic-classes/image-tag.html)

### GetRotationTransformMatrix

Gets the 3x3 rotation transformation matrix of the original image relative to the rotated image.

```csharp
double[] GetRotationTransformMatrix()
```

**Return Value**

Returns a double array of length 9 which represents a 3x3 rotation matrix.
