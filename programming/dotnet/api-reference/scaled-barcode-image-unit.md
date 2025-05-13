---
layout: default-layout
title: ScaledBarcodeImageUnit Class - Dynamsoft Barcode Reader .NET Edition API Reference
description: This page shows ScaledBarcodeImageUnit class definition of Dynamsoft Barcode Reader SDK .NET Edition.
keywords: GetImageData, SetImageData, ScaledBarcodeImageUnit, api reference
---
# ScaledBarcodeImageUnit Class

The `ScaledBarcodeImageUnit` class represents a unit that contains scaled up barcode image. It inherits from the `IntermediateResultUnit` class.

## Definition

*Namespace:* Dynamsoft.DBR.intermediate_results


*Inheritance:* [IntermediateResultUnit]({{ site.dcvb_dotnet_api }}core/intermediate-results/intermediate-result-unit.html) -> ScaledBarcodeImageUnit

```csharp
class ScaledBarcodeImageUnit : IntermediateResultUnit
```

## Methods

| Method                            | Description |
|-----------------------------------|-------------|
| [`GetImageData`](#getimagedata)           | Gets the scaled up barcode image data.|
| [`SetImageData`](#setimagedata)           | Sets the scaled up image data.|

### Inherited Methods

Checkout inherited methods from [IntermediateResultUnit]({{ site.dcvb_dotnet_api }}core/intermediate-results/intermediate-result-unit.html) for more details.

### GetImageData

Gets the scaled up barcode image data.

```csharp
ImageData GetImageData()
```

**Return value**

Returns the scaled up image of the barcode.

**See Also**

[ImageData]({{ site.dcvb_dotnet_api }}core/basic-classes/image-data.html)

### SetImageData

Sets the scaled up image data.

```csharp
int SetImageData(ImageData imgData)
```

**Parameters**

`[in] imgData` The pointer to the scaled up image data.

**Return value**

Returns 0 if successful, otherwise returns a negative value.

**See Also**

[ImageData]({{ site.dcvb_dotnet_api }}core/basic-classes/image-data.html)
