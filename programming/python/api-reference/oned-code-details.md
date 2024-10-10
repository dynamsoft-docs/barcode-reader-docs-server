---
layout: default-layout
title: OneDCodeDetails Class - Dynamsoft Barcode Reader Module Python Edition API Reference
description: Definition of OneDCodeDetails class in Dynamsoft Barcode Reader Module Python Edition.
keywords: startchar, stopchars, OneDCodeDetails, api reference
---
# OneDCodeDetails

The `OneDCodeDetails` class represents detailed information about a one-dimensional barcode. It inherits from the `BarcodeDetails` class.

## Definition

*Module:* dynamsoft_barcode_reader

*Inheritance:* [BarcodeDetails]({{ site.dbr_python_api }}barcode-details.html) -> OneDCodeDetails

```python
class OneDCodeDetails(BarcodeDetails)
```

## Properties

| Property  | Type |
|---------- | ---- |
| [`start_chars_bytes`](#start_chars_bytes) | *bytes* |
| [`stop_chars_bytes`](#stop_chars_bytes) | *bytes* |
| [`check_digit_bytes`](#check_digit_bytes) | *bytes* |
| [`start_pattern_range`](#start_pattern_range) | *List[float]* |
| [`middle_pattern_range`](#middle_pattern_range) | *List[float]* |
| [`end_pattern_range`](#end_pattern_range) | *List[float]* |

### start_chars_bytes

The start chars of the one-dimensional barcode in a byte array.

### stop_chars_bytes

The stop chars of the one-dimensional barcode in a byte array.

### check_digit_bytes

The check digit chars of the one-dimensional barcode in a byte array.

### start_pattern_range

The position of the start pattern relative to the barcode location.

**Remarks**

The property represents a float list of length 2:
- Index 0: X coordinate of the start position in percentage value.
- Index 1: X coordinate of the end position in percentage value.

### middle_pattern_range

The position of the middle pattern relative to the barcode location.

**Remarks**

The property represents a float list of length 2:
- Index 0: X coordinate of the start position in percentage value.
- Index 1: X coordinate of the end position in percentage value.

### end_pattern_range

The position of the end pattern relative to the barcode location.

**Remarks**

The property represents a float list of length 2:
- Index 0: X coordinate of the start position in percentage value.
- Index 1: X coordinate of the end position in percentage value.
