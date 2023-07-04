---
layout: default-layout
title: BarcodeReaderError Class - Dynamsoft Barcode Reader SDK Python Edition API Reference
description: This page shows the BarcodeReaderError Class of Dynamsoft Barcode Reader SDK Python Edition.
keywords: BarcodeReaderError, class, api reference, python
needAutoGenerateSidebar: false
permalink: /programming/python/api-reference/class/BarcodeReaderError.html
---


# BarcodeReaderError
The exception class of BarcodeReader

```python
class BarcodeReaderError(Exception)
```  

---

## Attributes
  
| Attribute | Type |
|---------- | ----------- | 
| [`error_info`](#error_info) | *str* |

### error_info
Detailed exception information

## Methods

| Method | Description |
|---------- | ----------- | 
| [`__str__`](#__str__) | *Return detailed exception information.* |
  
### \_\_str\_\_

```python
from dbr import *

reader = BarcodeReader()
reader.init_license("t0260NwAAAHV***************")

try:
    results = reader.decode_file(r"<your barcode image file path.>")
except BarcodeReaderError as e:
    print(e)
```

 

