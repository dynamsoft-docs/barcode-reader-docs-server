---
layout: default-layout
title: FurtherModes Class - Dynamsoft Barcode Reader SDK Java Edition API Reference
description: This page shows the FurtherModes Class of Dynamsoft Barcode Reader SDK Java Edition API Reference.
keywords: FurtherModes, class, api reference, java
needAutoGenerateSidebar: false
permalink: /programming/java/api-reference/class/FurtherModes.html
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
| [`dpmCodeReadingModes`](#dpmcodereadingmodes) | *int\[\]* |
| [`deformationResistingModes`](#deformationresistingmodes) | *int\[\]* |
| [`barcodeComplementModes`](#barcodecomplementmodes) | *int\[\]* |
| [`barcodeColourModes`](#barcodecolourmodes) | *int\[\]* |
| [`accompanyingTextRecognitionModes`](#accompanyingtextrecognitionmodes) | *int\[\]* |

### colourClusteringModes
Sets the mode and priority for colour categorization. Not supported yet.  
```java
int[] com.dynamsoft.dbr.FurtherModes.colourClusteringModes
```
**Value Range**    
   Each array item can be any one of the [`EnumColourClusteringMode`]({{ site.java_enumerations }}parameter-mode-enums.html#colourclusteringmode) Enumeration items.  
     
**Default Value**    
   `[CCM_SKIP,CCM_SKIP,CCM_SKIP,CCM_SKIP,CCM_SKIP,CCM_SKIP,CCM_SKIP,CCM_SKIP]`  
     
**Remarks**      
   The array index represents the priority of the item. The smaller index is, the higher priority is. 
   
**See Also**      
   [`EnumColourClusteringMode`]({{ site.java_enumerations }}parameter-mode-enums.html#colourclusteringmode)

### colourConversionModes
Sets the mode and priority for converting a colour image to a grayscale image.
```java
int[] com.dynamsoft.dbr.FurtherModes.colourConversionModes
```
**Value Range**    
   Each array item can be any one of the [`EnumColourConversionMode`]({{ site.java_enumerations }}parameter-mode-enums.html#colourconversionmode) Enumeration items. 
     
**Default Value**    
   `[CICM_GENERAL,CICM_SKIP,CICM_SKIP,CICM_SKIP,CICM_SKIP,CICM_SKIP,CICM_SKIP,CICM_SKIP]`  
     
**Remarks**      
   The array index represents the priority of the item. The smaller index is, the higher priority is.  
   
**See Also**      
   [`EnumColourConversionMode`]({{ site.java_enumerations }}parameter-mode-enums.html#colourconversionmode)
   
### grayscaleTransformationModes
Sets the mode and priority for the grayscale image conversion.
```java
int[] com.dynamsoft.dbr.FurtherModes.grayscaleTransformationModes
```
**Value Range**    
   Each array item can be any one of the [`EnumGrayscaleTransformationMode`]({{ site.java_enumerations }}parameter-mode-enums.html#grayscaletransformationmode) Enumeration items. 
     
**Default Value**    
   `[GTM_ORIGINAL,GTM_SKIP,GTM_SKIP,GTM_SKIP,GTM_SKIP,GTM_SKIP,GTM_SKIP,GTM_SKIP]`  
     
**Remarks**      
   The array index represents the priority of the item. The smaller index is, the higher priority is.  
   
**See Also**      
   [`EnumGrayscaleTransformationMode`]({{ site.java_enumerations }}parameter-mode-enums.html#grayscaletransformationmode)

### regionPredetectionModes
Sets the region pre-detection mode for barcodes search.
```java
int[] com.dynamsoft.dbr.FurtherModes.regionPredetectionModes
```
**Value Range**    
   Each array item can be any one of the [`EnumRegionPredetectionMode`]({{ site.java_enumerations }}parameter-mode-enums.html#regionpredetectionmode) Enumeration items.  
     
**Default Value**    
   `[RPM_GENERAL,RPM_SKIP,RPM_SKIP,RPM_SKIP,RPM_SKIP,RPM_SKIP,RPM_SKIP,RPM_SKIP]`  
     
**Remarks**      
   The array index represents the priority of the item. The smaller index is, the higher priority is. If the image is large and the barcode on the image is very small, it is recommended to enable region predetection to speed up the localization process and recognition accuracy.
   
**See Also**      
   [`EnumRegionPredetectionMode`]({{ site.java_enumerations }}parameter-mode-enums.html#regionpredetectionmode)

### imagePreprocessingModes
Sets the mode and priority for image preprocessing algorithms.
```java
int[] com.dynamsoft.dbr.FurtherModes.imagePreprocessingModes
```
**Value Range**    
   Each array item can be any one of the [`EnumImagePreprocessingMode`]({{ site.java_enumerations }}parameter-mode-enums.html#imagepreprocessingmode) Enumeration items.  
     
**Default Value**    
   `[IPM_GENERAL,IPM_SKIP,IPM_SKIP,IPM_SKIP,IPM_SKIP,IPM_SKIP,IPM_SKIP,IPM_SKIP]`  
     
**Remarks**      
   The array index represents the priority of the item. The smaller index is, the higher priority is.
   
**See Also**      
   [`EnumImagePreprocessingMode`]({{ site.java_enumerations }}parameter-mode-enums.html#imagepreprocessingmode)

### textureDetectionModes
Sets the mode and priority for texture detection. 
```java
int[] com.dynamsoft.dbr.FurtherModes.textureDetectionModes
```
**Value Range**    
   Each array item can be any one of the [`EnumTextureDetectionMode`]({{ site.java_enumerations }}parameter-mode-enums.html#texturedetectionmode) Enumeration items.  
     
**Default Value**    
   `[TDM_GENERAL_WIDTH_CONCENTRATION,TDM_SKIP,TDM_SKIP,TDM_SKIP,TDM_SKIP,TDM_SKIP,TDM_SKIP,TDM_SKIP]`  
     
**Remarks**      
   The array index represents the priority of the item. The smaller index is, the higher priority is.
   
**See Also**      
   [`EnumTextureDetectionMode`]({{ site.java_enumerations }}parameter-mode-enums.html#texturedetectionmode)
   
### textFilterModes
Sets the mode and priority for text filter.
```java
int[] com.dynamsoft.dbr.FurtherModes.textFilterModes
```
**Value Range**    
   Each array item can be any one of the [`EnumTextFilterMode`]({{ site.java_enumerations }}parameter-mode-enums.html#textfiltermode) Enumeration items.  
     
**Default Value**    
   `[TFM_GENERAL_CONTOUR,TFM_SKIP,TFM_SKIP,TFM_SKIP,TFM_SKIP,TFM_SKIP,TFM_SKIP,TFM_SKIP]`  
     
**Remarks**      
   The array index represents the priority of the item. The smaller index is, the higher priority is. If the image contains a lot of text, you can enable text filter to speed up the localization process.
   
**See Also**      
   [`EnumTextFilterMode`]({{ site.java_enumerations }}parameter-mode-enums.html#textfiltermode)
   
   
### dpmCodeReadingModes
Sets the mode and priority for DPM code reading.
```java
int[] com.dynamsoft.dbr.FurtherModes.dpmCodeReadingModes
```
**Value Range**    
   Each array item can be any one of the [`EnumDPMCodeReadingMode`]({{ site.java_enumerations }}parameter-mode-enums.html#dpmcodereadingmode) Enumeration items.  
     
**Default Value**    
   `[DPMCRM_SKIP,DPMCRM_SKIP,DPMCRM_SKIP,DPMCRM_SKIP,DPMCRM_SKIP,DPMCRM_SKIP,DPMCRM_SKIP,DPMCRM_SKIP]`  
     
**Remarks**      
   The array index represents the priority of the item. The smaller index is, the higher priority is.  
   
**See Also**      
   [`EnumDPMCodeReadingMode`]({{ site.java_enumerations }}parameter-mode-enums.html#dpmcodereadingmode)

### deformationResistingModes
Sets the mode and priority for deformation resisting.
```java
int[] com.dynamsoft.dbr.FurtherModes.deformationResistingModes
```
**Value Range**    
   Each array item can be any one of the [`EnumDeformationResistingMode`]({{ site.java_enumerations }}parameter-mode-enums.html#deformationresistingmode) Enumeration items.  
     
**Default Value**    
   `[DRM_SKIP,DRM_SKIP,DRM_SKIP,DRM_SKIP,DRM_SKIP,DRM_SKIP,DRM_SKIP,DRM_SKIP]`  
     
**Remarks**      
   The array index represents the priority of the item. The smaller index is, the higher priority is.  
   
**See Also**      
   [`EnumDeformationResistingMode`]({{ site.java_enumerations }}parameter-mode-enums.html#deformationresistingmode) 

### barcodeComplementModes
Sets the mode and priority to complement the missing parts in the barcode.
```java
int[] com.dynamsoft.dbr.FurtherModes.barcodeComplementModes
```
**Value Range**    
   Each array item can be any one of the [`EnumBarcodeComplementMode`]({{ site.java_enumerations }}parameter-mode-enums.html#barcodecomplementmode) Enumeration items.  
     
**Default Value**    
   `[BCM_SKIP,BCM_SKIP,BCM_SKIP,BCM_SKIP,BCM_SKIP,BCM_SKIP,BCM_SKIP,BCM_SKIP]`  
     
**Remarks**      
   The array index represents the priority of the item. The smaller index is, the higher priority is.  
   
**See Also**      
   [`EnumBarcodeComplementMode`]({{ site.java_enumerations }}parameter-mode-enums.html#barcodecomplementmode) 

### barcodeColourModes
Sets the mode and priority for the barcode colour mode used to process the barcode zone.
```java
int[] com.dynamsoft.dbr.FurtherModes.barcodeColourModes
```
**Value Range**    
   Each array item can be any one of the [`EnumBarcodeColourMode`]({{ site.java_enumerations }}parameter-mode-enums.html#barcodecolourmode) Enumeration items.  
     
**Default Value**    
   `[BICM_DARK_ON_LIGHT,BICM_SKIP,BICM_SKIP,BICM_SKIP,BICM_SKIP,BICM_SKIP,BICM_SKIP,BICM_SKIP]`  
     
**Remarks**      
   The array index represents the priority of the item. The smaller index is, the higher priority is.  
   
**See Also**      
   [`EnumBarcodeColourMode`]({{ site.java_enumerations }}parameter-mode-enums.html#barcodecolourmode)

### accompanyingTextRecognitionModes

`Deprecated`. Sets the mode and priority to recognize accompanying text.

```java
int[] com.dynamsoft.dbr.FurtherModes.accompanyingTextRecognitionModes
```
