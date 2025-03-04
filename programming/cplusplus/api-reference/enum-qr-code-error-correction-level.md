---
layout: default-layout
title: QRCodeErrorCorrectionLevel - Dynamsoft Barcode Reader Enumerations
description: The enumeration QRCodeErrorCorrectionLevel of Dynamsoft Barcode Reader describes the error correction level when processing the QR code.
keywords: QR code error correction level
codeAutoHeight: true
---

# Enumeration QRCodeErrorCorrectionLevel

`QRCodeErrorCorrectionLevel` describes the error correction level when processing the QR code.

<div class="sample-code-prefix template2"></div>
   >- C++
   >
>
```cpp
typedef enum QRCodeErrorCorrectionLevel
{
   /**Error Correction Level H (high) */
   QRECL_ERROR_CORRECTION_H,
   /**Error Correction Level L (low) */
   QRECL_ERROR_CORRECTION_L,
   /**Error Correction Level M (medium-low) */
   QRECL_ERROR_CORRECTION_M,
   /**Error Correction Level Q (medium-high) */
   QRECL_ERROR_CORRECTION_Q
}QRCodeErrorCorrectionLevel;
```
