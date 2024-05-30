---
layout: default-layout
title: Result Enumerations - Dynamsoft Barcode Reader SDK Python Edition
description: This article shows Result Enumerations of Dynamsoft Barcode Reader.
keywords: IMResultDataType, IntermediateResultSavingMode, IntermediateResultType, ResultCoordinateType, ResultType, TextResultOrderMode, result enumeration, enumeration
needGenerateH3Content: false
permalink: /programming/python/api-reference/enumeration/result-enums-v7.6.0.html
---

# Result Enumeration

  | Enumeration | Description |
  |-------------|-------------|
  | [`IMResultDataType`](#imresultdatatype) | Describes the intermediate result data type. |
  | [`IntermediateResultSavingMode`](#intermediateresultsavingmode) | Describes the intermediate result saving mode. |
  | [`IntermediateResultType`](#intermediateresulttype) | Describes the intermediate result type. |
  | [`ResultCoordinateType`](#resultcoordinatetype) | Describes the result coordinate type. |
  | [`ResultType`](#resulttype) | Describes the extended result type. |
  | [`TextResultOrderMode`](#textresultordermode) | Describes the text result order mode. |
  


## IMResultDataType
Describes the intermediate result data type.


### Declarations
   



```python
class EnumIMResultDataType(IntEnum)
```




### Members
   
| Member | Value | Description |
| --------------------------  | ----- | ----------- |
| IMRDT_IMAGE | 0x01 | Specifies the `ImageData`. |
| IMRDT_CONTOUR | 0x02 | Specifies the `Contour`. |
| IMRDT_LINESEGMENT | 0x04 | Specifies the `LineSegment`. |
| IMRDT_LOCALIZATIONRESULT | 0x08 | Specifies the `LocalizationResult`. |
| IMRDT_REGIONOFINTEREST  | 0x10 | Specifies the `RegionOfInterest`. |
| IMRDT_QUADRILATERAL | 0x20 | Specifies the `Quadrilateral`. |  



## IntermediateResultSavingMode
Describes the intermediate result saving mode.


### Declarations
   



```python
class EnumIntermediateResultSavingMode(IntEnum)
```



### Members
   
| Member | Value | Description |
| --------------------------  | ----- | ----------- |
| IRSM_MEMORY | 0x01 | Saves intermediate results in memory. |
| IRSM_FILESYSTEM | 0x02 | Saves intermediate results in file system. Check arguments of [`IntermediateResultSavingMode`]({{ site.dbr_parameters_reference }}intermediate-result-saving-mode.html) for available argument settings. |
| IRSM_BOTH | 0x04 | Saves intermediate results in both memory and file system. Check arguments of [`IntermediateResultSavingMode`]({{ site.dbr_parameters_reference }}intermediate-result-saving-mode.html) for available argument settings. |





## IntermediateResultType
Describes the intermediate result type.


### Declarations
   



```python
class EnumIntermediateResultType(IntEnum)
```




### Members
   
| Member | Value | Description |
| --------------------------  | ----- | ----------- |
| IRT_NO_RESULT | 0x00 | No intermediate result |
| IRT_ORIGINAL_IMAGE | 0x01 | Original image |
| IRT_COLOUR_CLUSTERED_IMAGE | 0x02 | Colour clustered image **(not supported yet)** |
| IRT_COLOUR_CONVERTED_GRAYSCALE_IMAGE | 0x04 | Colour image converted to grayscale |
| IRT_TRANSFORMED_GRAYSCALE_IMAGE | 0x08 | Transformed grayscale image |
| IRT_PREDETECTED_REGION | 0x10 | Predetected region |
| IRT_PREPROCESSED_IMAGE | 0x20 | Preprocessed image |
| IRT_BINARIZED_IMAGE | 0x40 | Binarized image |
| IRT_TEXT_ZONE | 0x80 | Text zone |
| IRT_CONTOUR | 0x100 | Contour |
| IRT_LINE_SEGMENT | 0x200 | Line segment |
| IRT_FORM | 0x400 | Form **(not supported yet)** |
| IRT_SEGMENTATION_BLOCK | 0x800 | Segmentation block **(not supported yet)** |
| IRT_TYPED_BARCODE_ZONE | 0x1000 | Typed barcode zone |
| IRT_PREDETECTED_QUADRILATERAL | 0x2000  | Predetected quadrilateral |





## ResultCoordinateType
Describes the result coordinate type.


### Declarations
   



```python
class EnumResultCoordinateType(IntEnum)
```




### Members
   
| Member | Value | Description |
| --------------------------  | ----- | ----------- |
| RCT_PIXEL | 0x01 | Returns the coordinate in pixel value. |
| RCT_PERCENTAGE | 0x02 | Returns the coordinate as a percentage. |






## ResultType
Describes the extended result type.


### Declarations
   



```python
class EnumResultType(IntEnum)
```




### Members
   
| Member | Value | Description |
| --------------------------  | ----- | ----------- |
| RT_STANDARD_TEXT  | 0 | Specifies the standard text. This means the barcode value. |
| RT_RAW_TEXT  | 1 | Specifies the raw text. This means the text that includes start/stop characters, check digits, etc. |
| RT_CANDIDATE_TEXT  | 2 | Specifies all the candidate text. This means all the standard text results decoded from the barcode. |
| RT_PARTIAL_TEXT  | 3 | Specifies the partial text. This means part of the text result decoded from the barcode. |





## TextResultOrderMode
Describes the text result order mode.


### Declarations
   



```python
class EnumTextResultOrderMode(IntEnum)
```




### Members
   
| Member | Value | Description |
| --------------------------  | ----- | ----------- |
| TROM_SKIP | 0x00 | Skips the result ordering operation. |
| TROM_CONFIDENCE | 0x01 | Returns the text results in descending order by confidence. |
| TROM_POSITION | 0x02 | Returns the text results in position order, from top to bottom, then left to right. |
| TROM_FORMAT | 0x04 | Returns the text results in alphabetical and numerical order by barcode format string. |
