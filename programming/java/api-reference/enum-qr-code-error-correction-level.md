---
layout: default-layout
title: QRCodeErrorCorrectionLevel - Dynamsoft Barcode Reader Java Enumerations
description: Reference for the QRCodeErrorCorrectionLevel enumeration in DBR Java Edition, defining the four error correction levels (L, M, Q, H) used when encoding or decoding QR codes.
keywords: QR code error correction level
codeAutoHeight: true
---

# Enumeration QRCodeErrorCorrectionLevel

`QRCodeErrorCorrectionLevel` describes the error correction level when processing the QR code.

```java
@Retention(RetentionPolicy.CLASS)
public @interface EnumQRCodeErrorCorrectionLevel {
    //Error Correction Level H (high) 
    int QRECL_ERROR_CORRECTION_H = 0;
    //Error Correction Level L (low) 
    int QRECL_ERROR_CORRECTION_L = 1;
    //Error Correction Level M (medium-low) 
    int QRECL_ERROR_CORRECTION_M = 2;
    //Error Correction Level Q (medium-high) 
    int QRECL_ERROR_CORRECTION_Q = 3;
}
```
