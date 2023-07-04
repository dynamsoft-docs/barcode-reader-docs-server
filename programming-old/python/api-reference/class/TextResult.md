---
layout: default-layout
title: TextResult Class - Dynamsoft Barcode Reader SDK Python Edition API Reference
description: This page shows the TextResult Class of Dynamsoft Barcode Reader SDK Python Edition.
keywords: TextResult, class, api reference, python
needAutoGenerateSidebar: false
permalink: /programming/python/api-reference/class/TextResult.html
---


# TextResult
Stores the text result.

```python
public class TextResult
```  
  

## Attributes
  
| Attribute | Type |
|---------- | ---- |
| [`barcode_format`](#barcode_format) | [`EnumBarcodeFormat`]({{ site.python_enumerations }}format-enums.html#barcodeformat) |
| [`barcode_format_string`](#barcode_format_string) | *str* |
| [`barcode_format_2`](#barcode_format_2) | [`EnumBarcodeFormat_2`]({{ site.python_enumerations }}format-enums.html#barcodeformat_2) |
| [`barcode_format_string_2`](#barcode_format_string_2) | *str* |
| [`barcode_text`](#barcode_text) | *str* |
| [`barcode_bytes`](#barcode_bytes) | *bytearray* |
| [`localization_result`](#localization_result) | *[`LocalizationResult`](LocalizationResult.md)* |
| [`detailed_result`](#detailed_result) | *One of the following: [OnedDetailedResult](OnedDetailedResult.md), [PDFDetailedResult](PDFDetailedResult.md), [DataMatrixDetailedResult](DataMatrixDetailedResult.md), [AztecDetailedResult](AztecDetailedResult.md), [QRCodeDetailedResult](QRCodeDetailedResult.md)* |
| [`extended_results`](#extended_results) | *list[[`ExtendedResult`](ExtendedResult.md)]* |
| [`exception`](#exception) | *str* |
| [`is_dpm`](#is_dpm) | *int* |
| [`is_mirrored`](#is_mirrored) | *int* |


### barcode_format
Barcode type in BarcodeFormat group 1.

```python
TextResult.barcode_format
```

### barcode_format_string
Barcode type as string.

```python
TextResult.barcode_format_string
```

### barcode_format_2
Barcode type in BarcodeFormat group 2.

```python
TextResult.barcode_format_2
```

### barcode_format_string_2
`Deprecated`. Use [barcode_format_string](#barcode_format_string) instead.

```python
TextResult.barcode_format_string_2
```

### barcode_text
The barcode text

```python
TextResult.barcode_text
```

### barcode_bytes
The barcode content in a byte array.

```python
TextResult.barcode_bytes
```

### localization_result
The corresponding localization result.

```python
TextResult.localization_result
```

### detailed_result
One of the following: [OnedDetailedResult](OnedDetailedResult.md), [PDFDetailedResult](PDFDetailedResult.md), [DataMatrixDetailedResult](DataMatrixDetailedResult.md), [AztecDetailedResult](AztecDetailedResult.md), [QRCodeDetailedResult](QRCodeDetailedResult.md).

```python
TextResult.detailed_result
```

### extended_results
The extended result list

```python
TextResult.extended_results
```

### exception
Exception message

```python
TextResult.exception
```

### is_dpm
Identify whether the barcode is decoded using the DPM feature.
```python
TextResult.is_dpm
```

### is_mirrored
Identify whether the barcode is mirrored.
```python
TextResult.is_mirrored
```
