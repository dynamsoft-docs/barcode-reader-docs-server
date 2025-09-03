---
layout: default-layout
title: CDeformationResistedBarcodeImageUnit Class - Dynamsoft Barcode Reader C++ Edition API Reference
description: This page shows CDeformationResistedBarcodeImageUnit class definition of Dynamsoft Barcode Reader SDK C++ Edition.
keywords: GetDeformationResistedBarcode, SetDeformationResistedBarcode, CDeformationResistedBarcodeImageUnit, api reference
---
# CDeformationResistedBarcodeImageUnit Class

The `CDeformationResistedBarcodeImageUnit` class represents a unit that contains deformation resisted barcode image data. It inherits from the `CIntermediateResultUnit` class.

## Definition

*Namespace:* dynamsoft::dbr::intermediate_results

*Assembly:* DynamsoftBarcodeReader

*Inheritance:* [CIntermediateResultUnit]({{ site.dcvb_cpp_api }}core/intermediate-results/intermediate-result-unit.html) -> CDeformationResistedBarcodeImageUnit

```cpp
class CDeformationResistedBarcodeImageUnit: public CIntermediateResultUnit
```

## Methods

| Method                            | Description |
|-----------------------------------|-------------|
| [`GetDeformationResistedBarcode`](#getdeformationresistedbarcode) | Gets the deformation resisted barcode object.|
| [`SetDeformationResistedBarcode`](#setdeformationresistedbarcode) | Sets the deformation resisted barcode object.|

### Inherited Methods

{%- include inherited-methods/intermediate-result-unit.md -%}

### GetDeformationResistedBarcode

Gets the deformation resisted barcode object.

```cpp
virtual CDeformationResistedBarcode GetDeformationResistedBarcode() const = 0;
```

**Return value**

Returns an instance of CDeformationResistedBarcode.

**See Also**

[CDeformationResistedBarcode]({{ site.dbr_cpp_api }}deformation-resisted-barcode.html)

### SetDeformationResistedBarcode

Sets the deformation resisted barcode object.

```cpp
virtual int SetDeformationResistedBarcode(const CDeformationResistedBarcode& barcode, const double matrixToOriginalImage[9] = IDENTITY_MATRIX) = 0;
```

**Parameters**

`[in] barcode` The deformation resisted barcode object.

`matrixToOriginalImage` The matrix to original image.

**Return value**

Returns 0 if successful, otherwise returns a negative value.

**See Also**

[CDeformationResistedBarcode]({{ site.dbr_cpp_api }}deformation-resisted-barcode.html)
