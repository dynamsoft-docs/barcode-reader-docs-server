---
layout: default-layout
title: Other Enumerations - Dynamsoft Barcode Reader SDK Java Edition
description: This article shows other Enumerations of Dynamsoft Barcode Reader v7.6.0 for Java Programming Laguage
keywords: ImagePixelFormat, QRCodeErrorCorrectionLevel, other enumeration, enumeration
needGenerateH3Content: false
permalink: /programming/java/api-reference/enumeration/other-enums-v7.6.0.html
---


# Other Enumeration

  | Enumeration | Description |
  |-------------|-------------|
  | [`ImagePixelFormat`](#imagepixelformat) | Describes the image pixel format. |
  | [`QRCodeErrorCorrectionLevel`](#qrcodeerrorcorrectionlevel) | Describes the QR Code error correction level.   |
  

## ImagePixelFormat
Describes the image pixel format.


### Declarations
   



```java
class EnumImagePixelFormat
```





### Members
   
| Member | Value | Description |
| --------------------------  | ----- | ----------- |
| IPF_BINARY | 0 | 0: Black, 1: White |
| IPF_BINARYINVERTED | 1 | 0: Black, 1: White |
| IPF_GRAYSCALED | 2 | 8 bit gray |
| IPF_NV21 | 3 | NV21 |
| IPF_RGB_565 | 4 | 16bit with RGB channel order stored in memory from high to low address |
| IPF_RGB_555 | 5 | 16bit with RGB channel order stored in memory from high to low address |
| IPF_RGB_888 | 6 | 24bit with RGB channel order stored in memory from high to low address |
| IPF_ARGB_8888 | 7 | 32bit with ARGB channel order stored in memory from high to low address |
| IPF_RGB_161616 | 8 | 48bit with RGB channel order stored in memory from high to low address |
| IPF_ARGB_16161616 | 9 | 64bit with ARGB channel order stored in memory from high to low address |
| IPF_ABGR_8888 | 10 | 32bit with ABGR channel order stored in memory from high to low address |
| IPF_ABGR_16161616 | 11 | 64bit with ABGR channel order stored in memory from high to low address |
| IPF_BGR_888 | 12 | 24bit with BGR channel order stored in memory from high to low address |





## QRCodeErrorCorrectionLevel
Describes the QR Code error correction level.  


### Declarations
   


```java
class EnumQRCodeErrorCorrectionLevel
```





### Members
   
| Member | Value | Description |
| --------------------------  | ----- | ----------- |
| QRECL_ERROR_CORRECTION_H | 0 | Error Correction Level H (high) |
| QRECL_ERROR_CORRECTION_L | 1 | Error Correction Level L (low) |
| QRECL_ERROR_CORRECTION_M | 2 | Error Correction Level M (medium-low) |
| QRECL_ERROR_CORRECTION_Q | 3 | Error Correction Level Q (medium-high) |

