---
layout: default-layout
title: LocalizedBarcodeElement Class - Dynamsoft Barcode Reader Python Edition API Reference
description: This page shows LocalizedBarcodeElement class definition of Dynamsoft Barcode Reader SDK Python Edition.
keywords: get_angle, get_confidence, get_possible_formats, get_possible_formats_string, get_module_size, set_possible_formats, LocalizedBarcodeElement, api reference
---
# LocalizedBarcodeElement Class

The `LocalizedBarcodeElement` class represents a localized barcode element detected in an image. It is inherited from `RegionObjectElement` class.

## Definition

*Module:* dbr

*Inheritance:* [RegionObjectElement]({{ site.dcvb_python_api }}core/intermediate-results/region-object-element.html) -> LocalizedBarcodeElement

```python
class LocalizedBarcodeElement(RegionObjectElement)
```

## Methods

| Method | Description |
|--------|-------------|
| [`__init__`](#__init__) | Initializes a new instance of the `LocalizedBarcodeElement` class. |
| [`get_angle`](#get_angle) | Gets the orientation angle of the barcode. |
| [`get_confidence`](#get_confidence) | Gets the confidence score of the barcode localization result. |
| [`get_possible_formats`](#get_possible_formats) | Gets the possible format of the barcode. |
| [`get_possible_formats_string`](#get_possible_formats_string) | Get all possible formats of the localized barcode in one string splited by ",". |
| [`get_module_size`](#get_module_size) | Gets the module size of the barcode. |
| [`set_possible_formats`](#set_possible_formats) | Sets the posssible formats of the barcode. |

### \_\_init\_\_

Initializes a new instance of the `LocalizedBarcodeElement` class.

```python
def __init__(self):
```

### get_angle

It is used to get the orientation angle of the barcode.

```python
def get_angle(self) -> int:
```

**Return value**

Returns the orientation angle of the barcode.

### get_confidence

It is used to get the confidence score of the barcode localization result.

```python
def get_confidence(self) -> int:
```

**Return value**

Returns the confidence score of the barcode recognition result. It represents the confidence that the positioning area is a barcode.

### get_possible_formats

It is used to get the format of the barcode.

```python
def get_possible_formats(self) -> int:
```

**Return value**

Returns the format of the barcode.

**See Also**

[EnumBarcodeFormat]({{ site.dbr_python_api }}enum-barcode-format.html)

### get_possible_formats_string

It is used to get all possible formats of the localized barcode in one string splited by ",".

```python
def get_possible_formats_string(self) -> str:
```

**Return value**

Returns the string representation of the barcode format in one string splited by ",".

### get_module_size

It is used to get the module size of the barcode.

```python
def get_module_size(self) -> int:
```

**Return value**

Returns the module size of the barcode.

### set_possible_formats

Sets the posssible formats of the barcode.

```python
def set_possible_formats(self, possible_formats: int) -> None:
```

**Parameters**

`possible_formats` The posssible formats of the barcode.

**See Also**

[EnumBarcodeFormat]({{ site.dbr_python_api }}enum-barcode-format.html)