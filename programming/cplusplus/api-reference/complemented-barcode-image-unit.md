---
layout: default-layout
title: CComplementedBarcodeImageUnit Class
description: This page shows CComplementedBarcodeImageUnit class definition of Dynamsoft Barcode Reader SDK C++ Edition.
keywords: GetImageData, CComplementedBarcodeImageUnit, api reference
permalink: /programming/cplusplus/api-reference/complemented-barcode-image-unit.html
---
# CComplementedBarcodeImageUnit Class
The `CComplementedBarcodeImageUnit` class represents a unit that contains complemented barcode image data. It inherits from the `CIntermediateResultUnit` class.

## Definition

*Namespace:* dynamsoft::dbr::intermediate_results

*Assembly:* DynamsoftBarcodeReader.dll

```cpp
class CComplementedBarcodeImageUnit: public CIntermediateResultUnit
```

## Methods

| Method                            | Description |
|-----------------------------------|-------------|
| [`GetLocation`](#getlocation) | Get the location of the complemented barcode in a quadrilateral.|
| [`GetImageData`](#getimagedata) | Gets the complemented barcode image data.|

### GetLocation

Get the location of the complemented barcode in a quadrilateral.

```cpp
virtual CQuadrilateral GetLocation() const = 0;
```

**Return value**

Returns the location of the complemented barcode in a quadrilateral.

### GetImageData

Gets the complemented barcode image data.

```cpp
virtual const CImageData* GetImageData() const = 0;
```

**Return value**

Returns a pointer to the complemented image of the barcode.
