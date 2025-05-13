---
layout: default-layout
title: ComplementedBarcodeImageUnit Class - Dynamsoft Barcode Reader .NET Edition API Reference
description: This page shows ComplementedBarcodeImageUnit class definition of Dynamsoft Barcode Reader SDK .NET Edition.
keywords: GetImageData, GetLocation, SetLocation, ComplementedBarcodeImageUnit, api reference
---
# ComplementedBarcodeImageUnit Class

The `ComplementedBarcodeImageUnit` class represents a unit that contains complemented barcode image data. It inherits from the `IntermediateResultUnit` class.

## Definition

*Namespace:* Dynamsoft.DBR.intermediate_results


*Inheritance:* [IntermediateResultUnit]({{ site.dcvb_dotnet_api }}core/intermediate-results/intermediate-result-unit.html) -> ComplementedBarcodeImageUnit

```csharp
class ComplementedBarcodeImageUnit : IntermediateResultUnit
```

## Methods

| Method                            | Description |
|-----------------------------------|-------------|
| [`GetImageData`](#getimagedata) | Gets the complemented barcode image data.|
| [`GetLocation`](#getlocation) | Gets the location of the complemented barcode in a quadrilateral.|
| [`SetLocation`](#setlocation) | Sets the location of the complemented barcode in a quadrilateral.|

### Inherited Methods

Checkout inherited methods from [IntermediateResultUnit]({{ site.dcvb_dotnet_api }}core/intermediate-results/intermediate-result-unit.html) for more details.

### GetImageData

Gets the complemented barcode image data.

```csharp
ImageData GetImageData()
```

**Return value**

Returns the complemented image of the barcode.

**See Also**

[ImageData]({{ site.dcvb_dotnet_api }}core/basic-classes/image-data.html)

### GetLocation

Gets the location of the complemented barcode in a quadrilateral.

```csharp
Quadrilateral GetLocation()
```

**Return value**

Returns the location of the complemented barcode in a quadrilateral.

**See Also**

[Quadrilateral]({{ site.dcvb_dotnet_api }}core/basic-classes/quadrilateral.html)

### SetLocation

Sets the location of the complemented barcode in a quadrilateral.

```csharp
int SetLocation(Quadrilateral location, double[] matrixToOriginalImage = null)
```

**Parameters**

`location` The location of the complemented barcode.

`matrixToOriginalImage` The matrix to original image.

**Return value**

Returns 0 if successful, otherwise returns a negative value.

**See Also**

[Quadrilateral]({{ site.dcvb_dotnet_api }}core/basic-classes/quadrilateral.html)

