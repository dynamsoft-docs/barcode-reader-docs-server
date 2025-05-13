---
layout: default-layout
title: QRCodeDetails Class - Dynamsoft Barcode Reader Module .NET Edition API Reference
description: Definition of QRCodeDetails class in Dynamsoft Barcode Reader Module .NET Edition.
keywords: rows, columns, errorCorrectionLevel, version, model, mode, page, totalPage, parityData, QRCodeDetails, api reference
---
# QRCodeDetails

The `QRCodeDetails` class represents the details of a QR Code. It is derived from the `BarcodeDetails` class and contains various attributes related to the QR Code.

## Definition

*Namespace:* Dynamsoft.DBR


*Inheritance:* [BarcodeDetails]({{ site.dbr_dotnet_api }}barcode-details.html) -> QRCodeDetails

```csharp
public class QRCodeDetails : BarcodeDetails
```

## Attributes

| Attribute | Type |
|---------- | ---- |
| [`rows`](#rows) | *int* |
| [`columns`](#columns) | *int* |
| [`errorCorrectionLevel`](#errorcorrectionlevel) | *EnumQRCodeErrorCorrectionLevel* |
| [`version`](#version) | *int* |
| [`model`](#model) | *int* |
| [`mode`](#mode) | *int* |
| [`page`](#page) | *int* |
| [`totalPage`](#totalpage) | *int* |
| [`parityData`](#paritydata) | *byte* |
| [`codewords`](#codewords) | *byte[]* |
| [`dataMaskPattern`](#datamaskpattern) | *int* |

### rows

The row count of the QR Code.

```csharp
int rows;
```

### columns

The column count of the QR Code.

```csharp
int columns;
```

### errorCorrectionLevel

The error correction level of the QR Code.

```csharp
EnumQRCodeErrorCorrectionLevel errorCorrectionLevel;
```

**See Also**

[EnumQRCodeErrorCorrectionLevel]({{ site.dbr_dotnet_api }}enum-qr-code-error-correction-level.html)

### version

The version of the QR Code.

```csharp
int version;
```

### model

Number of models of the QR Code.

```csharp
int model;
```

### mode

Identify the first data encoding mode of the QR Code.

```csharp
int mode;
```

### page

Identify the position of the particular symbol in the Structured Append format of the QR Code.

```csharp
int page;
```

### totalPage

Identify the total number of symbols to be concatenated in the Structured Append format of the QR Code.

```csharp
int totalPage;
```

### parityData

The Parity Data shall be an 8 bit byte following the Symbol Sequence Indicator. The parity data is a value obtained by XORing byte by byte the ASCII/JIS values of all the original input data before division into symbol blocks.

```csharp
byte parityData;
```

### codewords

The codewords of the QR Code.

```csharp
byte[] codewords;
```

### dataMaskPattern

The data mask pattern reference for QR Code symbols.

```csharp
int dataMaskPattern;
```
