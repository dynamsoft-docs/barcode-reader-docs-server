---
layout: default-layout
title: DeblurMode - Dynamsoft Barcode Reader Java Enumerations
description: The enumeration DeblurMode of Dynamsoft Barcode Reader describes deblur modes that implemented on the localized barcodes.
keywords: Deblur mode
codeAutoHeight: true
---

# Enumeration DeblurMode

`DeblurMode` specifies the image processing algorithms applied to the localized zones containing barcodes, aimed at generating a binary image for extracting barcode data during the final phase of the barcode decoding process.

```java
@Retention(RetentionPolicy.CLASS)
public @interface EnumDeblurMode {
    //Performs deblur process using the direct binarization algorithm.
    int DM_DIRECT_BINARIZATION = 0x01;
    //Performs deblur process using the threshold binarization algorithm.
    int DM_THRESHOLD_BINARIZATION = 0x02;
    //Performs deblur process using the gray equalization algorithm.
    int DM_GRAY_EQUALIZATION = 0x04;
    //Performs deblur process using the smoothing algorithm.
    int DM_SMOOTHING = 0x08;
    //Performs deblur process using the morphing algorithm.
    int DM_MORPHING = 0x10;
    //Performs deblur process using the deep analysis algorithm.
    int DM_DEEP_ANALYSIS = 0x20;
    //Performs deblur process using the sharpening algorithm.
    int DM_SHARPENING = 0x40;
    //Performs deblur process based on the binary image from the localization process.
    int DM_BASED_ON_LOC_BIN = 0x80;
    //Performs deblur process using the sharpening and smoothing algorithm.
    int DM_SHARPENING_SMOOTHING = 0x100;
    //Performs deblur process using the neural network algorithm.
    int DM_NEURAL_NETWORK = 0x200;
    //Reserved setting for deblur mode.
    int DM_REV = 0x80000000;
    //End marker for deblur mode.
    int DM_END = 0xFFFFFFFF;
    //Skips the deblur process.
    int DM_SKIP = 0x00;
}
```
