---
layout: default-layout
title: Dynamsoft Barcode Reader C & C++ Struct - PDF417Details
description: This page shows the PDF417Details struct of Dynamsoft Barcode Reader for C & C++ Language.
keywords: PDF417Details, struct, c, c++
needAutoGenerateSidebar: false
---


# PDF417Details
Stores the PDF417 details.

## Typedefs

```cpp
typedef struct tagPDF417Details  PDF417Details
```  

## Attributes
  
| Attribute | Type |
|---------- | ---- |
| [`moduleSize`](#modulesize) | *int* |
| [`rows`](#rows) | *int* |
| [`columns`](#columns) | *int* |
| [`errorCorrectionLevel`](#errorcorrectionlevel) | *int* |
| [`leftRowIndicatorExists`](#leftrowindicatorexists) | *int* |
| [`rightRowIndicatorExists`](#rightrowindicatorexists) | *int* |
| [`reserved`](#reserved) | *char\[24\]* |

### moduleSize

The barcode module size (the minimum bar width in pixel).

```cpp
int tagPDF417Details::moduleSize
```

### rows

The row count of the barcode.

```cpp
int tagPDF417Details::rows
```

### columns

The column count of codewords between the left and right row indicators, where the actual data and the ECC is encoded.

```cpp
int tagPDF417Details::columns
```

### errorCorrectionLevel

The error correction level of the barcode.

```cpp
int tagPDF417Details::errorCorrectionLevel
```

### leftRowIndicatorExists

Whether the left row indicator of the PDF417 code exists.

- 0: left row indicator does not exist
- 1: left row indicator exists

```cpp
int tagPDF417Details::leftRowIndicatorExists
```

### rightRowIndicatorExists

Whether the right row indicator of the PDF417 code exists.

- 0: right row indicator does not exist
- 1: right row indicator exists

```cpp
int tagPDF417Details::rightRowIndicatorExists
```

### reserved

Reserved memory for the struct. The length of this array indicates the size of the memory reserved for this struct.

```cpp
char tagPDF417Details::reserved[24]
```
