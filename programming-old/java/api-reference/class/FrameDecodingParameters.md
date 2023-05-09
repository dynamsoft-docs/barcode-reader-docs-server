---
layout: default-layout
title: FrameDecodingParameters Class - Dynamsoft Barcode Reader SDK Java Edition API Reference
description: This page shows the FrameDecodingParameters Class of Dynamsoft Barcode Reader SDK Java Edition API Reference.
keywords: FrameDecodingParameters, class, api reference, java
needAutoGenerateSidebar: false
permalink: /programming/java/api-reference/class/FrameDecodingParameters.html
---


# FrameDecodingParameters
Defines a struct to configure the frame decoding Parameters.  


## Attributes
    
| Attribute | Type |
|---------- | ---- |
| [`maxQueueLength`](#maxqueuelength) | *int* |
| [`maxResultQueueLength`](#maxresultqueuelength) | *int* |
| [`width`](#width) | *int* |
| [`height`](#height) | *int* |
| [`stride`](#stride) | *int* |
| [`imagePixelFormat`](#imagepixelformat) | *int* |
| [`region`](#region) | [`RegionDefinition`](RegionDefinition.md) |
| [`threshold`](#threshold) | *float* |
| [`fps`](#fps) | *int* |
| [`autoFilter`](#autofilter) | *int* |
| [`clarityCalculationMethod`](#claritycalculationmethod) | *int* |
| [`clarityFilterMode`](#clarityfiltermode) | *int* |
| [`duplicateForgetTime`](#duplicateforgettime) | *int* |
| [`orientation`](#orientation) | *int* |


### maxQueueLength
The maximum number of frames waiting for decoding.
```java
int com.dynamsoft.dbr.FrameDecodingParameters.maxQueueLength
```
**Value Range**     
    [0,0x7fffffff]   
      
**Default Value**     
    3

### maxResultQueueLength
The maximum number of frames whose results (text result/localization result) will be kept for further reference.  
```java
int com.dynamsoft.dbr.FrameDecodingParameters.maxResultQueueLength
```
**Value Range**     
    [0,0x7fffffff]   
      
**Default Value**     
    10  

### width
The width of the frame image in pixels. 
```java
int com.dynamsoft.dbr.FrameDecodingParameters.width
```
**Value Range**     
    [0,0x7fffffff]   
      
**Default Value**     
    0  

### height
The height of the frame image in pixels.
```java
int com.dynamsoft.dbr.FrameDecodingParameters.height
```
**Value Range**     
    [0,0x7fffffff]   
      
**Default Value**     
    0  

### stride
The stride (or scan width) of the frame image.
```java
int com.dynamsoft.dbr.FrameDecodingParameters.stride
```
**Value Range**     
    [0,0x7fffffff]   
      
**Default Value**     
    0 
      
### imagePixelFormat
The image pixel format used in the image byte array.
```java
int com.dynamsoft.dbr.FrameDecodingParameters.imagePixelFormat
```
**Value Range**     
    A value of [`EnumImagePixelFormat`]({{ site.java_enumerations }}other-enums.html#imagepixelformat) Enumeration items.
      
**Default Value**     
    `IPF_GRAYSCALED`
    
**See Also**      
    [`EnumImagePixelFormat`]({{ site.java_enumerations }}other-enums.html#imagepixelformat)
      
### region
The region definition of the frame to calculate the internal indicator.  
```java
RegionDefinition com.dynamsoft.dbr.FrameDecodingParameters.region
```
**Default Value**    
    `{ regionLeft = 0, regionRight = 100, regionTop = 0, regionBottom = 100, regionMeasuredByPercentage = 1 }`
      
**See Also**       
    [`RegionDefinition`](RegionDefinition.md)
     
### threshold
The threshold used for filtering frames.
```java
float com.dynamsoft.dbr.FrameDecodingParameters.threshold
```
**Value Range**     
    [0, 1]
      
**Default Value**     
    0.01
    
**Remarks**      
    The SDK will calculate an inner indicator for each frame from [`appendFrame`](../BarcodeReader/video.md#appendframe), if the change rate of the indicators between the current frame and the history frames is larger than the given threshold, the current frame will not be added to the inner frame queue waiting for decoding.

### fps
The frequency of calling [`appendFrame`](../BarcodeReader/video.md#appendframe) per second.
```java
int com.dynamsoft.dbr.FrameDecodingParameters.fps
```
**Value Range**     
    [0,0x7fffffff]
      
**Default Value**     
    0  
    
**Remarks**      
    0 means the frequency will be calculated automatically by the SDK.

### autoFilter
Sets whether to filter frames automatically.
```java
int com.dynamsoft.dbr.FrameDecodingParameters.autoFilter
```
**Value Range**     
    [0,1]
      
**Default Value**     
    1  
    
**Remarks**      
    0: Diable filtering frames automatically. 1: Enable filtering frames automatically. 
    

### clarityCalculationMethod
Sets the method used for calculating the clarity of the frames.
```java
int com.dynamsoft.dbr.FrameDecodingParameters.clarityCalculationMethod
```
**Value Range**     
    Any one of the [`EnumClarityCalculationMethod`]({{ site.java_enumerations }}frame-decoding-enums.html#claritycalculationmethod) Enumeration items.   
      
**Default Value**     
    ECCM_CONTRAST   
    
**See Also**      
    [`EnumClarityCalculationMethod`]({{ site.java_enumerations }}frame-decoding-enums.html#claritycalculationmethod)    
    

### clarityFilterMode
Sets the mode used for filtering frames by calculated clarity.
```java
int com.dynamsoft.dbr.FrameDecodingParameters.clarityFilterMode
```
**Value Range**     
    Any one of the [`EnumClarityFilterMode`]({{ site.java_enumerations }}frame-decoding-enums.html#clarityfiltermode) Enumeration items.   
      
**Default Value**     
    CFM_GENERAL   
    
**See Also**      
    [`EnumClarityFilterMode`]({{ site.java_enumerations }}frame-decoding-enums.html#clarityfiltermode)    

### duplicateForgetTime

Set the time period used to ignore duplicate results found in frames. Measured in ms.

```java
int com.dynamsoft.dbr.FrameDecodingParameters.duplicateForgetTime
```

**Value Range**

[0, 600000]

**Default Value**

3000

**Remarks**

The library keeps each barcode result (type and value) in the buffer for a period of time (set with duplicateForgetTime) during which if a new result is an exact match, it's seen as a duplicate and will again be kept for that period of time while the old result is removed and so on.

### orientation

Set the orientation of the frame image data. The value is the angle that the image needs to be rotated clockwise so it shows correctly on the display in its natural orientation. It can be 0, 90, 180, or 270.

```java
int com.dynamsoft.dbr.FrameDecodingParameters.orientation
```

**Value Range**

0, 90, 180, or 270

**Default Value**

0
