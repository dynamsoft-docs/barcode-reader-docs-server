---
layout: default-layout
title: QRCodeDetails Struct - Dynamsoft Barcode Reader SDK C & C++ Edition
description: This page shows the QRCodeDetails struct of Dynamsoft Barcode Reader SDK C & C++ Edition.
keywords: QRCodeDetails, struct, c, c++
needAutoGenerateSidebar: false
permalink: /programming/c-cplusplus/struct/QRCodeDetails-v8.1.0.html
---


# QRCodeDetails
Stores the QRCode details.  

## Typedefs

```cpp
typedef struct tagQRCodeDetails  QRCodeDetails
```  

## Attributes
  
| Attribute | Type |
|---------- | ---- |
| [`moduleSize`](#modulesize) | *int* |
| [`rows`](#rows) | *int* |
| [`columns`](#columns) | *int* |
| [`errorCorrectionLevel`](#errorcorrectionlevel) | [`QRCodeErrorCorrectionLevel`]({{ site.c_cpp_enumerations }}other-enums.html#qrcodeerrorcorrectionlevel) |
| [`version`](#version) | *int* |
| [`model`](#model) | *int* |
| [`reserved`](#reserved) | *char\[32\]* |


### moduleSize
The barcode module size (the minimum bar width in pixel).  
```cpp
int tagQRCodeDetails::moduleSize
```

### rows
The row count of the barcode.  
```cpp
int tagQRCodeDetails::rows
```

### columns
The column count of the barcode. 
```cpp
int tagQRCodeDetails::columns
```

### errorCorrectionLevel
The error correction level of the barcode.  
```cpp
QRCodeErrorCorrectionLevel tagQRCodeDetails::errorCorrectionLevel
```

### version
The version of the QR Code.
```cpp
int tagQRCodeDetails::version
```

### model
Number of the models.
```cpp
int tagQRCodeDetails::model
```

### reserved
Reserved memory for the struct. The length of this array indicates the size of the memory reserved for this struct.
```cpp
char tagQRCodeDetails::reserved[32]
```

