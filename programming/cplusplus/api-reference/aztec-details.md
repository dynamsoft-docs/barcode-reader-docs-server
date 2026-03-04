---
layout: default-layout
title: CAztecDetails Class - Dynamsoft Barcode Reader C++ Edition API Reference
description: API reference for the CAztecDetails class in Dynamsoft Barcode Reader C++ Edition, which stores the row count, column count, and layer number of a decoded Aztec barcode.
keywords: rows, columns, layerNumber, CAztecDetails, api reference
---
# CAztecDetails

The `CAztecDetails` class represents a barcode in Aztec format. It inherits from the `CBarcodeDetails` class and contains information about the row count, column count, and layer number of the barcode.

## Definition

*Namespace:* dynamsoft::dbr

*Assembly:* DynamsoftBarcodeReader

*Inheritance:* [CBarcodeDetails]({{ site.dbr_cpp_api }}barcode-details.html) -> CAztecDetails

```cpp
class CAztecDetails : public CBarcodeDetails
```

## Attributes

| Attribute | Type |
|---------- | ---- |
| [`rows`](#rows) | *int* |
| [`columns`](#columns) | *int* |
| [`layerNumber`](#layernumber) | *int* |

### rows

The number of rows in the Aztec barcode.

```cpp
int rows
```

### columns

The number of columns in the Aztec barcode.

```cpp
int columns
```

### layerNumber

Specifies the layer number of the Aztec barcode. A negative number (-1, -2, -3, -4) specifies a compact Aztec code. A positive number (1, 2, .. 32) specifies a normal (full-range) Aztec code.

```cpp
int layerNumber
```
