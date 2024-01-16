---
layout: default-layout
title: CComplementedBarcodeImageUnit Class
description: This page shows CComplementedBarcodeImageUnit class definition of Dynamsoft Barcode Reader SDK C++ Edition.
keywords: GetImageData, CComplementedBarcodeImageUnit, api reference
---
# CComplementedBarcodeImageUnit Class
The `CComplementedBarcodeImageUnit` class represents a unit that contains complemented barcode image data. It inherits from the `CIntermediateResultUnit` class.

## Definition

*Namespace:* dynamsoft::dbr::intermediate_results

*Assembly:* DynamsoftBarcodeReader

*Inheritance:* [CIntermediateResultUnit]({{ site.dcv_cpp_api }}core/intermediate-results/intermediate-result-unit.html) -> CComplementedBarcodeImageUnit

```cpp
class CComplementedBarcodeImageUnit: public CIntermediateResultUnit
```

## Methods

| Method                            | Description |
|-----------------------------------|-------------|
| [`GetLocation`](#getlocation) | Get the location of the complemented barcode in a quadrilateral.|
| [`GetImageData`](#getimagedata) | Gets the complemented barcode image data.|

### Inherited Methods

{%- include inherited-methods/intermediate-result-unit-10.0.20.md -%}

### GetLocation

Get the location of the complemented barcode in a quadrilateral.

```cpp
virtual CQuadrilateral GetLocation() const = 0;
```

**Return value**

Returns the location of the complemented barcode in a quadrilateral.

**See Also**

[CQuadrilateral]({{ site.dcv_cpp_api }}core/basic-structures/quadrilateral.html)

### GetImageData

Gets the complemented barcode image data.

```cpp
virtual const CImageData* GetImageData() const = 0;
```

**Return value**

Returns a pointer to the complemented image of the barcode.

**See Also**

[CImageData]({{ site.dcv_cpp_api }}core/basic-structures/image-data.html)
