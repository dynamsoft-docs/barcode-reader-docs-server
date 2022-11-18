---
layout: default-layout
title: Dynamsoft Barcode Reader Python API Reference - PDFDetailedResult Class
description: This page shows the PDFDetailedResult Class of Dynamsoft Barcode Reader for Python SDK.
keywords: PDFDetailedResult, class, api reference, python
needAutoGenerateSidebar: false
---


# PDFDetailedResult
Stores the PDF417 details.

```python
class PDFDetailedResult
```  

## Attributes
  
| Attribute | Type |
|---------- | ---- |
| [`module_size`](#module_size) | *int* |
| [`rows`](#rows) | *int* |
| [`columns`](#columns) | *int* |
| [`error_correction_level`](#error_correction_level) | *int* |
| [`has_left_row_indicator`](#has_left_row_indicator) | *int* |
| [`has_right_row_indicator`](#has_right_row_indicator) | *int* |

### module_size

The barcode module size (the minimum bar width in pixel).

```python
PDFDetailedResult.module_size
```

### rows

The row count of the barcode.

```python
PDFDetailedResult.rows
```

### columns

The column count of codewords between the left and right row indicators, where the actual data and the ECC is encoded.

```python
PDFDetailedResult.columns
```

### error_correction_level

The error correction level of the barcode.

```python
PDFDetailedResult.error_correction_level
```

### has_left_row_indicator

Whether the left row indicator of the PDF417 code exists.

- 0: left row indicator does not exist
- 1: left row indicator exists

```python
PDFDetailedResult.has_left_row_indicator
```

### has_right_row_indicator

Whether the right row indicator of the PDF417 code exists.

- 0: right row indicator does not exist
- 1: right row indicator exists

```python
PDFDetailedResult.has_right_row_indicator
```
