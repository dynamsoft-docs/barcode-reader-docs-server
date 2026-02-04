---
layout: default-layout
title: DeformationResistedBarcodeImageUnit Class - Dynamsoft Barcode Reader Python Edition API Reference
description: This page shows DeformationResistedBarcodeImageUnit class definition of Dynamsoft Barcode Reader SDK Python Edition.
keywords: get_deformation_resisted_barcode, set_deformation_resisted_barcode, DeformationResistedBarcodeImageUnit, api reference
---
# DeformationResistedBarcodeImageUnit Class

The `DeformationResistedBarcodeImageUnit` class represents a unit that contains deformation resisted barcode image data. It inherits from the `IntermediateResultUnit` class.

## Definition

*Module:* dbr

*Inheritance:* [IntermediateResultUnit]({{ site.dcvb_python_api }}core/intermediate-results/intermediate-result-unit.html) -> DeformationResistedBarcodeImageUnit

```python
class DeformationResistedBarcodeImageUnit(IntermediateResultUnit)
```

## Methods

| Method                            | Description |
|-----------------------------------|-------------|
| [`get_deformation_resisted_barcode`](#get_deformation_resisted_barcode) | Gets the deformation resisted barcode object.|
| [`set_deformation_resisted_barcode`](#set_deformation_resisted_barcode) | Sets the deformation resisted barcode object.|

### get_deformation_resisted_barcode

Gets the deformation resisted barcode object.

```python
def get_deformation_resisted_barcode(self) -> DeformationResistedBarcode:
```

**Return value**

Returns an instance of `DeformationResistedBarcode`.

**See Also**

[DeformationResistedBarcode]({{ site.dbr_python_api }}deformation-resisted-barcode.html)

### set_deformation_resisted_barcode

Sets the deformation resisted barcode object.

```python
def set_deformation_resisted_barcode(self, barcode: DeformationResistedBarcode, matrix_to_original_image: List[float] = IDENTITY_MATRIX) -> int:
```

**Parameters**

`barcode` The deformation resisted barcode object.

`matrix_to_original_image` The matrix to original image.

**Return value**

Returns 0 if successful, otherwise returns a negative value.

**See Also**

[DeformationResistedBarcode]({{ site.dbr_python_api }}deformation-resisted-barcode.html)
