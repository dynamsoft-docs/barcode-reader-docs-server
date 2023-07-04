---
layout: default-layout
title: SamplingImageData Struct - Dynamsoft Barcode Reader SDK C & C++ Edition
description: This page shows the SamplingImageData struct of Dynamsoft Barcode Reader SDK C & C++ Edition.
keywords: SamplingImageData, struct, c, c++
needAutoGenerateSidebar: false
permalink: /programming/c-cplusplus/struct/SamplingImageData.html
---


# SamplingImageData
Stores the sampling image data.

## Typedefs

```cpp
typedef struct tagSamplingImageData  SamplingImageData
```  

## Attributes
  
| Attribute | Type |
|---------- | ---- |
| [`bytes`](#bytes) | *unsigned char \** |
| [`width`](#width) | *int* |
| [`height`](#height) | *int* |


### bytes
The sampling image data in a byte array.
```cpp
unsigned char* tagSamplingImageData::bytes
```

### width
The width of the sampling image.
```cpp
int tagSamplingImageData::width
```

### height
The height of the sampling image.
```cpp
int tagSamplingImageData::height
```
