---
layout: default-layout
title: CScaledUpBarcodeImageUnit Class
description: This page shows CScaledUpBarcodeImageUnit class definition of Dynamsoft Barcode Reader SDK C++ Edition.
keywords: GetImageData, CScaledUpBarcodeImageUnit, api reference
permalink: /programming/cplusplus/api-reference/scaled-up-barcode-image-unit.html
---
# CScaledUpBarcodeImageUnit Class

The `CScaledUpBarcodeImageUnit` class represents a unit that contains scaled up barcode image. It inherits from the `CIntermediateResultUnit` class.

## Definition

*Namespace:* dynamsoft::dbr::intermediate_results

*Assembly:* DynamsoftBarcodeReader

*Inheritance:* [CIntermediateResultUnit]({{ site.dcv_cpp_api }}core/intermediate-results/intermediate-result-unit.html) -> CScaledUpBarcodeImageUnit

```cpp
class CScaledUpBarcodeImageUnit: public CIntermediateResultUnit
```

## Methods

| Method                            | Description |
|-----------------------------------|-------------|
| [`GetImageData`](#getimagedata)           | Gets the scaled up barcode image data.|

### Inherited Methods

{%- include inherited-methods/intermediate-result-unit.md -%}

### GetImageData

Gets the scaled up barcode image data.

```cpp
virtual const CImageData* GetImageData() const = 0;
```

**Return value**

Returns a pointer to the scaled up image of the barcode.

**See Also**

[CImageData]({{ site.dcv_cpp_api }}core/basic-structures/image-data.html)
