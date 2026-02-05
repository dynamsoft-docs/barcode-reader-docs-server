---
layout: default-layout
title: AztecDetails Class - Dynamsoft Barcode Reader Module Python Edition API Reference
description: Definition of AztecDetails class in Dynamsoft Barcode Reader Module Python Edition.
keywords: rows, columns, layer_number, AztecDetails, api reference
---

# AztecDetails

The `AztecDetails` class represents a barcode in Aztec format. It inherits from the `BarcodeDetails` class and contains information about the row count, column count, and layer number of the barcode.

## Definition

*Module:* dbr

*Inheritance:* [BarcodeDetails]({{ site.dbr_python_api }}barcode-details.html) -> AztecDetails

```python
class AztecDetails(BarcodeDetails)
```

## Properties

| Property  | Type |
|---------- | ---- |
| [`rows`](#rows) | *int* |
| [`columns`](#columns) | *int* |
| [`layer_number`](#layer_number) | *int* |

### rows

The number of rows in the Aztec barcode.

### columns

The number of columns in the Aztec barcode.

### layer_number

Specifies the layer number of the Aztec barcode. A negative number (-1, -2, -3, -4) specifies a compact Aztec code. A positive number (1, 2, .. 32) specifies a normal (full-range) Aztec code.
