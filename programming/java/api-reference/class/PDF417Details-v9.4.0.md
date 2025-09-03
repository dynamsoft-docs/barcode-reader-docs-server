---
layout: default-layout
title: PDF417Details Class - Dynamsoft Barcode Reader SDK Java Edition API Reference
description: This page shows the PDF417Details Class of Dynamsoft Barcode Reader SDK Java Edition API Reference.
keywords: PDF417Details, class, api reference, java
needAutoGenerateSidebar: false
permalink: /programming/java/api-reference/class/PDF417Details-v9.4.0.html
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
