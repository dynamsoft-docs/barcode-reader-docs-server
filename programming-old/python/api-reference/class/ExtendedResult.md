---
layout: default-layout
title: ExtendedResult Class - Dynamsoft Barcode Reader SDK Python Edition API Reference
description: This page shows the ExtendedResult Class of Dynamsoft Barcode Reader SDK Python Edition.
keywords: ExtendedResult, class, api reference, python
needAutoGenerateSidebar: false
permalink: /programming/python/api-reference/class/ExtendedResult.html
---


# ExtendedResult
Stores the extended result. 

```python
class ExtendedResult
```  


## Attributes
  
| Attribute | Type |
|---------- | ---- |
| [`result_type`](#result_type) | [`EnumResultType`]({{ site.python_enumerations }}result-enums.html#resulttype) |
| [`barcode_format`](#barcode_format) | [`EnumBarcodeFormat`]({{ site.python_enumerations }}format-enums.html#barcodeformat) |
| [`barcode_format_string`](#barcode_format_string) | *str* |
| [`barcode_format_2`](#barcode_format_2) | [`EnumBarcodeFormat_2`]({{ site.python_enumerations }}format-enums.html#barcodeformat_2) |
| [`barcode_format_string_2`](#barcode_format_string_2) | *str* | 
| [`confidence`](#confidence) | *int* | 
| [`bytes`](#bytes) | *bytearray* | 
| [`accompanying_text_bytes`](#accompanying_text_bytes) | *bytearray* | 
| [`deformation`](#deformation) | *int* | 
| [`detailed_result`](#detailed_result) | *One of the following: [OnedDetailedResult](OnedDetailedResult.md), [PDFDetailedResult](PDFDetailedResult.md), [DataMatrixDetailedResult](DataMatrixDetailedResult.md), [AztecDetailedResult](AztecDetailedResult.md), [QRCodeDetailedResult](QRCodeDetailedResult.md)* |
| [`sampling_image`](#sampling_image) | *[`SamplingImageData`](SamplingImageData.md)* |
| [`clarity`](#clarity) | *int* | 

### result_type
Extended result type. 

```python
ExtendedResult.result_type
```

### barcode_format
Barcode type in BarcodeFormat group 1. 

```python
ExtendedResult.barcode_format
```

### barcode_format_string
Barcode type as string.

```python
ExtendedResult.barcode_format_string
```

### barcode_format_2
Barcode type in BarcodeFormat group 2.

```python
ExtendedResult.barcode_format_2
```
 
### barcode_format_string_2
`Deprecated`. Use [barcode_format_string](#barcode_format_string) instead.

```python
ExtendedResult.barcode_format_string_2
```

### confidence
The confidence of the result.

```python
ExtendedResult.confidence
```

### bytes
The content in a byte array.

```python
ExtendedResult.bytes
```

### accompanying_text_bytes
The accompanying text content in a byte array.

```python
ExtendedResult.accompanying_text_bytes
```

### deformation
The deformation value.

```python
ExtendedResult.deformation
```

### detailed_result
One of the following: [OnedDetailedResult](OnedDetailedResult.md), [PDFDetailedResult](PDFDetailedResult.md), [DataMatrixDetailedResult](DataMatrixDetailedResult.md), [AztecDetailedResult](AztecDetailedResult.md), [QRCodeDetailedResult](QRCodeDetailedResult.md).

```python
ExtendedResult.detailed_result
```

### sampling_image
The sampling image info.

```python
ExtendedResult.sampling_image
```
 
### clarity
The clarity of the barcode zone in percentage.

```python
ExtendedResult.clarity
```
