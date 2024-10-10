---
layout: default-layout
title: QRCodeDetails Class - Dynamsoft Barcode Reader Module Python Edition API Reference
description: Definition of QRCodeDetails class in Dynamsoft Barcode Reader Module Python Edition.
keywords: rows, columns, error_correction_level, version, model, mode, page, total_page, parity_data, QRCodeDetails, api reference
---
# QRCodeDetails

The `QRCodeDetails` class represents the details of a QR Code. It is derived from the `BarcodeDetails` class and contains various attributes related to the QR Code.

## Definition

*Module:* dynamsoft_barcode_reader

*Inheritance:* [BarcodeDetails]({{ site.dbr_python_api }}barcode-details.html) -> QRCodeDetails

```python
class QRCodeDetails(BarcodeDetails)
```

## Properties

| Property  | Type |
|---------- | ---- |
| [`rows`](#rows) | *int* |
| [`columns`](#columns) | *int* |
| [`error_correction_level`](#error_correction_level) | *int* |
| [`version`](#version) | *int* |
| [`model`](#model) | *int* |
| [`mode`](#mode) | *int* |
| [`page`](#page) | *int* |
| [`total_page`](#total_page) | *int* |
| [`parity_data`](#parity_data) | *byte* |
| [`data_mask_pattern`](#data_mask_pattern) | *int* |
| [`codewords`](#codewords) | *bytes* |

### rows

The row count of the QR Code.

### columns

The column count of the QR Code.

### error_correction_level

The error correction level of the QR Code.

It is a value of the `EnumQRCodeErrorCorrectionLevel` enumeration.

**See Also**

[EnumQRCodeErrorCorrectionLevel]({{ site.dcvb_enumerations }}barcode-reader/qr-code-error-correction-level.html?lang=python)

### version

The version of the QR Code.

### model

Number of models of the QR Code.

### mode

The first data encoding mode of the QR Code.

### page

The position of the particular symbol in the Structured Append format of the QR Code.

### total_page

The total number of symbols to be concatenated in the Structured Append format of the QR Code.

### parity_data

The Parity Data shall be an 8 bit byte following the Symbol Sequence Indicator. The parity data is a value obtained by XORing byte by byte the ASCII/JIS values of all the original input data before division into symbol blocks.

### data_mask_pattern

The data mask pattern reference for QR Code symbols.

### codewords

The codewords of the QR Code.
