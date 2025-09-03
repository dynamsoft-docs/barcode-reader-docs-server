---
layout: default-layout
title: CQRCodeDetails Class - Dynamsoft Barcode Reader C++ Edition API Reference
description: This page shows CQRCodeDetails class definition of Dynamsoft Barcode Reader SDK C++ Edition.
keywords: rows, columns, errorCorrectionLevel, version, model, CQRCodeDetails, api reference
---
# CQRCodeDetails

The `CQRCodeDetails` class represents the details of a QR Code. It is derived from the `CBarcodeDetails` class and contains various attributes related to the QR Code.

## Definition

*Namespace:* dynamsoft::dbr

*Assembly:* DynamsoftBarcodeReader

*Inheritance:* [CBarcodeDetails]({{ site.dbr_cpp_api }}barcode-details.html) -> CQRCodeDetails

```cpp
class CQRCodeDetails : public CBarcodeDetails
```

## Attributes

| Attribute | Type |
|---------- | ---- |
| [`rows`](#rows) | *int* |
| [`columns`](#columns) | *int* |
| [`errorCorrectionLevel`](#errorcorrectionlevel) | *QRCodeErrorCorrectionLevel* |
| [`version`](#version) | *int* |
| [`model`](#model) | *int* |
| [`mode`](#mode) | *int* |
| [`page`](#page) | *int* |
| [`totalPage`](#totalpage) | *int* |
| [`parityData`](#paritydata) | *unsigned char* |
| [`dataMaskPattern`](#datamaskpattern) | *int* |
| [`codewords`](#codewords) | *unsigned char\** |
| [`codewordsCount`](#codewordscount) | *int* |

### rows

The row count of the QR Code.

```cpp
int rows
```

### columns

The column count of the QR Code.

```cpp
int columns
```

### errorCorrectionLevel

The error correction level of the QR Code.

```cpp
QRCodeErrorCorrectionLevel errorCorrectionLevel
```

**See Also**

[Enumeration QRCodeErrorCorrectionLevel]({{ site.dcvb_enumerations }}barcode-reader/qr-code-error-correction-level.html?src=cpp&&lang=cpp)

### version

The version of the QR Code.

```cpp
int version
```

### model

Number of models of the QR Code.

```cpp
int model
```

### mode

Identify the first data encoding mode of the QR Code.

```cpp
int mode
```

### page

Identify the position of the particular symbol in the Structured Append format of the QR Code.

```cpp
int page
```

### totalPage

Identify the total number of symbols to be concatenated in the Structured Append format of the QR Code.

```cpp
int totalPage
```

### parityData

The Parity Data shall be an 8 bit byte following the Symbol Sequence Indicator. The parity data is a value obtained by XORing byte by byte the ASCII/JIS values of all the original input data before division into symbol blocks.

```cpp
unsigned char parityData
```

### dataMaskPattern

The data mask pattern reference for QR Code symbols.

```cpp
int dataMaskPattern
```

### codewords

The codewords of the QR Code.

```cpp
unsigned char* codewords
```

### codewordsCount

The count of the codewords.

```cpp
int codewordsCount
```
