---
layout: default-layout
title: Dynamsoft Barcode Reader C++ API Reference - CBarcodeReader Constructor and Destructor
description: This page shows CBarcodeReader constructor and destructor of Dynamsoft Barcode Reader for C++ Language.
keywords: CBarcodeReader, ~CBarcodeReader, constructor and destructor, api reference, c++
needAutoGenerateSidebar: true
---

# Constructor and Destructor

  | Method               | Description |
  |----------------------|-------------|
  | [`CBarcodeReader`](#cbarcodereader) | Default constructor of `CBarcodeReader` object.|
  | [`~CBarcodeReader`](#~cbarcodereader) | Destructor of `CBarcodeReader` object.|
  | [`GetInstance`](#getinstance) | Gets an idle Dynamsoft Barcode Reader instance running on concurrent instance mode. |
  | [`Recycle`](#recycle) | Recycles a Dynamsoft Barcode Reader instance running on concurrent instance mode. |

## CBarcodeReader

Default constructor of a `CBarcodeReader` object.

```cpp
dynamsoft::dbr::CBarcodeReader::CBarcodeReader()
```



## ~CBarcodeReader

Destructor of a `CBarcodeReader` object.

```cpp
dynamsoft::dbr::CBarcodeReader::~CBarcodeReader()
```

## GetInstance

Gets an idle Dynamsoft Barcode Reader instance running on concurrent instance mode.

```cpp
static CBarcodeReader* dynamsoft::dbr::CBarcodeReader::GetInstance()
```

**Return Value**  
Returns an idle Dynamsoft Barcode Reader instance running on concurrent instance mode. If failed, returns `NULL`.

**Code Snippet**  

```cpp
char errorBuf[512];
dynamsoft::dbr::CBarcodeReader::InitLicense("YOUR-LICENSE-KEY", errorBuf, 512);
CBarcodeReader* barcodeReader = dynamsoft::dbr::CBarcodeReader::GetInstance();
// Add your code here to call decoding method, process barcode results and so on
// ...
// Recycle the barcodeReader instance to make it idle for other concurrent tasks
barcodeReader.Recycle();
```

## Recycle

Recycles a Dynamsoft Barcode Reader instance running on concurrent instance mode.

```cpp
void dynamsoft::dbr::CBarcodeReader::Recycle()
```

**Code Snippet**  

```cpp
char errorBuf[512];
dynamsoft::dbr::CBarcodeReader::InitLicense("YOUR-LICENSE-KEY", errorBuf, 512);
CBarcodeReader* barcodeReader = dynamsoft::dbr::CBarcodeReader::GetInstance();
// Add your code here to call decoding method, process barcode results and so on
// ...
// Recycle the barcodeReader instance to make it idle for other concurrent tasks
barcodeReader.Recycle();
```
