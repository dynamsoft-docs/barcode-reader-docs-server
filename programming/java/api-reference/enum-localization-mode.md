---
layout: default-layout
title: LocalizationMode - Dynamsoft Barcode Reader Java Enumerations
description: The enumeration LocalizationMode of Dynamsoft Barcode Reader describes the localization modes of the barcodes.
keywords: Localization mode
codeAutoHeight: true
---

# Enumeration LocalizationMode

`LocalizationMode` specifies the strategies used to identify the locations of barcodes within an image.

```java
@Retention(RetentionPolicy.CLASS)
public @interface EnumLocalizationMode {
    //Not supported yet. 
    int LM_AUTO = 0x01;
    //Localizes barcodes by searching for connected blocks. This algorithm usually gives best result and it is recommended to set ConnectedBlocks to the highest priority. 
    int LM_CONNECTED_BLOCKS = 0x02;
    //Localizes barcodes by groups of contiguous black-white regions. This is optimized for QRCode and DataMatrix. 
    int LM_STATISTICS = 0x04;
    //Localizes barcodes by searching for groups of lines. This is optimized for 1D and PDF417 barcodes. 
    int LM_LINES = 0x08;
    //Localizes barcodes quickly. This mode is recommended in interactive scenario.
    int LM_SCAN_DIRECTLY = 0x10;
    //Localizes barcodes by groups of marks.This is optimized for DPM codes. 
    int LM_STATISTICS_MARKS = 0x20;
    //Localizes barcodes by groups of connected blocks and lines.This is optimized for postal codes. 
    int LM_STATISTICS_POSTAL_CODE = 0x40;
    //Localizes barcodes from the centre of the image.
    int LM_CENTRE = 0x80;
    //Localizes 1D barcodes fast.
    int LM_ONED_FAST_SCAN = 0x100;
    //Reserved setting for localization mode.
    int LM_REV = 0x80000000;
    //End marker for localization mode.
    int LM_END = 0xFFFFFFFF;
    //Skips localization. 
    int LM_SKIP = 0x00;
}
```
