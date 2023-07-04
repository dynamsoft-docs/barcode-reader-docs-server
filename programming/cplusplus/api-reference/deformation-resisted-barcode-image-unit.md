---
layout: default-layout
title: CDeformationResistedBarcodeImageUnit Class
description: This page shows CDeformationResistedBarcodeImageUnit class definition of Dynamsoft Barcode Reader SDK C++ Edition.
keywords: GetImageData, CDeformationResistedBarcodeImageUnit, api reference
permalink: /programming/cplusplus/api-reference/deformation-resisted-barcode-image-unit.html
---
# CDeformationResistedBarcodeImageUnit Class

The `CDeformationResistedBarcodeImageUnit` class represents a unit that contains deformation resisted barcode image data. It inherits from the `CIntermediateResultUnit` class.

## Definition

*Namespace:* dynamsoft::dbr::intermediate_results

*Assembly:* DynamsoftBarcodeReader

```cpp
class CDeformationResistedBarcodeImageUnit: public CIntermediateResultUnit
```

## Methods

| Method                            | Description |
|-----------------------------------|-------------|
| [`GetImageData`](#getimagedata)           | Gets the deformation resisted barcode image data.|


### GetImageData

Gets the deformation resisted barcode image data.

```cpp
virtual const CImageData* GetImageData() const = 0;
```

**Return value**

Returns a pointer to the deformation resisted barcode image data.
