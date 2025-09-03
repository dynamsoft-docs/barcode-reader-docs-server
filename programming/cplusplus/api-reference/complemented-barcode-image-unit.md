---
layout: default-layout
title: CComplementedBarcodeImageUnit Class - Dynamsoft Barcode Reader C++ Edition API Reference
description: This page shows CComplementedBarcodeImageUnit class definition of Dynamsoft Barcode Reader SDK C++ Edition.
keywords: GetImageData, GetLocation, SetLocation, CComplementedBarcodeImageUnit, api reference
---
# CComplementedBarcodeImageUnit Class
The `CComplementedBarcodeImageUnit` class represents a unit that contains complemented barcode image data. It inherits from the `CIntermediateResultUnit` class.

## Definition

*Namespace:* dynamsoft::dbr::intermediate_results

*Assembly:* DynamsoftBarcodeReader

*Inheritance:* [CIntermediateResultUnit]({{ site.dcvb_cpp_api }}core/intermediate-results/intermediate-result-unit.html) -> CComplementedBarcodeImageUnit

```cpp
class CComplementedBarcodeImageUnit: public CIntermediateResultUnit
```

## Methods

| Method                            | Description |
|-----------------------------------|-------------|
| [`GetImageData`](#getimagedata) | Gets the complemented barcode image data.|
| [`GetLocation`](#getlocation) | Gets the location of the complemented barcode in a quadrilateral.|
| [`SetLocation`](#setlocation) | Sets the location of the complemented barcode in a quadrilateral.|

### Inherited Methods

{%- include inherited-methods/intermediate-result-unit.md -%}

### GetImageData

Gets the complemented barcode image data.

```cpp
virtual const CImageData* GetImageData() const = 0;
```

**Return value**

Returns a pointer to the complemented image of the barcode.

**See Also**

[CImageData]({{ site.dcvb_cpp_api }}core/basic-structures/image-data.html)

### GetLocation

Gets the location of the complemented barcode in a quadrilateral.

```cpp
virtual CQuadrilateral GetLocation() const = 0;
```

**Return value**

Returns the location of the complemented barcode in a quadrilateral.

**See Also**

[CQuadrilateral]({{ site.dcvb_cpp_api }}core/basic-structures/quadrilateral.html)

### SetLocation

Sets the location of the complemented barcode in a quadrilateral.

```cpp
virtual int SetLocation(const CQuadrilateral& location, const double matrixToOriginalImage[9] = IDENTITY_MATRIX) = 0;
```

**Parameters**

`location` The location of the complemented barcode.

`matrixToOriginalImage` The matrix to original image.

**Return value**

Returns 0 if successful, otherwise returns a negative value.

**See Also**

[CQuadrilateral]({{ site.dcvb_cpp_api }}core/basic-structures/quadrilateral.html)

