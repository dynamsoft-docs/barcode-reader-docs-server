---
layout: default-layout
title: BarcodeReader Constructor and Destructor - Dynamsoft Barcode Reader SDK Python Edition API Reference
description: This page shows the BarcodeReader Constructor and Destructor of Dynamsoft Barcode Reader SDK Python Edition.
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
license_key = 'YOUR-LICENSE-KEY'
BarcodeReader.init_license(license_key)
barcode_reader = BarcodeReader.get_instance()
# Add your code here to call decoding method, process barcode results and so on
# ...
# Recycle the barcode_reader instance to make it idle for other concurrent tasks
barcode_reader.recycle()
```

## recycle

Recycles a Dynamsoft Barcode Reader instance running on concurrent instance mode.

```python
BarcodeReader.recycle()
```

**Code Snippet**  

```python
license_key = 'YOUR-LICENSE-KEY'
BarcodeReader.init_license(license_key)
barcode_reader = BarcodeReader.get_instance()
# Add your code here to call decoding method, process barcode results and so on
# ...
# Recycle the barcode_reader instance to make it idle for other concurrent tasks
barcode_reader.recycle()
```
