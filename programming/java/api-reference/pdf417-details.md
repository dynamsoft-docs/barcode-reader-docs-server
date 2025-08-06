---
layout: default-layout
title: PDF417Details Class - Dynamsoft Barcode Reader Java Edition API Reference
description: Definition of PDF417Details class in Dynamsoft Barcode Reader Java Edition.
keywords: rows, columns, errorCorrectionLevel, PDF417Details, api reference
---
# PDF417Details

The `PDF417Details` class represents a barcode in PDF417 format. It inherits from the `BarcodeDetails` class and contains information about the row count, column count, and error correction level of the barcode.

## Definition

*Package:* com.dynamsoft.dbr

*Inheritance:* [BarcodeDetails]({{ site.dbr_java_api }}barcode-details.html) -> PDF417Details

```java
public class PDF417Details extends BarcodeDetails
```

## Attributes

| Attribute | Type | Description |
|---------- | ---- | ----------- |
| [`rows`](#rows) | *int* | The number of rows in the PDF417 barcode. |
| [`columns`](#columns) | *int* | The number of columns in the PDF417 barcode. |
| [`errorCorrectionLevel`](#errorcorrectionlevel) | *int* | The error correction level of PDF417 code. |
| [`hasLeftRowIndicator`](#hasleftrowindicator) | *int* | Specifies whether the left row indicator of the PDF417 code exists. |
| [`hasRightRowIndicator`](#hasrightrowindicator) | *int* | Specifies whether the right row indicator of the PDF417 code exists. |
| [`codewords`](#codewords) | *int[]* | Specifies the codewords of the PDF417 barcode. |

## Constructors

| Constructor | Description |
|------------ | ----------- |
| [`PDF417Details()`](#pdf417details) | Default constructor. |
| [`PDF417Details(int rows, int columns, int errorCorrectionLevel, int hasLeftRowIndicator, int hasRightRowIndicator)`](#pdf417detailsint-rows-int-columns-int-errorcorrectionlevel-int-hasleftrowindicator-int-hasrightrowindicator) | Constructor with parameters. |
| [`PDF417Details(PDF417Details pdf417Details)`](#pdf417detailspdf417details-pdf417details) | Copy constructor. |

## Attribute Details

### rows

The number of rows in the PDF417 barcode.

```java
public int rows
```

### columns

The number of columns in the PDF417 barcode.

```java
public int columns
```

### errorCorrectionLevel

The error correction level of PDF417 code.

```java
public int errorCorrectionLevel
```

### hasLeftRowIndicator

Specifies whether the left row indicator of the PDF417 code exists.

```java
public int hasLeftRowIndicator
```

### hasRightRowIndicator

Specifies whether the right row indicator of the PDF417 code exists.

```java
public int hasRightRowIndicator
```

### codewords

Specifies the codewords of the PDF417 barcode.

```java
public int[] codewords
```

## Constructor Details

### PDF417Details()

Default constructor. Initializes a new instance of the PDF417Details class with default values (-1, -1, -1, -1, -1).

```java
public PDF417Details()
```

### PDF417Details(int rows, int columns, int errorCorrectionLevel, int hasLeftRowIndicator, int hasRightRowIndicator)

Constructor with parameters. Initializes a new instance of the PDF417Details class with specified values.

```java
public PDF417Details(int rows, int columns, int errorCorrectionLevel, int hasLeftRowIndicator, int hasRightRowIndicator)
```

**Parameters**

`rows`: The number of rows in the PDF417 barcode.

`columns`: The number of columns in the PDF417 barcode.

`errorCorrectionLevel`: The error correction level of PDF417 code.

`hasLeftRowIndicator`: Specifies whether the left row indicator of the PDF417 code exists.

`hasRightRowIndicator`: Specifies whether the right row indicator of the PDF417 code exists.

### PDF417Details(PDF417Details pdf417Details)

Copy constructor. Initializes a new instance of the PDF417Details class by copying another PDF417Details instance.

```java
public PDF417Details(PDF417Details pdf417Details)
```

**Parameters**

`pdf417Details`: The PDF417Details instance to copy from.
