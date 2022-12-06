---
layout: default-layout
title: BarcodeReader Constructor and Destructor - Dynamsoft Barcode Reader SDK .NET Edition API Reference
description: This page shows BarcodeReader Constructor and Destructor of Dynamsoft Barcode Reader SDK .NET Edition.
keywords: BarcodeReader, Dispose, api reference, .Net
needAutoGenerateSidebar: true
---

# .Net API Reference - BarcodeReader Constructor and Destructor

  | Method               | Description |
  |----------------------|-------------|
  | [`BarcodeReader`](#barcodereader) | Default constructor of `BarcodeReader` object.|
  | [`Dispose`](#dispose) | Destroys an instance of Dynamsoft Barcode Reader. |

---



## BarcodeReader

### BarcodeReader()

Default constructor of a `BarcodeReader` object.

```C#
Dynamsoft.Barcode.BarcodeReader.BarcodeReader()
```

### BarcodeReader(string productKey)

Constructor with a given product key.

```C#
Dynamsoft.Barcode.BarcodeReader.BarcodeReader(string productKey)
```

#### Parameters
`[in] productKey` <*string*> : Product key. 

### BarcodeReader(string modulePath, string productKey)

Constructor with a given product key and a given path to load DLLs.

```C#
Dynamsoft.Barcode.BarcodeReader.BarcodeReader(string modulePath, string productKey)
```

#### Parameters
`[in] modulePath` <*string*> : The path where you store these DLLs.  
`[in] productKey` <*string*> : Product key. 




## Dispose

### Dispose()

Destroys an instance of Dynamsoft Barcode Reader.

```C#
void Dynamsoft.Barcode.BarcodeReader.Dispose() 
```