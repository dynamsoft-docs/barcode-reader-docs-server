---
layout: default-layout
title: QRCodeDetailedResult Class - Dynamsoft Barcode Reader SDK Python Edition API Reference
description: This page shows the QRCodeDetailedResult Class of Dynamsoft Barcode Reader SDK Python Edition.
keywords: QRCodeDetailedResult, class, api reference, python
needAutoGenerateSidebar: false
permalink: /programming/python/api-reference/class/QRCodeDetailedResult.html
---


# QRCodeDetailedResult
Stores the QRCode details.  


```python
class QRCodeDetailedResult
```  

## Attributes
  
| Attribute | Type |
|---------- | ---- |
| [`module_size`](#module_size) | *int* |
| [`rows`](#rows) | *int* |
| [`columns`](#columns) | *int* |
| [`error_correction_level`](#error_correction_level) | [`EnumQRCodeErrorCorrectionLevel`]({{ site.python_enumerations }}other-enums.html#qrcodeerrorcorrectionlevel) |
| [`version`](#version) | *int* |
| [`model`](#model) | *int* |
| [`mode`](#mode) | *int* |
| [`page`](#page) | *int* |
| [`totalPage`](#totalpage) | *int* |
| [`parityData`](#paritydata) | *int* |


### module_size
The barcode module size (the minimum bar width in pixel).  

```python
QRCodeDetailedResult.module_size
```

### rows
The row count of the barcode.  

```python
QRCodeDetailedResult.rows
```

### columns
The column count of the barcode. 

```python
QRCodeDetailedResult.columns
```

### error_correction_level
The error correction level of the barcode.  

```python
QRCodeDetailedResult.error_correction_level
```

### version
The version of the QR Code.

```python
QRCodeDetailedResult.version
```

### model
Number of the models.

```python
QRCodeDetailedResult.model
```

### mode

Identify the first data encoding mode.

```python
QRCodeDetailedResult.mode
```

### page

Identify the position of the particular symbol.

```python
QRCodeDetailedResult.page
```

### totalPage

Identify the total number of symbols to be concatenated in the Structured Append format.

```python
QRCodeDetailedResult.totalPage
```

### parityData

The Parity Data shall be an 8 bit byte following the Symbol Sequence Indicator. The parity data is a value obtained by XORing byte by byte the ASCII/JIS values of all the original input data before division into symbol blocks.

```python
QRCodeDetailedResult.parityData
```
