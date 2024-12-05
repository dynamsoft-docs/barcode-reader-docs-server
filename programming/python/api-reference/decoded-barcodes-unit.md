---
layout: default-layout
title: DecodedBarcodesUnit Class - Dynamsoft Barcode Reader Python Edition API Reference
description: This page shows DecodedBarcodesUnit class definition of Dynamsoft Barcode Reader SDK Python Edition.
keywords: get_count, get_decoded_barcode, remove_all_decoded_barcodes, set_decoded_barcode, DecodedBarcodesUnit, api reference
---
# DecodedBarcodesUnit Class

The `DecodedBarcodesUnit` class represents a unit that contains decoded barcode elements. It inherits from the `IntermediateResultUnit` class.

## Definition

*Module:* dynamsoft_barcode_readers

*Inheritance:* [IntermediateResultUnit]({{ site.dcvb_python_api }}core/intermediate-results/intermediate-result-unit.html) -> DecodedBarcodesUnit

```python
class DecodedBarcodesUnit(IntermediateResultUnit)
```

## Methods

| Method                            | Description |
|-----------------------------------|-------------|
| [`get_count`](#get_count)           | Gets the number of decoded barcodes in the unit.|
| [`get_decoded_barcode`](#get_decoded_barcode)           | Gets the `DecodedBarcodeElement` object at the specified index.|
| [`remove_all_decoded_barcodes`](#remove_all_decoded_barcodes)           | Removes all the decoded barcodes in the unit.|
| [`set_decoded_barcode`](#set_decoded_barcode)           | Sets the decoded barcode.|

### get_count

Gets the number of decoded barcodes in the unit.

```python
def get_count(self) -> int:
```

**Return value**

Returns the number of decoded barcodes in the unit.

### get_decoded_barcode

Gets the `DecodedBarcodeElement` object at the specified index.

```python
def get_decoded_barcode(self, index: int) -> DecodedBarcodeElement:
```

**Parameter**

`index` The index of the desired `DecodedBarcodeElement` object.

**Return value**

Returns the `DecodedBarcodeElement` object at the specified index.

**See Also**

[DecodedBarcodeElement]({{ site.dbr_python_api }}decoded-barcode-element.html)

### remove_all_decoded_barcodes

Removes all the decoded barcodes in the unit.

```python
def remove_all_decoded_barcodes(self) -> None:
```

### set_decoded_barcode

Sets the decoded barcode.

```python
def set_decoded_barcode(self, element: DecodedBarcodeElement, matrix_to_original_image: List[float] = IDENTITY_MATRIX) -> int:
```

**Parameters**

`element` The decoded barcode element.

`matrix_to_original_image` The matrix to original image.

**Return value**

Returns 0 if successful, otherwise returns a negative value.

**See Also**

[DecodedBarcodeElement]({{ site.dbr_python_api }}decoded-barcode-element.html)
