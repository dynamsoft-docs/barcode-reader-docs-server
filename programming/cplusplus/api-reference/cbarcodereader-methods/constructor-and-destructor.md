---
layout: default-layout
title: CBarcodeReader Constructor and Destructor - Dynamsoft Barcode Reader SDK C++ Edition API Reference
description: This page shows CBarcodeReader constructor and destructor of Dynamsoft Barcode Reader SDK C++ Edition.
keywords: CBarcodeReader, ~CBarcodeReader, constructor and destructor, api reference, c++
needAutoGenerateSidebar: true
permalink: /programming/cplusplus/api-reference/cbarcodereader-methods/constructor-and-destructor.html
---

# Constructor and Destructor

  | Method               | Description |
  |----------------------|-------------|
  | [`CBarcodeReader`](#cbarcodereader) | Default constructor of `CBarcodeReader` object.|
  | [`~CBarcodeReader`](#~cbarcodereader) | Destructor of `CBarcodeReader` object.|
  | [`GetInstance`](#getinstance) | Creates an instance of Dynamsoft Barcode Reader. |
  | [`Recycle`](#recycle) | Destroys an instance of Dynamsoft Barcode Reader. |

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

Creates an instance of Dynamsoft Barcode Reader.

```cpp
static CBarcodeReader* dynamsoft::dbr::CBarcodeReader::GetInstance()
```

**Return Value**  
Returns an instance of Dynamsoft Barcode Reader. If failed, returns `NULL`.

**Code Snippet**  

```cpp
//Make sure InitLicense have been called somewhere before GetInstance
CBarcodeReader* dbr = CBarcodeReader::GetInstance();
// If no instance is available right away, the application will wait until one becomes available
if(dbr != NULL)
{
    // Add your code here to call decoding method, process barcode results and so on
    // ...
    dbr->Recycle();
}
```

## Recycle

Recycles an instance of Dynamsoft Barcode Reader.

```cpp
void dynamsoft::dbr::CBarcodeReader::Recycle()
```

**Code Snippet**  

```cpp
//Make sure InitLicense have been called somewhere before GetInstance
CBarcodeReader* dbr = CBarcodeReader::GetInstance();
// If no instance is available right away, the application will wait until one becomes available
if(dbr != NULL)
{
    // Add your code here to call decoding method, process barcode results and so on
    // ...
    dbr->Recycle();
}
```
