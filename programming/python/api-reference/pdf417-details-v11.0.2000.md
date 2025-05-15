---
layout: default-layout
title: PDF417Details Class - Dynamsoft Barcode Reader Module Python Edition API Reference
description: Definition of PDF417Details class in Dynamsoft Barcode Reader Module Python Edition.
keywords: rows, columns, error_correction_level, PDF417Details, api reference
---
# PDF417Details

The `PDF417Details` class represents a barcode in PDF417 format. It inherits from the `BarcodeDetails` class and contains information about the row count, column count, and error correction level of the barcode.

## Definition

*Module:* dynamsoft_barcode_reader

*Inheritance:* [BarcodeDetails]({{ site.dbr_python_api }}barcode-details.html) -> PDF417Details

```python
class PDF417Details(BarcodeDetails)
```

## Properties

| Property  | Type |
|---------- | ---- |
| [`rows`](#rows) | *int* |
| [`columns`](#columns) | *int* |
| [`error_correction_level`](#error_correction_level) | *int* |
| [`has_left_row_indicator`](#has_left_row_indicator) | *int* |
| [`has_right_row_indicator`](#has_right_row_indicator) | *int* |

### rows

The number of rows in the PDF417 barcode.

### columns

The number of columns in the PDF417 barcode.

### error_correction_level

The error correction level of PDF417 code.

### has_left_row_indicator

Specifies whether the left row indicator of the PDF417 code exists.

### has_right_row_indicator

Specifies whether the right row indicator of the PDF417 code exists.
