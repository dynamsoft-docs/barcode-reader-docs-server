---
layout: default-layout
title: Parameter Mode Enumerations - Dynamsoft Barcode Reader .NET Edition
description: This article shows Parameter Mode Enumerations of Dynamsoft Barcode Reader.
keywords: BarcodeColourMode, BarcodeComplementMode, BinarizationMode, ColourClusteringMode, ColourConversionMode, ConflictMode, DeblurMode, DeformationResistingMode, DPMCodeReadingMode, GrayscaleTransformationMode, ImagePreprocessingMode, LocalizationMode, PDFReadingMode, RegionPredetectionMode, ScaleUpMode, TerminatePhase, TextFilterMode, TextureDetectionMode, parameter mode enumeration, enumeration
needGenerateH3Content: false
permalink: /programming/dotnet/api-reference/enumeration/parameter-mode-enums-v8.6.0.html
---

# Parameter Mode Enumeration

  | Enumeration | Description |
  |-------------|-------------|
  | [`BarcodeColourMode`](#barcodecolourmode) | Describes the barcode colour mode. |
  | [`BarcodeComplementMode`](#barcodecomplementmode) | Describes the barcode complement mode. |
  | [`BinarizationMode`](#binarizationmode) | Describes the binarization mode. |
  | [`ColourClusteringMode`](#colourclusteringmode) | Describes the colour clustering mode. |
  | [`ColourConversionMode`](#colourconversionmode) | Describes the colour conversion mode. |
  | [`ConflictMode`](#conflictmode) | Describes the conflict mode. |
  | [`DeblurMode`](#deblurmode) | Describes the deblur mode. |
  | [`DeformationResistingMode`](#deformationresistingmode) | Describes the deformation resisting mode. |
  | [`DPMCodeReadingMode`](#dpmcodereadingmode) | Describes the DPM code reading mode. |
  | [`GrayscaleTransformationMode`](#grayscaletransformationmode) | Describes the grayscale transformation mode. |
  | [`ImagePreprocessingMode`](#imagepreprocessingmode) | Describes the image preprocessing mode. |
  | [`LocalizationMode`](#localizationmode) | Describes the localization mode. | 
  | [`PDFReadingMode`](#pdfreadingmode) | Describes the PDF reading mode.  |
  | [`RegionPredetectionMode`](#regionpredetectionmode) | Describes the region predetection mode. |
  | [`ScaleUpMode`](#scaleupmode) | Describes the scale up mode. |
  | [`TerminatePhase`](#terminatephase) | Describes the terminate phase. |
  | [`TextFilterMode`](#textfiltermode) | Describes the text filter mode. |
  | [`TextureDetectionMode`](#texturedetectionmode) | Describes the texture detection mode. | 


## BarcodeColourMode
Describes the barcode colour mode.


### Declarations
   
```csharp
enum Dynamsoft.DBR.EnumBarcodeColourMode
```





### Members
   
| Member | Value | Description | Valid Argument(s) |
| --------------------------  | ----- | ----------- | ----------------- |
| BICM_SKIP | 0x00 | Skips the barcode colour operation. | `N/A` |
| BICM_DARK_ON_LIGHT | 0x01 | Dark items on a light background. | [`LightReflection`]({{ site.parameters_reference }}barcode-colour-modes.html#lightreflection) |
| BICM_LIGHT_ON_DARK  | 0x02 | Light items on a dark background. **Not supported yet**.  | `N/A` |
| BICM_DARK_ON_DARK  | 0x04 | Dark items on a dark background. **Not supported yet**.  | `N/A` |
| BICM_LIGHT_ON_LIGHT  | 0x08 | Light items on a light background. **Not supported yet**.  | `N/A` |
| BICM_DARK_LIGHT_MIXED  | 0x10 | The background is mixed by dark and light. **Not supported yet**.  | `N/A` |
| BICM_DARK_ON_LIGHT_DARK_SURROUNDING  | 0x20 | Dark item on a light background surrounded by dark.  | [`LightReflection`]({{ site.parameters_reference }}barcode-colour-modes.html#lightreflection) |







## BarcodeComplementMode
Describes the barcode complement mode.


### Declarations
   
```csharp
enum Dynamsoft.DBR.EnumBarcodeComplementMode
```





### Members
   
| Member | Value | Description |
| --------------------------  | ----- | ----------- |
| BCM_SKIP | 0x00 | Skips the barcode complement. |
| BCM_AUTO | 0x01 | **Not supported yet.** |
| BCM_GENERAL | 0x02 | Complements the barcode using the general algorithm. |







## BinarizationMode
Describes the binarization mode.


### Declarations
   
```csharp
enum Dynamsoft.DBR.EnumBinarizationMode
```





### Members
   
| Member | Value | Description | Valid Argument(s) |
| --------------------------  | ----- | ----------- | ----------------- |
| BM_SKIP | 0x00 | Skips the binarization. | `N/A` |
| BM_AUTO | 0x01 | **Not supported yet.** | `N/A` |
| BM_LOCAL_BLOCK | 0x02 | Binarizes the image based on the local block. | [`BlockSizeX`]({{ site.parameters_reference }}binarization-modes.html#blocksizex)<br>[`BlockSizeY`]({{ site.parameters_reference }}binarization-modes.html#blocksizey)<br>[`EnableFillBinaryVacancy`]({{ site.parameters_reference }}binarization-modes.html#enablefillbinaryvacancy)<br>[`ImagePreprocessingModesIndex`]({{ site.parameters_reference }}binarization-modes.html#imagepreprocessingmodesindex)<br>[`ThresholdCompensation`]({{ site.parameters_reference }}binarization-modes.html#thresholdcompensation)<br> |
| BM_THRESHOLD | 0x04 | Performs image binarization based on the given threshold. | [`BinarizationThreshold`]({{ site.parameters_reference }}binarization-modes.html#binarizationThreshold)<br>[`ImagePreprocessingModesIndex`]({{ site.parameters_reference }}binarization-modes.html#imagepreprocessingmodesindex) |







## ColourClusteringMode
Describes the colour clustering mode.


### Declarations
   
```csharp
enum Dynamsoft.DBR.EnumColourClusteringMode
```





### Members
   
| Member | Value | Description | Valid Argument(s) |
| --------------------------  | ----- | ----------- | ----------------- |
| CCM_SKIP | 0x00 | Skips the colour clustering. | `N/A` |
| CCM_AUTO | 0x01 | **Not supported yet.** | `N/A` |
| CCM_GENERAL_HSV | 0x02 | Clusters colours using the general algorithm based on HSV. | [`Sensitivity`]({{ site.parameters_reference }}colour-clustering-modes.html#sensitivity) |







## ColourConversionMode
Describes the colour conversion mode.


### Declarations
   
```csharp
enum Dynamsoft.DBR.EnumColourConversionMode
```





### Members
   
| Member | Value | Description | Valid Argument(s) |
| --------------------------  | ----- | ----------- | ----------------- |
| CICM_SKIP | 0x00 | Skip the colour conversion. | `N/A` |
| CICM_GENERAL | 0x01 | Converts a colour image to a grayscale image using the general algorithm. | [`BlueChannelWeight`]({{ site.parameters_reference }}colour-conversion-modes.html#bluechannelweight)<br>[`GreenChannelWeight`]({{ site.parameters_reference }}colour-conversion-modes.html#greenchannelweight)<br>[`RedChannelWeight`]({{ site.parameters_reference }}colour-conversion-modes.html#redchannelweight) |







## ConflictMode
Describes the conflict mode.


### Declarations
   
```csharp
enum Dynamsoft.DBR.EnumConflictMode
```





### Members
   
| Member | Value | Description |
| --------------------------  | ----- | ----------- |
| CM_IGNORE | 0x01 | Ignores new settings and inherits the previous settings. |
| CM_OVERWRITE | 0x02 | Overwrites the old settings with new settings. |







## DeblurMode
Describes the deblur mode.


### Declarations
   
```csharp
enum Dynamsoft.DBR.EnumDeblurMode
```





### Members
   
| Member | Value | Description |
| --------------------------  | ----- | ----------- |
| DM_SKIP | 0x00 | Skips the deblur process. |
| DM_DIRECT_BINARIZATION | 0x01 | Performs deblur process using the direct binarization algorithm. |
| DM_THRESHOLD_BINARIZATION | 0x02 | Performs deblur process using the threshold binarization algorithm. |
| DM_GRAY_EQUALIZATION | 0x04 | Performs deblur process using the gray equalization algorithm.|
| DM_SMOOTHING | 0x08 | Performs deblur process using the smoothing algorithm.|
| DM_MORPHING | 0x10 | Performs deblur process using the morphing algorithm.|
| DM_DEEP_ANALYSIS | 0x20 | Performs deblur process using the deep analysis algorithm. |
| DM_SHARPENING | 0x40 | Performs deblur process using the sharpening algorithm. |
| DM_BASED_ON_LOC_BIN | 0x80 | Performs deblur process based on the binary image from the localization process. |
| DM_SHARPENING_SMOOTHING | 0x100 | Performs deblur process using the sharpening and smoothing algorithm.|







## DeformationResistingMode
Describes the deformation resisting mode.


### Declarations
   
```csharp
enum Dynamsoft.DBR.EnumDeformationResistingMode
```





### Members
   
| Member | Value | Description | Valid Argument(s) |
| --------------------------  | ----- | ----------- | ----------------- |
| DRM_SKIP | 0x00 | Skip the deformation resisting. | `N/A` |
| DRM_AUTO | 0x01 | **Not supported yet.** | `N/A` |
| DRM_GENERAL | 0x02 | Resists deformation using the general algorithm. | [`Level`]({{ site.parameters_reference }}deformation-resisting-modes.html#level) |







## DPMCodeReadingMode
Describes the DPM code reading mode.

### Declarations
   
```csharp
enum Dynamsoft.DBR.EnumDPMCodeReadingMode
```





### Members
   
| Member | Value | Description |
| --------------------------  | ----- | ----------- |
| DPMCRM_SKIP | 0x00 | Skip the DPM code reading. |
| DPMCRM_AUTO | 0x01 | **Not supported yet.** |
| DPMCRM_GENERAL | 0x02 | Reads DPM code using the general algorithm. |







## GrayscaleTransformationMode
Describes the grayscale transformation mode.


### Declarations
   
```csharp
enum Dynamsoft.DBR.EnumGrayscaleTransformationMode
```





### Members
   
| Member | Value | Description |
| --------------------------  | ----- | ----------- |
| GTM_SKIP  | 0x00 | Skips grayscale transformation. |
| GTM_INVERTED  | 0x01 | Transforms to inverted grayscale. Recommended for light on dark images. |
| GTM_ORIGINAL | 0x02 | Keeps the original grayscale. Recommended for dark on light images. |







## ImagePreprocessingMode
Describes the image preprocessing mode.

### Declarations
   
```csharp
enum Dynamsoft.DBR.EnumImagePreprocessingMode
```





### Members
   
| Member | Value | Description | Valid Argument(s) |
| --------------------------  | ----- | ----------- | ----------------- |
| IPM_SKIP | 0x00 | Skips image preprocessing. | `N/A` |
| IPM_AUTO | 0x01 | **Not supported yet.** | `N/A` |
| IPM_GENERAL | 0x02 | Takes the unpreprocessed image for following operations. | `N/A` |
| IPM_GRAY_EQUALIZE | 0x04 | Preprocesses the image using the gray equalization algorithm. | [`Sensitivity`]({{ site.parameters_reference }}image-preprocessing-modes.html#sensitivity) |
| IPM_GRAY_SMOOTH | 0x08 | Preprocesses the image using the gray smoothing algorithm. | [`SmoothBlockSizeX`]({{ site.parameters_reference }}image-preprocessing-modes.html#smoothblocksizex)<br>[`SmoothBlockSizeY`]({{ site.parameters_reference }}image-preprocessing-modes.html#smoothblocksizey) |
| IPM_SHARPEN_SMOOTH | 0x10 | Preprocesses the image using the sharpening and smoothing algorithm. | [`SmoothBlockSizeX`]({{ site.parameters_reference }}image-preprocessing-modes.html#smoothblocksizex)<br>[`SmoothBlockSizeY`]({{ site.parameters_reference }}image-preprocessing-modes.html#smoothblocksizey)<br>[`SharpenBlockSizeX`]({{ site.parameters_reference }}image-preprocessing-modes.html#sharpenblocksizex)<br>[`SharpenBlockSizeY`]({{ site.parameters_reference }}image-preprocessing-modes.html#sharpenblocksizey) |
| IPM_MORPHOLOGY  | 0x20 | Preprocesses the image using the morphology algorithm. | [`MorphOperation`]({{ site.parameters_reference }}image-preprocessing-modes.html#morphoperation)<br>[`MorphShape`]({{ site.parameters_reference }}image-preprocessing-modes.html#morphshape)<br>[`MorphOperationKernelSizeX`]({{ site.parameters_reference }}image-preprocessing-modes.html#morphoperationkernelsizex)<br>[`MorphOperationKernelSizeY`]({{ site.parameters_reference }}image-preprocessing-modes.html#morphoperationkernelsizey) |







## LocalizationMode
Describes the localization mode.


### Declarations
   
```csharp
enum Dynamsoft.DBR.EnumLocalizationMode
```





### Members
   
| Member | Value | Description | Valid Argument(s) |
| --------------------------  | ----- | ----------- | ----------------- |
| LM_SKIP | 0x00 | Skips localization. | `N/A` |
| LM_AUTO  | 0x01 | Not supported yet. | `N/A` |
| LM_CONNECTED_BLOCKS | 0x02 | Localizes barcodes by searching for connected blocks. This algorithm usually gives best result and it is recommended to set ConnectedBlocks to the highest priority. | `N/A` |
| LM_STATISTICS | 0x04 | Localizes barcodes by groups of contiguous black-white regions. This is optimized for QRCode and DataMatrix. | `N/A` |
| LM_LINES | 0x08 | Localizes barcodes by searching for groups of lines. This is optimized for 1D and PDF417 barcodes. | `N/A` |
| LM_SCAN_DIRECTLY | 0x10 |  Localizes barcodes quickly. This mode is recommended in interactive scenario. | [`ScanStride`]({{ site.parameters_reference }}localization-modes.html#scanstride)<br>[`ScanDirection`]({{ site.parameters_reference }}localization-modes.html#scandirection) |
| LM_STATISTICS_MARKS | 0x20 | Localizes barcodes by groups of marks.This is optimized for DPM codes. | `N/A` |
| LM_STATISTICS_POSTAL_CODE | 0x40 | Localizes barcodes by groups of connected blocks and lines.This is optimized for postal codes. | `N/A` |
| LM_CENTRE | 0x80 | Localizes barcodes from the centre of the image. | `N/A` |







## PDFReadingMode
Describes the PDF reading mode. 


### Declarations
   
```csharp
enum Dynamsoft.DBR.EnumPDFReadingMode
```






### Members
   
| Member | Value | Description |
| --------------------------  | ----- | ----------- |
| PDFRM_AUTO | 0x01 | Lets the library choose the reading mode automatically. |
| PDFRM_VECTOR | 0x02 | Detects barcode from vector data in PDF file. |
| PDFRM_RASTER | 0x04 | Converts the PDF file to image(s) first, then perform barcode recognition. |






## RegionPredetectionMode
Describes the region predetection mode.


### Declarations
   
```csharp
enum Dynamsoft.DBR.EnumRegionPredetectionMode
```





### Members
   
| Member | Value | Description | Valid Argument(s) |
| --------------------------  | ----- | ----------- | ----------------- |
| RPM_SKIP | 0x00 | Skips region detection. | `N/A` |
| RPM_AUTO | 0x01 | Lets the library choose an algorithm automatically to detect region. | `N/A` |
| RPM_GENERAL | 0x02 | Takes the whole image as a region. | `N/A` |
| RPM_GENERAL_RGB_CONTRAST | 0x04 | Detects region using the general algorithm based on RGB colour contrast. | [`MinImageDimension`]({{ site.parameters_reference }}region-predetection-modes.html#minimagedimension)<br>[`Sensitivity`]({{ site.parameters_reference }}region-predetection-modes.html#sensitivity)<br>[`SpatialIndexBlockSize`]({{ site.parameters_reference }}region-predetection-modes.html#spatialindexblocksize) |
| RPM_GENERAL_GRAY_CONTRAST | 0x08 | Detects region using the general algorithm based on gray contrast. | [`MinImageDimension`]({{ site.parameters_reference }}region-predetection-modes.html#minimagedimension)<br>[`Sensitivity`]({{ site.parameters_reference }}region-predetection-modes.html#sensitivity)<br>[`SpatialIndexBlockSize`]({{ site.parameters_reference }}region-predetection-modes.html#spatialindexblocksize) |
| RPM_GENERAL_HSV_CONTRAST | 0x10 | Detects region using the general algorithm based on HSV colour contrast. | [`AspectRatioRange`]({{ site.parameters_reference }}region-predetection-modes.html#aspectratiorange)<br>[`FindAccurateBoundary`]({{ site.parameters_reference }}region-predetection-modes.html#findaccurateboundary)<br>[`ForeAndBackgroundColours`]({{ site.parameters_reference }}region-predetection-modes.html#foreandbackgroundcolours)<br>[`HeightRange`]({{ site.parameters_reference }}region-predetection-modes.html#heightrange)<br>[`MinImageDimension`]({{ site.parameters_reference }}region-predetection-modes.html#minimagedimension)<br>[`RelativeBarcodeRegions`]({{ site.parameters_reference }}region-predetection-modes.html#relativebarcoderegions)<br>[`Sensitivity`]({{ site.parameters_reference }}region-predetection-modes.html#sensitivity)<br>[`SpatialIndexBlockSize`]({{ site.parameters_reference }}region-predetection-modes.html#spatialindexblocksize)<br>[`WidthRange`]({{ site.parameters_reference }}region-predetection-modes.html#widthrange) |







## ScaleUpMode
Describes the scale up mode. 


### Declarations
   
```csharp
enum Dynamsoft.DBR.EnumScaleUpMode
```





### Members
   
| Member | Value | Description | Valid Argument(s) |
| --------------------------  | ----- | ----------- | ----------------- |
| SUM_SKIP | 0x00 | Skip the scale-up process. | `N/A` |
| SUM_AUTO | 0x01 | The library chooses an interpolation method automatically to scale up. | `N/A` |
| SUM_LINEAR_INTERPOLATION | 0x02 | Scales up using the linear interpolation method. | [`AcuteAngleWithXThreshold`]({{ site.parameters_reference }}scale-up-modes.html#acuteanglewithxthreshold)<br>[`ModuleSizeThreshold`]({{ site.parameters_reference }}scale-up-modes.html#modulesizethreshold)<br>[`TargetModuleSize`]({{ site.parameters_reference }}scale-up-modes.html#targetmodulesize) |
| SUM_NEAREST_NEIGHBOUR_INTERPOLATION | 0x04 | Scales up using the nearest-neighbour interpolation method. | [`AcuteAngleWithXThreshold`]({{ site.parameters_reference }}scale-up-modes.html#acuteanglewithxthreshold)<br>[`ModuleSizeThreshold`]({{ site.parameters_reference }}scale-up-modes.html#modulesizethreshold)<br>[`TargetModuleSize`]({{ site.parameters_reference }}scale-up-modes.html#targetmodulesize) |







## TerminatePhase
Describes the terminate phase.


### Declarations
   
```csharp
enum Dynamsoft.DBR.EnumTerminatePhase
```





### Members
   
| Member | Value | Description |
| --------------------------  | ----- | ----------- |
| TP_REGION_PREDETECTED | 0x01 | Exits the barcode reading algorithm after the region predetection is done. |
| TP_IMAGE_PREPROCESSED | 0x02 | Exits the barcode reading algorithm after the region predetection and image pre-processing is done. |
| TP_IMAGE_BINARIZED | 0x04 | Exits the barcode reading algorithm after the region predetection, image pre-processing, and image binarization are done. |
| TP_BARCODE_LOCALIZED | 0x08 | Exits the barcode reading algorithm after the region predetection, image pre-processing, image binarization, and barcode localization are done. |
| TP_BARCODE_TYPE_DETERMINED | 0x10 | Exits the barcode reading algorithm after the region predetection, image pre-processing, image binarization, barcode localization, and barcode type determining are done. |
| TP_BARCODE_RECOGNIZED | 0x20 | Exits the barcode reading algorithm after the region predetection, image pre-processing, image binarization, barcode localization, barcode type determining, and barcode recognition are done. |








## TextFilterMode
Describes the text filter mode.

### Declarations
   
```csharp
enum Dynamsoft.DBR.EnumTextFilterMode
```





### Members
   
| Member | Value | Description | Valid Argument(s) |
| --------------------------  | ----- | ----------- | ----------------- |
| TFM_SKIP | 0x00 | Skip the text filtering. | `N/A` |
| TFM_AUTO | 0x01 | **Not supported yet.** | `N/A` |
| TFM_GENERAL_CONTOUR | 0x02 | Filters text using the general algorithm based on contour. | [`MinImageDimension`]({{ site.parameters_reference }}text-filter-modes.html#minimagedimension)<br>[`Sensitivity`]({{ site.parameters_reference }}text-filter-modes.html#sensitivity) |







## TextureDetectionMode
Describes the texture detection mode.


### Declarations
   
```csharp
enum Dynamsoft.DBR.EnumTextureDetectionMode
```





### Members
   
| Member | Value | Description | Valid Argument(s) |
| --------------------------  | ----- | ----------- | ----------------- |
| TDM_SKIP  | 0x00 | Skips texture detection. | `N/A` |
| TDM_AUTO  | 0x01 | Not supported yet. | `N/A` |
| TDM_GENERAL_WIDTH_CONCENTRATION  | 0x02 | Detects texture using the general algorithm. | [`Sensitivity`]({{ site.parameters_reference }}texture-detection-modes.html#sensitivity) |


