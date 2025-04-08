---
layout: default-layout
title: CandidateBarcodeZone Class - Dynamsoft Barcode Reader Python Edition API Reference
description: This page shows CandidateBarcodeZone class definition of Dynamsoft Barcode Reader SDK Python Edition.
keywords: get_location, set_location, get_possible_formats, set_possible_formats, CandidateBarcodeZone, api reference
---
# CandidateBarcodeZone Class

The `CandidateBarcodeZone` class represents a candidate zone for barcode detection.

## Definition

*Module:* dynamsoft_barcode_readers

```python
class CandidateBarcodeZone
```

## Methods

| Method                            | Description |
|-----------------------------------|-------------|
| [`__init__`](#__init__) | Initializes a new instance of the `CandidateBarcodeZone` class. |
| [`get_location`](#get_location)           | Gets the location of the candidate barcode.|
| [`set_location`](#set_location)           | Sets the location of the candidate barcode.|
| [`get_possible_formats`](#get_possible_formats)           | Gets the posssible formats of the candidate barcode. |
| [`set_possible_formats`](#set_possible_formats)           | Sets the posssible formats of the candidate barcode. |


### \_\_init\_\_

Initializes a new instance of the `CandidateBarcodeZone` class.

```python
def __init__(self, location: Quadrilateral=None, possibleFormats: int=None):
```

**Parameters**

`location` The location of the candidate barcode.

`possible_formats` The posssible formats of the candidate barcode.

### get_location

Gets the location of the candidate barcode.

```python
def get_location(self) -> Quadrilateral:
```

**Return value**

Returns the location of the candidate barcode.

**See Also**

[Quadrilateral]({{ site.dcvb_python_api }}core/basic-classes/quadrilateral.html)

### set_location

Sets the location of the candidate barcode.

```python
def set_location(self, loc: Quadrilateral) -> None:
```

**Parameters**

`loc` The location of the candidate barcode. 

**See Also**

[Quadrilateral]({{ site.dcvb_python_api }}core/basic-classes/quadrilateral.html)

### get_possible_formats

Gets the posssible formats of the candidate barcode.

```python
def get_possible_formats(self) -> int:
```

**Return value**

Returns the posssible formats of the candidate barcode.

**See Also**

[EnumBarcodeFormat]({{ site.dbr_python_api }}enum-barcode-format.html)

### set_possible_formats

Sets the posssible formats of the candidate barcode.

```python
def set_possible_formats(self, formats: int) -> None:
```

**Parameters**

`formats` The posssible formats of the candidate barcode.

**See Also**

[EnumBarcodeFormat]({{ site.dbr_python_api }}enum-barcode-format.html)