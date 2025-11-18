---
layout: default-layout
title: CLocalizedBarcodesUnit Class - Dynamsoft Barcode Reader C++ Edition API Reference
description: This page shows CLocalizedBarcodesUnit class definition of Dynamsoft Barcode Reader SDK C++ Edition.
keywords: GetCount, GetLocalizedBarcode, AddLocalizedBarcode, RemoveAllLocalizedBarcodes, RemoveLocalizedBarcode, SetLocalizedBarcode, CLocalizedBarcodesUnit, api reference
---
# CLocalizedBarcodesUnit Class

The `CLocalizedBarcodesUnit` class represents a unit that contains localized barcodes unit. It inherits from the `CIntermediateResultUnit` class.

## Definition

*Namespace:* dynamsoft::dbr::intermediate_results

*Assembly:* DynamsoftBarcodeReader

*Inheritance:* [CIntermediateResultUnit]({{ site.dcvb_cpp_api }}core/intermediate-results/intermediate-result-unit.html) -> CLocalizedBarcodesUnit

```cpp
class CLocalizedBarcodesUnit: public CIntermediateResultUnit
```

## Methods

| Method                            | Description |
|-----------------------------------|-------------|
| [`AddLocalizedBarcode`](#addlocalizedbarcode)           | Adds a localized barcode.|
| [`GetLocalizedBarcode`](#getlocalizedbarcode)           | Gets a pointer to a specific localized barcode element.|
| [`GetCount`](#getcount)           | Gets the number of localized barcodes in the unit.|
| [`RemoveAllLocalizedBarcodes`](#removealllocalizedbarcodes)           | Removes all the localized barcodes.|
| [`RemoveLocalizedBarcode`](#removelocalizedbarcode)           | Removes a localized barcode at the specified index.|
| [`SetLocalizedBarcode`](#setlocalizedbarcode)           | Sets a localized barcode at the specified index.|
| [`operator[]`](#operator)           | Gets a pointer to a specific localized barcode element.|
| **Methods Inherited from [CIntermediateResultUnit]({{ site.dcvb_cpp_api }}core/intermediate-results/intermediate-result-unit.html):** | |
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

### AddLocalizedBarcode

Adds a localized barcode.

```cpp
virtual int AddLocalizedBarcode(const CLocalizedBarcodeElement* element, const double matrixToOriginalImage[9] = IDENTITY_MATRIX) = 0;
```

**Parameters**

`element` The localized barcode element to be added.

`matrixToOriginalImage` The matrix to original image.

**Return value**

Returns 0 if successful, otherwise returns a negative value.


### GetCount

Gets the number of localized barcodes in the unit.

```cpp
virtual int GetCount() const = 0;
```

**Return value**

Returns the number of localized barcodes in the unit.


### GetLocalizedBarcode

Gets a pointer to a specific localized barcode element.

```cpp
virtual const CLocalizedBarcodeElement* GetLocalizedBarcode(int index) const = 0;
```

**Parameters**

`[in] index` The index of the localized barcode element to retrieve.

**Return value**

Returns a const pointer to the localized barcode element at the specified index.

**See Also**

[CLocalizedBarcodeElement]({{ site.dbr_cpp_api }}localized-barcode-element.html)

### RemoveAllLocalizedBarcodes

Removes all the localized barcodes

```cpp
virtual void RemoveAllLocalizedBarcodes() = 0;
```

### RemoveLocalizedBarcode

Removes a localized barcode at the specified index

```cpp
virtual int RemoveLocalizedBarcode(int index) = 0;
```

**Parameters**

`index` The index of the localized barcode.

**Return value**

Returns 0 if successful, otherwise returns a negative value.

### SetLocalizedBarcode

Sets a localized barcode at the specified index.

```cpp
virtual int SetLocalizedBarcode(int index, const CLocalizedBarcodeElement* element, const double matrixToOriginalImage[9] = IDENTITY_MATRIX) = 0;
```

**Parameters**

`index` The index of the localized barcode.

`element` The localized barcode element to be set.

`matrixToOriginalImage` The matrix to original image.

**Return value**

Returns 0 if successful, otherwise returns a negative value.

### operator[]

Gets a pointer to a specific localized barcode element.

```cpp
virtual const CLocalizedBarcodeElement* operator[](int index) const = 0;
```

**Parameters**

`[in] index` The index of the localized barcode element to retrieve.

**Return value**

Returns a const pointer to the localized barcode element at the specified index.

**See Also**

[CLocalizedBarcodeElement]({{ site.dbr_cpp_api }}localized-barcode-element.html)
