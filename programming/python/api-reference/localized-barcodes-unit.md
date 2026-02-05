---
layout: default-layout
title: LocalizedBarcodesUnit Class - Dynamsoft Barcode Reader Python Edition API Reference
description: This page shows LocalizedBarcodesUnit class definition of Dynamsoft Barcode Reader SDK Python Edition.
keywords: get_count, get_localized_barcode, add_localized_barcode, remove_all_localized_barcodes, remove_localized_barcode, set_localized_barcode, LocalizedBarcodesUnit, api reference
---
# LocalizedBarcodesUnit Class

The `LocalizedBarcodesUnit` class represents a unit that contains localized barcodes unit. It inherits from the `IntermediateResultUnit` class.

## Definition

*Module:* dbr

*Inheritance:* [IntermediateResultUnit]({{ site.dcvb_python_api }}core/intermediate-results/intermediate-result-unit.html) -> LocalizedBarcodesUnit

```python
class LocalizedBarcodesUnit(IntermediateResultUnit)
```

## Methods

| Method                            | Description |
|-----------------------------------|-------------|
| [`add_localized_barcode`](#add_localized_barcode)           | Adds a localized barcode.|
| [`get_localized_barcode`](#get_localized_barcode)           | Gets a localized barcode element.|
| [`get_count`](#get_count)           | Gets the number of localized barcodes in the unit.|
| [`remove_all_localized_barcodes`](#remove_all_localized_barcodes)           | Removes all the localized barcodes.|
| [`remove_localized_barcode`](#remove_localized_barcode)           | Removes a localized barcode at the specified index.|
| [`set_localized_barcode`](#set_localized_barcode)           | Sets a localized barcode at the specified index.|

### add_localized_barcode

Adds a localized barcode.

```python
def add_localized_barcode(self, element: LocalizedBarcodeElement, matrix_to_original_image: List[float] = IDENTITY_MATRIX) -> int:
```

**Parameters**

`element` The localized barcode element to be added.

`matrix_to_original_image` The matrix to original image.

**Return value**

Returns 0 if successful, otherwise returns a negative value.


### get_count

Gets the number of localized barcodes in the unit.

```python
def get_count(self) -> int:
```

**Return value**

Returns the number of localized barcodes in the unit.


### get_localized_barcode

Gets a localized barcode element.

```python
def get_localized_barcode(self, index: int) -> LocalizedBarcodeElement:
```

**Parameters**

`index` The index of the localized barcode element to retrieve.

**Return value**

Returns the localized barcode element at the specified index.

**See Also**

[LocalizedBarcodeElement]({{ site.dbr_python_api }}localized-barcode-element.html)

### remove_all_localized_barcodes

Removes all the localized barcodes

```python
def remove_all_localized_barcodes(self) -> None:
```

### remove_localized_barcode

Removes a localized barcode at the specified index

```python
def remove_localized_barcode(self, index: int) -> int:
```

**Parameters**

`index` The index of the localized barcode.

**Return value**

Returns 0 if successful, otherwise returns a negative value.

### set_localized_barcode

Sets a localized barcode at the specified index.

```python
def set_localized_barcode(self, index: int, element: LocalizedBarcodeElement, matrix_to_original_image: List[float] = IDENTITY_MATRIX) -> int:
```

**Parameters**

`index` The index of the localized barcode.

`element` The localized barcode element to be set.

`matrix_to_original_image` The matrix to original image.

**Return value**

Returns 0 if successful, otherwise returns a negative value.

