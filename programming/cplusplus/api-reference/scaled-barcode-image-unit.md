---
layout: default-layout
title: CScaledBarcodeImageUnit Class - Dynamsoft Barcode Reader C++ Edition API Reference
description: This page shows CScaledBarcodeImageUnit class definition of Dynamsoft Barcode Reader SDK C++ Edition.
keywords: GetImageData, SetImageData, CScaledBarcodeImageUnit, api reference
---
# CScaledBarcodeImageUnit Class

The `CScaledBarcodeImageUnit` class represents a unit that contains scaled up barcode image. It inherits from the `CIntermediateResultUnit` class.

## Definition

*Namespace:* dynamsoft::dbr::intermediate_results

*Assembly:* DynamsoftBarcodeReader

*Inheritance:* [CIntermediateResultUnit]({{ site.dcvb_cpp_api }}core/intermediate-results/intermediate-result-unit.html) -> CScaledBarcodeImageUnit

```cpp
class CScaledBarcodeImageUnit: public CIntermediateResultUnit
```

## Methods

| Method                            | Description |
|-----------------------------------|-------------|
| [`GetImageData`](#getimagedata)           | Gets the scaled up barcode image data.|
| [`SetImageData`](#setimagedata)           | Sets the scaled up image data.|

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

[CImageData]({{ site.dcvb_cpp_api }}core/basic-structures/image-data.html)

### SetImageData

Sets the scaled up image data.

```cpp
virtual int SetImageData(const CImageData* imgData) = 0;
```

**Parameters**

`[in] imgData` The pointer to the scaled up image data.

**Return value**

Returns 0 if successful, otherwise returns a negative value.

**See Also**

[CImageData]({{ site.dcvb_cpp_api }}core/basic-structures/image-data.html)
