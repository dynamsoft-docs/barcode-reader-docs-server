---
layout: default-layout
title: IntermediateResult Struct - Dynamsoft Barcode Reader SDK C & C++ Edition
description: This page shows the IntermediateResult struct of Dynamsoft Barcode Reader SDK C & C++ Edition.
keywords: IntermediateResult, struct, c, c++
needAutoGenerateSidebar: false
permalink: /programming/c-cplusplus/struct/IntermediateResult.html
---


# IntermediateResult
Stores the intermediate result.

## Typedefs

```cpp
typedef struct tagIntermediateResult  IntermediateResult 
typedef struct tagIntermediateResult*  PIntermediateResult
```  

## Attributes
  
| Attribute | Type |
|---------- | ---- |
| [`resultsCount`](#resultscount) | *int* |
| [`results`](#results) | *const void \*\** |
| [`dataType`](#datatype) | [`IMResultDataType`]({{ site.dbr_c_cpp_enumerations }}result-enums.html#imresultdatatype) |
| [`resultType`](#resulttype) | [`IntermediateResultType`]({{ site.dbr_c_cpp_enumerations }}result-enums.html#intermediateresulttype) |
| [`barcodeComplementMode`](#barcodecomplementmode) | [`BarcodeComplementMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html#barcodecomplementmode) |
| [`bcmIndex`](#bcmindex) | *int* |
| [`deformationResistingMode`](#deformationresistingmode) | [`DeformationResistingMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html#deformationresistingmode) |
| [`drmIndex`](#drmindex) | *int* |
| [`dpmCodeReadingMode`](#dpmcodereadingmode) | [`DPMCodeReadingMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html#dpmcodereadingmode) |
| [`dpmcrmIndex`](#dpmcrmindex) | *int* |
| [`rotationMatrix`](#rotationmatrix) | *double\[9\]* |
| [`textFilterMode`](#textfiltermode) | [`TextFilterMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html#textfiltermode) |
| [`tfmIndex`](#tfmindex) | *int* |
| [`localizationMode`](#localizationmode) | [`LocalizationMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html#localizationmode) |
| [`lmIndex`](#lmindex) | *int* |
| [`binarizationMode`](#binarizationmode) | [`BinarizationMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html#binarizationmode) |
| [`bmIndex`](#bmindex) | *int* |
| [`imagePreprocessingMode`](#imagepreprocessingmode) | [`ImagePreprocessingMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html#imagepreprocessingmode) |
| [`ipmIndex`](#ipmindex) | *int* |
| [`roiId`](#roiid) | *int* |
| [`regionPredetectionMode`](#regionpredetectionmode) | [`RegionPredetectionMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html#regionpredetectionmode) |
| [`rpmIndex`](#rpmindex) | *int* |
| [`grayscaleTransformationMode`](#grayscaletransformationmode) | [`GrayscaleTransformationMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html#grayscaletransformationmode) |
| [`gtmIndex`](#gtmindex) | *int* |
| [`colourConversionMode`](#colourconversionmode) | [`ColourConversionMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html#colourconversionmode) |
| [`cicmIndex`](#cicmindex) | *int* |
| [`colourClusteringMode`](#colourclusteringmode) | [`ColourClusteringMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html#colourclusteringmode) |
| [`ccmIndex`](#ccmindex) | *int* |
| [`scaleDownRatio`](#scaledownratio) | *int* |
| [`frameId`](#frameid) | *int* |
| [`rpmColourArgumentIndex`](#rpmcolourargumentindex) | *int* |
| [`reserved`](#reserved) | *char\[60\]* |


### resultsCount
The total result count.
```cpp
int tagIntermediateResult::resultsCount
```

### results
One of the following types: Array of [`Contour`](Contour.md), Array of [`ImageData`](ImageData.md), Array of [`LineSegment`](LineSegment.md), Array of [`LocalizationResult`](LocalizationResult.md), Array of [`RegionOfInterest`](RegionOfInterest.md), Array of [`Quadrilateral`](Quadrilateral.md).
```cpp
const void** tagIntermediateResult::results
```

### dataType
The data type of the intermediate result
```cpp
IMResultDataType tagIntermediateResult::dataType
```

### resultType
Intermediate result type.
```cpp
IntermediateResultType tagIntermediateResult::resultType
```

### barcodeComplementMode
The [`BarcodeComplementMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html#barcodecomplementmode) used when generating the current intermediate result. 
```cpp
BarcodeComplementMode tagIntermediateResult::barcodeComplementMode
```

### bcmIndex
The array index of current used [`BarcodeComplementMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html#barcodecomplementmode) in the [`barcodeComplementModes`](FurtherModes.md#barcodecomplementmodes) setting.
```cpp
int tagIntermediateResult::bcmIndex
```

### deformationResistingMode
The [`DeformationResistingMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html#deformationresistingmode) used when generating the current intermediate result.
```cpp
DeformationResistingMode tagIntermediateResult::deformationResistingMode
```

### drmIndex
The array index of current used [`DeformationResistingMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html#deformationresistingmode) in the [`deformationResistingModes`](FurtherModes.md#deformationresistingmodes) setting.
```cpp
int tagIntermediateResult::drmIndex
```

### dpmCodeReadingMode
The [`DPMCodeReadingMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html#dpmcodereadingmode) used when generating the current intermediate result.
```cpp
DPMCodeReadingMode tagIntermediateResult::dpmCodeReadingMode
```

### dpmcrmIndex
The array index of current used [`DPMCodeReadingMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html#dpmcodereadingmode) in the [`dpmCodeReadingModes`](FurtherModes.md#dpmcodereadingmodes) setting.
```cpp
int tagIntermediateResult::dpmcrmIndex
```

### rotationMatrix
The rotation matrix.
```cpp
double tagIntermediateResult::rotationMatrix[9]
```

### textFilterMode
The [`TextFilterMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html#textfiltermode) used when generating the current intermediate result.
```cpp
TextFilterMode tagIntermediateResult::textFilterMode
```

### tfmIndex
The array index of current used [`TextFilterMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html#textfiltermode) in the [`textFilterModes`](FurtherModes.md#textfiltermodes) setting.
```cpp
int tagIntermediateResult::tfmIndex
```

### localizationMode
The [`LocalizationMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html#localizationmode) used when generating the current intermediate result.
```cpp
LocalizationMode tagIntermediateResult::localizationMode
```

### lmIndex
The array index of current used [`LocalizationMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html#localizationmode) in the [`localizationModes`](PublicRuntimeSettings.md#localizationmodes) setting.
```cpp
int tagIntermediateResult::lmIndex
```

### binarizationMode
The [`BinarizationMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html#binarizationmode) used when generating the current intermediate result.
```cpp
BinarizationMode tagIntermediateResult::binarizationMode
```

### bmIndex
The array index of current used [`BinarizationMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html#binarizationmode) in the [`binarizationModes`](PublicRuntimeSettings.md#binarizationmodes) setting.
```cpp
int tagIntermediateResult::bmIndex
```

### imagePreprocessingMode
The [`ImagePreprocessingMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html#imagepreprocessingmode) used when generating the current intermediate result.
```cpp
ImagePreprocessingMode tagIntermediateResult::imagePreprocessingMode
```

### ipmIndex
The array index of current used [`ImagePreprocessingMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html#imagepreprocessingmode) in [`imagePreprocessingModes`](FurtherModes.md#imagepreprocessingmodes) setting.
```cpp
int tagIntermediateResult::ipmIndex
```

### roiId
The ID of the ROI (Region Of Interest) generated by the SDK. -1 means the original image.
```cpp
int tagIntermediateResult::roiId
```

### regionPredetectionMode
The [`RegionPredetectionMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html#regionpredetectionmode) used when generating the current intermediate result.
```cpp
RegionPredetectionMode tagIntermediateResult::regionPredetectionMode
```

### rpmIndex
The array index of current used [`RegionPredetectionMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html#regionpredetectionmode) in the [`regionPredetectionModes`](FurtherModes.md#regionpredetectionmodes) setting.
```cpp
int tagIntermediateResult::rpmIndex
```

### grayscaleTransformationMode
The [`GrayscaleTransformationMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html#grayscaletransformationmode) used when generating the current intermediate result.
```cpp
GrayscaleTransformationMode tagIntermediateResult::grayscaleTransformationMode
```

### gtmIndex
The array index of current used [`GrayscaleTransformationMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html#grayscaletransformationmode) in the [`grayscaleTransformationModes`](FurtherModes.md#grayscaletransformationmodes) setting.
```cpp
int tagIntermediateResult::gtmIndex
```

### colourConversionMode
The [`ColourConversionMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html#colourconversionmode) used when generating the current intermediate result.
```cpp
ColourConversionMode tagIntermediateResult::colourConversionMode
```

### cicmIndex
The array index of current used [`ColourConversionMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html#colourconversionmode) in the [`colourConversionModes`](FurtherModes.md#colourconversionmodes) setting.
```cpp
int tagIntermediateResult::cicmIndex
```

### colourClusteringMode
The [`ColourClusteringMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html#colourclusteringmode) used when generating the current intermediate result.
```cpp
ColourClusteringMode tagIntermediateResult::colourClusteringMode
```

### ccmIndex
The array index of current used [`ColourClusteringMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html#colourclusteringmode) in the [`colourClusteringModes`](FurtherModes.md#colourclusteringmodes) setting.
```cpp
int tagIntermediateResult::ccmIndex
```

### scaleDownRatio
The scale down ratio.
```cpp
int tagIntermediateResult::scaleDownRatio
```

### frameId
The ID of the operated frame.
```cpp
int tagIntermediateResult::frameId
```

### rpmColourArgumentIndex
The index of ForeAndBackgroundColour argument used for RegionPredetectionMode.
```cpp
int tagIntermediateResult::rpmColourArgumentIndex
```

### reserved
Reserved memory for the struct. The length of this array indicates the size of the memory reserved for this struct.
```cpp
char tagIntermediateResult::reserved[60]
```

