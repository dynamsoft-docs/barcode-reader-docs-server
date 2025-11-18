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
| Inherited Methods from [CIntermediateResultUnit]({{ site.dcvb_cpp_api }}core/intermediate-results/intermediate-result-unit.html): | |
| [`GetHashId`]({{ site.dcvb_cpp_api }}core/intermediate-results/intermediate-result-unit.html#gethashid) | Gets the hash ID of the unit.|
| [`GetOriginalImageHashId`]({{ site.dcvb_cpp_api }}core/intermediate-results/intermediate-result-unit.html#getoriginalimagehashid) | Gets the hash ID of the original image. |
| [`GetOriginalImageTag`]({{ site.dcvb_cpp_api }}core/intermediate-results/intermediate-result-unit.html#getoriginalimagetag) | Gets the image tag of the original image. |
| [`GetType`]({{ site.dcvb_cpp_api }}core/intermediate-results/intermediate-result-unit.html#gettype) | Gets the type of the intermediate result unit. |
| [`Clone`]({{ site.dcvb_cpp_api }}core/intermediate-results/intermediate-result-unit.html#clone) | Creates a copy of the intermediate result unit. |
| [`SetHashId`]({{ site.dcvb_cpp_api }}core/intermediate-results/intermediate-result-unit.html#sethashid) | Sets the hash ID of the unit. |
| [`SetOriginalImageHashId`]({{ site.dcvb_cpp_api }}core/intermediate-results/intermediate-result-unit.html#setoriginalimagehashid) | Sets the hash ID of the original image. |
| [`SetOriginalImageTag`]({{ site.dcvb_cpp_api }}core/intermediate-results/intermediate-result-unit.html#setoriginalimagetag) | Sets the image tag of the original image. |
| [`Retain`]({{ site.dcvb_cpp_api }}core/intermediate-results/intermediate-result-unit.html#retain) | Increases the reference count of the unit. |
| [`Release`]({{ site.dcvb_cpp_api }}core/intermediate-results/intermediate-result-unit.html#release) | Decreases the reference count of the unit. |
| [`GetTransformMatrix`]({{ site.dcvb_cpp_api }}core/intermediate-results/intermediate-result-unit.html#gettransformmatrix) | Gets the transformation matrix via TransformMatrixType. |
| [`SetTransformMatrix`]({{ site.dcvb_cpp_api }}core/intermediate-results/intermediate-result-unit.html#settransformmatrix) | Sets the transformation matrix via TransformMatrixType. |

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

