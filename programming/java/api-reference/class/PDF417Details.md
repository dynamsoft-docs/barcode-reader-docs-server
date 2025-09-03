---
layout: default-layout
title: PDF417Details Class - Dynamsoft Barcode Reader SDK Java Edition API Reference
description: This page shows the PDF417Details Class of Dynamsoft Barcode Reader SDK Java Edition API Reference.
keywords: PDF417Details, class, api reference, java
needAutoGenerateSidebar: false
permalink: /programming/java/api-reference/class/PDF417Details.html
---


# PDF417Details
Stores the PDF417 details.

## Attributes
  
| Attribute | Type |
|---------- | ---- |
| [`moduleSize`](#modulesize) | *int* |
| [`rows`](#rows) | *int* |
| [`columns`](#columns) | *int* |
| [`errorCorrectionLevel`](#errorcorrectionlevel) | *int* |
| [`hasLeftRowIndicator`](#hasleftrowindicator) | *int* |
| [`hasRightRowIndicator`](#hasrightrowindicator) | *int* |

### moduleSize

The barcode module size (the minimum bar width in pixel).

```java
int com.dynamsoft.dbr.PDF417Details.moduleSize
```

### rows

The row count of the barcode.

```java
int com.dynamsoft.dbr.PDF417Details.rows
```

### columns

The column count of codewords between the left and right row indicators, where the actual data and the ECC is encoded.

```java
int com.dynamsoft.dbr.PDF417Details.columns
```

### errorCorrectionLevel

The error correction level of the barcode.

```java
int com.dynamsoft.dbr.PDF417Details.errorCorrectionLevel
```

### hasLeftRowIndicator

Whether the left row indicator of the PDF417 code exists.

- 0: left row indicator does not exist
- 1: left row indicator exists

```java
int com.dynamsoft.dbr.PDF417Details.hasLeftRowIndicator
```

### hasRightRowIndicator

Whether the right row indicator of the PDF417 code exists.

- 0: right row indicator does not exist
- 1: right row indicator exists

```java
int com.dynamsoft.dbr.PDF417Details.hasRightRowIndicator
```
