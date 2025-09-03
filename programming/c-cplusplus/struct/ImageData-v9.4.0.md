---
layout: default-layout
title: ImageData Struct - Dynamsoft Barcode Reader SDK C & C++ Edition
description: This page shows the ImageData struct of Dynamsoft Barcode Reader SDK C & C++ Edition.
keywords: ImageData, struct, c, c++
needAutoGenerateSidebar: false
permalink: /programming/c-cplusplus/struct/ImageData-v9.4.0.html
---


# ImageData
Stores the image data.  

## Typedefs

```cpp
typedef struct tagImageData  ImageData
```

---

## Attributes
    
| Attribute | Type |
|---------- | ---- |
| [`bytesLength`](#byteslength) | *int* |
| [`bytes`](#bytes) | *unsigned char\** |
| [`width`](#width) | *int* |
| [`height`](#height) | *int* |
| [`stride`](#stride) | *int* |
| [`format`](#format) | [`ImagePixelFormat`]({{ site.dbr_c_cpp_enumerations }}other-enums.html#imagepixelformat) |


### bytesLength
The length of the image data byte array. 
```cpp
int tagImageData::bytesLength
```
### bytes
The image data content in a byte array. 
```cpp
unsigned char* tagImageData::bytes
```

### width
The width of the image in pixels.  
```cpp
int tagImageData::width
```

### height
The height of the image in pixels.  
```cpp
int tagImageData::height
```

### stride
The stride (or scan width) of the image. 
```cpp
int tagImageData::stride
```

### format
The image pixel format used in the image byte array. 
```cpp
ImagePixelFormat tagImageData::format
```
  

