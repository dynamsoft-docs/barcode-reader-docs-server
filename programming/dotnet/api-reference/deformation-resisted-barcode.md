---
layout: default-layout
title: DeformationResistedBarcode Class - Dynamsoft Barcode Reader .NET Edition API Reference
description: This page shows DeformationResistedBarcode class definition of Dynamsoft Barcode Reader SDK .NET Edition.
keywords: GetLocation, SetLocation, GetFormat, SetFormat, GetImageData, SetImageData, DeformationResistedBarcode, api reference
---
# DeformationResistedBarcode Class

The `DeformationResistedBarcode` class represents a deformation resisted barcode.

## Definition

*Namespace:* Dynamsoft.DBR.intermediate_results


```csharp
class DeformationResistedBarcode
```

## Methods

| Method                            | Description |
|-----------------------------------|-------------|
| [`DeformationResistedBarcode`](#DeformationResistedBarcode-constructor)           | Constructs a `DeformationResistedBarcode` object. |
| [`GetFormat`](#getformat)           | Gets the format of the deformation resisted barcode. |
| [`SetFormat`](#setformat)           | Sets the format of the deformation resisted barcode. |
| [`GetImageData`](#getimagedata)           | Gets the deformation resisted barcode image. |
| [`SetImageData`](#setimagedata)           | Sets the deformation resisted barcode image. |
| [`GetLocation`](#getlocation)           | Gets the location of the deformation resisted barcode.|
| [`SetLocation`](#setlocation)           | Sets the location of the deformation resisted barcode.|


### DeformationResistedBarcode Constructor

Constructs a `DeformationResistedBarcode` object with the specified parameters.

```csharp
DeformationResistedBarcode();
DeformationResistedBarcode(ImageData img, Quadrilateral location, EnumBarcodeFormat format);
```

**Parameters**

`img` the deformation resisted barcode image.

`location` The location of the deformation resisted barcode.

`format` The format of the deformation resisted barcode.

### GetFormat

Gets the format of the deformation resisted barcode.

```csharp
EnumBarcodeFormat GetFormat()
```

**Return value**

Returns the format of the deformation resisted barcode.

**See Also**

[EnumBarcodeFormat]({{ site.dbr_dotnet_api }}enum-barcode-format.html)

### SetFormat

Sets the format of the deformation resisted barcode.

```csharp
void SetFormat(EnumBarcodeFormat format)
```

**Parameters**

`format` The format of the deformation resisted barcode.

**See Also**

[EnumBarcodeFormat]({{ site.dbr_dotnet_api }}enum-barcode-format.html)

### GetImageData

Gets the deformation resisted barcode image.

```csharp
ImageData GetImageData()
```

**Return value**

Returns the deformation resisted barcode image.

**See Also**

[ImageData]({{ site.dcvb_dotnet_api }}core/basic-classes/image-data.html)

### SetImageData

Sets the deformation resisted barcode image.

```csharp
void SetImageData(ImageData img)
```

**Parameters**

`img` the deformation resisted barcode image.

**See Also**

[ImageData]({{ site.dcvb_dotnet_api }}core/basic-classes/image-data.html)

### GetLocation

Gets the location of the deformation resisted barcode.

```csharp
Quadrilateral GetLocation()
```

**Return value**

Returns the location of the deformation resisted barcode.

**See Also**

[Quadrilateral]({{ site.dcvb_dotnet_api }}core/basic-classes/quadrilateral.html)

### SetLocation

Sets the location of the deformation resisted barcode.

```csharp
void SetLocation(Quadrilateral loc)
```

**Parameters**

`loc` The location of the deformation resisted barcode. 

**See Also**

[Quadrilateral]({{ site.dcvb_dotnet_api }}core/basic-classes/quadrilateral.html)

