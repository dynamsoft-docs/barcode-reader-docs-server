---
layout: default-layout
title: OnedDetailedResult Class - Dynamsoft Barcode Reader SDK Python Edition API Reference
description: This page shows the OnedDetailedResult Class of Dynamsoft Barcode Reader SDK Python Edition.
keywords: OnedDetailedResult, class, api reference, python
needAutoGenerateSidebar: false
permalink: /programming/python/api-reference/class/OnedDetailedResult-v7.5.0.html
---

# OnedDetailedResult
Stores the OneD code details.

```python
class OnedDetailedResult
```  

## Attributes
  
| Attribute | Type |
|---------- | ---- |
| [`module_size`](#module_size) | *int* |
| [`start_chars_bytes`](#startcharsbytes) | *bytearray* |
| [`stop_chars_bytes`](#stop_chars_bytes) | *bytearray* |
| [`check_digit_bytes`](#check_digit_bytes) | *bytearray* |


### module_size
The barcode module size (the minimum bar width in pixel).

```python
OnedDetailedResult.module_size
```

### start_chars_bytes
The start chars in a byte array.

```python
OnedDetailedResult.start_chars_bytes
```

### stop_chars_bytes
The stop chars in a byte array.

```python
OnedDetailedResult.stop_chars_bytes
```

### check_digit_bytes
The check digit chars in a byte array.

```python
OnedDetailedResult.check_digit_bytes
```
