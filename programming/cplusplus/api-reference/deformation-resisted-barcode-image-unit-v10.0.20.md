---
layout: default-layout
title: CDeformationResistedBarcodeImageUnit Class
description: This page shows CDeformationResistedBarcodeImageUnit class definition of Dynamsoft Barcode Reader SDK C++ Edition.
keywords: GetImageData, CDeformationResistedBarcodeImageUnit, api reference
---
# CDeformationResistedBarcodeImageUnit Class

The `CDeformationResistedBarcodeImageUnit` class represents a unit that contains deformation resisted barcode image data. It inherits from the `CIntermediateResultUnit` class.

## Definition

*Namespace:* dynamsoft::dbr::intermediate_results

*Assembly:* DynamsoftBarcodeReader

*Inheritance:* [CIntermediateResultUnit]({{ site.dcv_cpp_api }}core/intermediate-results/intermediate-result-unit.html) -> CDeformationResistedBarcodeImageUnit

```cpp
class CDeformationResistedBarcodeImageUnit: public CIntermediateResultUnit
```

## Methods

| Method                            | Description |
|-----------------------------------|-------------|
| [`GetImageData`](#getimagedata)           | Gets the deformation resisted barcode image data.|

### Inherited Methods

{%- include inherited-methods/intermediate-result-unit-10.0.20.md -%}

### GetImageData

Gets the deformation resisted barcode image data.

```cpp
virtual const CImageData* GetImageData() const = 0;
```

**Return value**

Returns a pointer to the deformation resisted barcode image data.

**See Also**

[CImageData]({{ site.dcv_cpp_api }}core/basic-structures/image-data.html)
