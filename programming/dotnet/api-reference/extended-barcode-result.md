---
layout: default-layout
title: ExtendedBarcodeResult Class - Dynamsoft Barcode Reader .NET Edition API Reference
description: This page shows ExtendedBarcodeResult class definition of Dynamsoft Barcode Reader SDK .NET Edition.
keywords: GetDeformation, GetClarity, GetSamplingImage, GetExtendedBarcodeResultType, ExtendedBarcodeResult, api reference
---
# ExtendedBarcodeResult Class

The `ExtendedBarcodeResult` class represents an extended barcode result in a decoded barcode element. It contains information such as the type of extended barcode, deformation, clarity, and a sampling image of the barcode.

## Definition

*Namespace:* Dynamsoft.DBR


*Inheritance:* [DecodedBarcodeElement]({{ site.dbr_dotnet_api }}decoded-barcode-element.html) -> ExtendedBarcodeResult

```csharp
class ExtendedBarcodeResult : DecodedBarcodeElement
```

## Methods

| Method | Description |
|--------|-------------|
| [`GetExtendedBarcodeResultType`](#getextendedbarcoderesulttype) | Gets the type of extended barcode result. |
| [`GetDeformation`](#getdeformation) | Gets the deformation of the barcode. |
| [`GetClarity`](#getclarity) | Gets the clarity of the barcode. |
| [`GetSamplingImage`](#getsamplingimage) | Gets the sampling image of the barcode. |

### GetExtendedBarcodeResultType

Gets the type of extended barcode result.

```csharp
EnumExtendedBarcodeResultType GetExtendedBarcodeResultType()
```

**Return value**

Returns the type of the extended barcode result.

**See Also**

[EnumExtendedBarcodeResultType]({{ site.dbr_dotnet_api }}enum-extended-barcode-result-type.html)

### GetDeformation

Gets the deformation of the barcode.

```csharp
int GetDeformation()
```

**Return value**

Returns the deformation of the barcode.

### GetClarity

Gets the clarity of the barcode.

```csharp
int GetClarity()
```

**Return value**

Returns the clarity of the barcode.

### GetSamplingImage

Gets the sampling image of the barcode.

```csharp
ImageData GetSamplingImage()
```

**Return value**

Returns the sampling image of the barcode.

**See Also**

[ImageData]({{ site.dcvb_dotnet_api }}core/basic-classes/image-data.html)
