---
layout: default-layout
title: DeblurMode - Dynamsoft Barcode Reader Python Enumerations
description: The enumeration DeblurMode of Dynamsoft Barcode Reader describes deblur modes that implemented on the localized barcodes.
keywords: Deblur mode
codeAutoHeight: true
---

# Enumeration DeblurMode

`DeblurMode` specifies the image processing algorithms applied to the localized zones containing barcodes, aimed at generating a binary image for extracting barcode data during the final phase of the barcode decoding process.

```python
class EnumDeblurMode(IntEnum):
    #Performs deblur process using the direct binarization algorithm.
    DM_DIRECT_BINARIZATION = 0x01
    #Performs deblur process using the threshold binarization algorithm.
    DM_THRESHOLD_BINARIZATION = 0x02
    #Performs deblur process using the gray equalization algorithm.
    DM_GRAY_EQUALIZATION = 0x04
    #Performs deblur process using the smoothing algorithm.
    DM_SMOOTHING = 0x08
    #Performs deblur process using the morphing algorithm.
    DM_MORPHING = 0x10
    #Performs deblur process using the deep analysis algorithm.
    DM_DEEP_ANALYSIS = 0x20
    #Performs deblur process using the sharpening algorithm.
    DM_SHARPENING = 0x40
    #Performs deblur process based on the binary image from the localization process.
    DM_BASED_ON_LOC_BIN = 0x80
    #Performs deblur process using the sharpening and smoothing algorithm.
    DM_SHARPENING_SMOOTHING = 0x100
    #Reserved setting for deblur mode.
    DM_REV = -2147483648
    #Skips the deblur process.
    DM_SKIP = 0x00
```
