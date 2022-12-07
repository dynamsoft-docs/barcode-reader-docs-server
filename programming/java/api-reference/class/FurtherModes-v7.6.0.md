---
layout: default-layout
title: FurtherModes Class - Dynamsoft Barcode Reader SDK Java Edition API Reference
description: This page shows the FurtherModes Class of Dynamsoft Barcode Reader SDK Java Edition API Reference.
keywords: FurtherModes, class, api reference, java
needAutoGenerateSidebar: false
---


# FurtherModes
Stores the FurtherModes.
  

## Attributes
  
| Attribute | Type |
|---------- | ---- |
| [`colourClusteringModes`](#colourclusteringmodes) | *int\[\]* |
| [`colourConversionModes`](#colourconversionmodes) | *int\[\]* |
| [`grayscaleTransformationModes`](#grayscaletransformationmodes) | *int\[\]* |
| [`regionPredetectionModes`](#regionpredetectionmodes) | *int\[\]* |
| [`imagePreprocessingModes`](#imagepreprocessingmodes) | *int\[\]* |
| [`textureDetectionModes`](#texturedetectionmodes) | *int\[\]* |
| [`textFilterModes`](#textfiltermodes) | *int\[\]* |
| [`textAssistedCorrectionMode`](#textassistedcorrectionmode) | *int* |
| [`dpmCodeReadingModes`](#dpmcodereadingmodes) | *int\[\]* |
| [`deformationResistingModes`](#deformationresistingmodes) | *int\[\]* |
| [`barcodeComplementModes`](#barcodecomplementmodes) | *int\[\]* |
| [`barcodeColourModes`](#barcodecolourmodes) | *int\[\]* |
| [`accompanyingTextRecognitionModes`](#accompanyingtextrecognitionmodes) | *int\[\]* |

### colourClusteringModes
Sets the mode and priority for colour categorization. Not supported yet.  
```java
int[] com.dynamsoft.barcode.FurtherModes.colourClusteringModes
```
- **Value range**  
   Each array item can be any one of the [`EnumColourClusteringMode`]({{ site.java_enumerations }}parameter-mode-enums.html#colourclusteringmode) Enumeration items.  
     
- **Default value**  
   `[CCM_SKIP,CCM_SKIP,CCM_SKIP,CCM_SKIP,CCM_SKIP,CCM_SKIP,CCM_SKIP,CCM_SKIP]`  
     
- **Remark**  
   The array index represents the priority of the item. The smaller index is, the higher priority is. 
   
- **See also**  
   [`EnumColourClusteringMode`]({{ site.java_enumerations }}parameter-mode-enums.html#colourclusteringmode)

### colourConversionModes
Sets the mode and priority for converting a colour image to a grayscale image.
```java
int[] com.dynamsoft.barcode.FurtherModes.colourConversionModes
```
- **Value range**  
   Each array item can be any one of the [`EnumColourConversionMode`]({{ site.java_enumerations }}parameter-mode-enums.html#colourconversionmode) Enumeration items. 
     
- **Default value**  
   `[CICM_GENERAL,CICM_SKIP,CICM_SKIP,CICM_SKIP,CICM_SKIP,CICM_SKIP,CICM_SKIP,CICM_SKIP]`  
     
- **Remark**  
   The array index represents the priority of the item. The smaller index is, the higher priority is.  
   
- **See also**  
   [`EnumColourConversionMode`]({{ site.java_enumerations }}parameter-mode-enums.html#colourconversionmode)
   
### grayscaleTransformationModes
Sets the mode and priority for the grayscale image conversion.
```java
int[] com.dynamsoft.barcode.FurtherModes.grayscaleTransformationModes
```
- **Value range**  
   Each array item can be any one of the [`EnumGrayscaleTransformationMode`]({{ site.java_enumerations }}parameter-mode-enums.html#grayscaletransformationmode) Enumeration items. 
     
- **Default value**  
   `[GTM_ORIGINAL,GTM_SKIP,GTM_SKIP,GTM_SKIP,GTM_SKIP,GTM_SKIP,GTM_SKIP,GTM_SKIP]`  
     
- **Remark**  
   The array index represents the priority of the item. The smaller index is, the higher priority is.  
   
- **See also**  
   [`EnumGrayscaleTransformationMode`]({{ site.java_enumerations }}parameter-mode-enums.html#grayscaletransformationmode)

### regionPredetectionModes
Sets the region pre-detection mode for barcodes search.
```java
int[] com.dynamsoft.barcode.FurtherModes.regionPredetectionModes
```
- **Value range**  
   Each array item can be any one of the [`EnumRegionPredetectionMode`]({{ site.java_enumerations }}parameter-mode-enums.html#regionpredetectionmode) Enumeration items.  
     
- **Default value**  
   `[RPM_GENERAL,RPM_SKIP,RPM_SKIP,RPM_SKIP,RPM_SKIP,RPM_SKIP,RPM_SKIP,RPM_SKIP]`  
     
- **Remark**  
   The array index represents the priority of the item. The smaller index is, the higher priority is. If the image is large and the barcode on the image is very small, it is recommended to enable region predetection to speed up the localization process and recognition accuracy.
   
- **See also**  
   [`EnumRegionPredetectionMode`]({{ site.java_enumerations }}parameter-mode-enums.html#regionpredetectionmode)

### imagePreprocessingModes
Sets the mode and priority for image preprocessing algorithms.
```java
int[] com.dynamsoft.barcode.FurtherModes.imagePreprocessingModes
```
- **Value range**  
   Each array item can be any one of the [`EnumImagePreprocessingMode`]({{ site.java_enumerations }}parameter-mode-enums.html#imagepreprocessingmode) Enumeration items.  
     
- **Default value**  
   `[IPM_GENERAL,IPM_SKIP,IPM_SKIP,IPM_SKIP,IPM_SKIP,IPM_SKIP,IPM_SKIP,IPM_SKIP]`  
     
- **Remark**  
   The array index represents the priority of the item. The smaller index is, the higher priority is.
   
- **See also**  
   [`EnumImagePreprocessingMode`]({{ site.java_enumerations }}parameter-mode-enums.html#imagepreprocessingmode)

### textureDetectionModes
Sets the mode and priority for texture detection. 
```java
int[] com.dynamsoft.barcode.FurtherModes.textureDetectionModes
```
- **Value range**  
   Each array item can be any one of the [`EnumTextureDetectionMode`]({{ site.java_enumerations }}parameter-mode-enums.html#texturedetectionmode) Enumeration items.  
     
- **Default value**  
   `[TDM_GENERAL_WIDTH_CONCENTRATION,TDM_SKIP,TDM_SKIP,TDM_SKIP,TDM_SKIP,TDM_SKIP,TDM_SKIP,TDM_SKIP]`  
     
- **Remark**  
   The array index represents the priority of the item. The smaller index is, the higher priority is.
   
- **See also**  
   [`EnumTextureDetectionMode`]({{ site.java_enumerations }}parameter-mode-enums.html#texturedetectionmode)
   
### textFilterModes
Sets the mode and priority for text filter.
```java
int[] com.dynamsoft.barcode.FurtherModes.textFilterModes
```
- **Value range**  
   Each array item can be any one of the [`EnumTextFilterMode`]({{ site.java_enumerations }}parameter-mode-enums.html#textfiltermode) Enumeration items.  
     
- **Default value**  
   `[TFM_GENERAL_CONTOUR,TFM_SKIP,TFM_SKIP,TFM_SKIP,TFM_SKIP,TFM_SKIP,TFM_SKIP,TFM_SKIP]`  
     
- **Remark**  
   The array index represents the priority of the item. The smaller index is, the higher priority is. If the image contains a lot of text, you can enable text filter to speed up the localization process.
   
- **See also**  
   [`EnumTextFilterMode`]({{ site.java_enumerations }}parameter-mode-enums.html#textfiltermode)
   
### textAssistedCorrectionMode
Sets the mode of text assisted correction for barcode decoding. ***Not supported yet***.
```java
int com.dynamsoft.barcode.FurtherModes.textAssistedCorrectionMode
```
- **Value range**  
   Any one of the [`EnumTextAssistedCorrectionMode`]({{ site.java_enumerations }}parameter-mode-enums.html#enumtextassistedcorrectionmode) Enumeration items.  
     
- **Default value**  
   `TACM_VERIFYING`  
   
- **See also**  
   [`EnumTextAssistedCorrectionMode`]({{ site.java_enumerations }}parameter-mode-enums.html#enumtextassistedcorrectionmode)
   
### dpmCodeReadingModes
Sets the mode and priority for DPM code reading.
```java
int[] com.dynamsoft.barcode.FurtherModes.dpmCodeReadingModes
```
- **Value range**  
   Each array item can be any one of the [`EnumDPMCodeReadingMode`]({{ site.java_enumerations }}parameter-mode-enums.html#dpmcodereadingmode) Enumeration items.  
     
- **Default value**  
   `[DPMCRM_SKIP,DPMCRM_SKIP,DPMCRM_SKIP,DPMCRM_SKIP,DPMCRM_SKIP,DPMCRM_SKIP,DPMCRM_SKIP,DPMCRM_SKIP]`  
     
- **Remark**  
   The array index represents the priority of the item. The smaller index is, the higher priority is.  
   
- **See also**  
   [`EnumDPMCodeReadingMode`]({{ site.java_enumerations }}parameter-mode-enums.html#dpmcodereadingmode)

### deformationResistingModes
Sets the mode and priority for deformation resisting.
```java
int[] com.dynamsoft.barcode.FurtherModes.deformationResistingModes
```
- **Value range**  
   Each array item can be any one of the [`EnumDeformationResistingMode`]({{ site.java_enumerations }}parameter-mode-enums.html#deformationresistingmode) Enumeration items.  
     
- **Default value**  
   `[DRM_SKIP,DRM_SKIP,DRM_SKIP,DRM_SKIP,DRM_SKIP,DRM_SKIP,DRM_SKIP,DRM_SKIP]`  
     
- **Remark**  
   The array index represents the priority of the item. The smaller index is, the higher priority is.  
   
- **See also**  
   [`EnumDeformationResistingMode`]({{ site.java_enumerations }}parameter-mode-enums.html#deformationresistingmode) 

### barcodeComplementModes
Sets the mode and priority to complement the missing parts in the barcode.
```java
int[] com.dynamsoft.barcode.FurtherModes.barcodeComplementModes
```
- **Value range**  
   Each array item can be any one of the [`EnumBarcodeComplementMode`]({{ site.java_enumerations }}parameter-mode-enums.html#barcodecomplementmode) Enumeration items.  
     
- **Default value**  
   `[BCM_SKIP,BCM_SKIP,BCM_SKIP,BCM_SKIP,BCM_SKIP,BCM_SKIP,BCM_SKIP,BCM_SKIP]`  
     
- **Remark**  
   The array index represents the priority of the item. The smaller index is, the higher priority is.  
   
- **See also**  
   [`EnumBarcodeComplementMode`]({{ site.java_enumerations }}parameter-mode-enums.html#barcodecomplementmode) 

### barcodeColourModes
Sets the mode and priority for the barcode colour mode used to process the barcode zone.
```java
int[] com.dynamsoft.barcode.FurtherModes.barcodeColourModes
```
- **Value range**  
   Each array item can be any one of the [`EnumBarcodeColourMode`]({{ site.java_enumerations }}parameter-mode-enums.html#barcodecolourmode) Enumeration items.  
     
- **Default value**  
   `[BICM_DARK_ON_LIGHT,BICM_SKIP,BICM_SKIP,BICM_SKIP,BICM_SKIP,BICM_SKIP,BICM_SKIP,BICM_SKIP]`  
     
- **Remark**  
   The array index represents the priority of the item. The smaller index is, the higher priority is.  
   
- **See also**  
   [`EnumBarcodeColourMode`]({{ site.java_enumerations }}parameter-mode-enums.html#barcodecolourmode)

### accompanyingTextRecognitionModes
Sets the mode and priority to recognize accompanying text.
```java
int[] com.dynamsoft.barcode.FurtherModes.accompanyingTextRecognitionModes
```
- **Value range**  
   Each array item can be any one of the [`EnumAccompanyingTextRecognitionMode`]({{ site.java_enumerations }}parameter-mode-enums.html#accompanyingtextrecognitionmode) Enumeration items.  
     
- **Default value**  
   `[ATRM_SKIP,ATRM_SKIP,ATRM_SKIP,ATRM_SKIP,ATRM_SKIP,ATRM_SKIP,ATRM_SKIP,ATRM_SKIP]`  
     
- **Remark**  
   The array index represents the priority of the item. The smaller index is, the higher priority is.  
   
- **See also**  
   [`EnumAccompanyingTextRecognitionMode`]({{ site.java_enumerations }}parameter-mode-enums.html#accompanyingtextrecognitionmode)
