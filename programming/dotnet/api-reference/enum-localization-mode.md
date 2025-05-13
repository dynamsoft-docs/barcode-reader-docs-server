---
layout: default-layout
title: LocalizationMode - Dynamsoft Barcode Reader .NET Enumerations
description: The enumeration LocalizationMode describes the localization modes of the barcodes for .NET Edition.
keywords: Localization mode
codeAutoHeight: true
---

# Enumeration LocalizationMode

`LocalizationMode` specifies the strategies used to identify the locations of barcodes within an image.

```csharp
public enum EnumLocalizationMode
{
   /**Not supported yet. */
   LM_AUTO = 0x01,
   /**Localizes barcodes by searching for connected blocks. This algorithm usually gives best result and it is recommended to set ConnectedBlocks to the highest priority. */
   LM_CONNECTED_BLOCKS = 0x02,
   /**Localizes barcodes by groups of contiguous black-white regions. This is optimized for QRCode and DataMatrix. */
   LM_STATISTICS = 0x04,
   /**Localizes barcodes by searching for groups of lines. This is optimized for 1D and PDF417 barcodes. */
   LM_LINES = 0x08,
   /**Localizes barcodes quickly. This mode is recommended in interactive scenario. Check @ref LM for available argument settings. */
   LM_SCAN_DIRECTLY = 0x10,
   /**Localizes barcodes by groups of marks.This is optimized for DPM codes. */
   LM_STATISTICS_MARKS = 0x20,
   /**Localizes barcodes by groups of connected blocks and lines.This is optimized for postal codes. */
   LM_STATISTICS_POSTAL_CODE = 0x40,
   /**Localizes barcodes from the centre of the image. Check @ref LM for available argument settings. */
   LM_CENTRE = 0x80,
   /**Localizes 1D barcodes fast. Check @ref LM for available argument settings. */
   LM_ONED_FAST_SCAN = 0x100,
   /**Reserved setting for localization mode. */
   LM_REV = -2147483648,
   /**Placeholder value with no functional meaning.*/
   LM_END = -1,
   /**Skips localization. */
   LM_SKIP = 0x00
}
```
