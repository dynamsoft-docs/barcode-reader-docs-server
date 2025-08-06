---
layout: default-layout
title: QRCodeDetails Class - Dynamsoft Barcode Reader Java Edition API Reference
description: Definition of QRCodeDetails class in Dynamsoft Barcode Reader Java Edition.
keywords: rows, columns, errorCorrectionLevel, version, model, mode, page, totalPage, parityData, QRCodeDetails, api reference
---
# QRCodeDetails

The `QRCodeDetails` class represents the details of a QR Code. It is derived from the `BarcodeDetails` class and contains various attributes related to the QR Code.

## Definition

*Package:* com.dynamsoft.dbr

*Inheritance:* [BarcodeDetails]({{ site.dbr_java_api }}barcode-details.html) -> QRCodeDetails

```java
public class QRCodeDetails extends BarcodeDetails
```

## Attributes

| Attribute | Type | Description |
|---------- | ---- | ----------- |
| [`rows`](#rows) | *int* | The row count of the QR Code. |
| [`columns`](#columns) | *int* | The column count of the QR Code. |
| [`errorCorrectionLevel`](#errorcorrectionlevel) | *int* | The error correction level of the QR Code. |
| [`version`](#version) | *int* | The version of the QR Code. |
| [`model`](#model) | *int* | Number of models of the QR Code. |
| [`mode`](#mode) | *int* | The first data encoding mode of the QR Code. |
| [`page`](#page) | *int* | The position of the particular symbol in the Structured Append format of the QR Code. |
| [`totalPage`](#totalpage) | *int* | The total number of symbols to be concatenated in the Structured Append format of the QR Code. |
| [`parityData`](#paritydata) | *byte* | The Parity Data following the Symbol Sequence Indicator. |
| [`dataMaskPattern`](#datamaskpattern) | *int* | The data mask pattern reference for QR Code symbols. |
| [`codewords`](#codewords) | *byte[]* | The codewords of the QR Code. |

## Constructors

| Constructor | Description |
|------------ | ----------- |
| [`QRCodeDetails()`](#qrcodedetails) | Default constructor. |
| [`QRCodeDetails(int rows, int columns, int errorCorrectionLevel, int version, int model, int mode, int page, int totalPage, int parityData)`](#qrcodedetailsint-rows-int-columns-int-errorcorrectionlevel-int-version-int-model-int-mode-int-page-int-totalpage-int-paritydata) | Constructor with parameters. |

## Attribute Details

### rows

The row count of the QR Code.

```java
public int rows
```

### columns

The column count of the QR Code.

```java
public int columns
```

### errorCorrectionLevel

The error correction level of the QR Code.

```java
public @EnumQRCodeErrorCorrectionLevel int errorCorrectionLevel
```

It is a value of the `EnumQRCodeErrorCorrectionLevel` enumeration.

**See Also**

[EnumQRCodeErrorCorrectionLevel]({{ site.dbr_java_api }}enum-qr-code-error-correction-level.html)

### version

The version of the QR Code.

```java
public int version
```

### model

Number of models of the QR Code.

```java
public int model
```

### mode

The first data encoding mode of the QR Code.

```java
public int mode
```

### page

The position of the particular symbol in the Structured Append format of the QR Code.

```java
public int page
```

### totalPage

The total number of symbols to be concatenated in the Structured Append format of the QR Code.

```java
public int totalPage
```

### parityData

The Parity Data shall be an 8 bit byte following the Symbol Sequence Indicator. The parity data is a value obtained by XORing byte by byte the ASCII/JIS values of all the original input data before division into symbol blocks.

```java
public byte parityData
```

### dataMaskPattern

The data mask pattern reference for QR Code symbols.

```java
public int dataMaskPattern
```

### codewords

The codewords of the QR Code.

```java
public byte[] codewords
```

## Constructor Details

### QRCodeDetails()

Default constructor. Initializes a new instance of the QRCodeDetails class with default values.

```java
public QRCodeDetails()
```

### QRCodeDetails(int rows, int columns, int errorCorrectionLevel, int version, int model, int mode, int page, int totalPage, int parityData)

Constructor with parameters. Initializes a new instance of the QRCodeDetails class with specified values.

```java
public QRCodeDetails(int rows, int columns, int errorCorrectionLevel, int version, int model, int mode, int page, int totalPage, int parityData)
```

**Parameters**

`rows`: The row count of the QR Code.

`columns`: The column count of the QR Code.

`errorCorrectionLevel`: The error correction level of the QR Code.

`version`: The version of the QR Code.

`model`: Number of models of the QR Code.

`mode`: The first data encoding mode of the QR Code.

`page`: The position of the particular symbol in the Structured Append format of the QR Code.

`totalPage`: The total number of symbols to be concatenated in the Structured Append format of the QR Code.

`parityData`: The Parity Data following the Symbol Sequence Indicator.
