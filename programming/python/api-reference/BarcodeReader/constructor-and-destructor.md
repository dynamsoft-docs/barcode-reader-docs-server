---
layout: default-layout
title: Dynamsoft Barcode Reader Python API Reference - BarcodeReader Constructor and Destructor
description: This page shows the BarcodeReader Constructor and Destructor of Dynamsoft Barcode Reader for Python SDK.
keywords: BarcodeReader, constructor and destructor, api reference, python
needAutoGenerateSidebar: true
---

# Python API Reference - BarcodeReader Constructor and Destructor

  | Method               | Description |
  |----------------------|-------------|
  | [`BarcodeReader`](#barcodereader) | The default constructor of `BarcodeReader` object.|
  | [`__del__`](#__del__) | The default destructor of `BarcodeReader` object.|
  | [`get_instance`](#get_instance) | Gets an idle Dynamsoft Barcode Reader instance running on concurrent instance mode. |
  | [`recycle`](#recycle) | Recycles a Dynamsoft Barcode Reader instance running on concurrent instance mode. |


## BarcodeReader

### BarcodeReader()
The default constructor of a `BarcodeReader` object.

```python
BarcodeReader BarcodeReader()
```

### \_\_del\_\_()

The default destructor of a `BarcodeReader` object.

```python
reader = BarcodeReader()
del reader
```

## get_instance

Gets an idle Dynamsoft Barcode Reader instance running on concurrent instance mode.

```python
BarcodeReader.get_instance()
```

**Return Value**  
Returns an idle Dynamsoft Barcode Reader instance running on concurrent instance mode. If failed, returns `NULL`.

**Code Snippet**  

```python
#TODO
```

## recycle

Recycles a Dynamsoft Barcode Reader instance running on concurrent instance mode.

```python
BarcodeReader.recycle()
```

**Code Snippet**  

```python
#TODO
```
