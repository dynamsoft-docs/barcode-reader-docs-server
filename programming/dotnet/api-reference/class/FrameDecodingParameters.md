---
layout: default-layout
title: Dynamsoft Barcode Reader .NET API Reference - FrameDecodingParameters Class
description: This page shows the FrameDecodingParameters Class of Dynamsoft Barcode Reader for .NET SDK.
keywords: FrameDecodingParameters, class, api reference, .Net
needAutoGenerateSidebar: false
---


# FrameDecodingParameters
Defines a struct to configure the frame decoding Parameters.  

```csharp
public class FrameDecodingParameters
```

## Attributes
    
| Attribute | Type |
|---------- | ---- |
| [`MaxQueueLength`](#maxqueuelength) | *int* |
| [`MaxResultQueueLength`](#maxresultqueuelength) | *int* |
| [`Width`](#width) | *int* |
| [`Height`](#height) | *int* |
| [`Stride`](#stride) | *int* |
| [`ImagePixelFormat`](#imagepixelformat) | [`EnumImagePixelFormat`]({{ site.dotnet_enumerations }}other-enums.html#imagepixelformat) |
| [`Region`](#region) | *[`RegionDefinition`](../struct/RegionDefinition.md)* |
| [`Threshold`](#threshold) | *float* |
| [`FPS`](#fps) | *int* |
| [`AutoFilter`](#autofilter) | *int* |
| [`ClarityCalculationMethod`](#claritycalculationmethod) | [`EnumClarityCalculationMethod`]({{ site.dotnet_enumerations }}frame-decoding-enums.html#claritycalculationmethod) |
| [`ClarityFilterMode`](#clarityfiltermode) | [`EnumClarityFilterMode`]({{ site.dotnet_enumerations }}frame-decoding-enums.html#clarityfiltermode) |
| [`DuplicateForgetTime`](#duplicateforgettime) | *int* |
| [`Orientation`](#orientation) | *int* |


### MaxQueueLength
The maximum number of frames waiting for decoding.

```csharp
int Dynamsoft.DBR.FrameDecodingParameters.MaxQueueLength
```

**Value Range**     
    [0,0x7fffffff]   
      
**Default Value**     
    3

### MaxResultQueueLength
The maximum number of frames whose results (text result/localization result) will be kept for further reference.  

```csharp
int Dynamsoft.DBR.FrameDecodingParameters.MaxResultQueueLength
```

**Value Range**     
    [0,0x7fffffff]   
      
**Default Value**     
    10  

### Width
The width of the frame image in pixels. 

```csharp
int Dynamsoft.DBR.FrameDecodingParameters.Width
```

**Value Range**     
    [0,0x7fffffff]   
      
**Default Value**     
    0  

### Height
The height of the frame image in pixels.

```csharp
int Dynamsoft.DBR.FrameDecodingParameters.Height
```

**Value Range**     
    [0,0x7fffffff]   
      
**Default Value**     
    0  

### Stride
The stride (or scan width) of the frame image.

```csharp
int Dynamsoft.DBR.FrameDecodingParameters.Stride
```

**Value Range**     
    [0,0x7fffffff]   
      
**Default Value**     
    0 
      
### ImagePixelFormat
The image pixel format used in the image byte array.

```csharp
EnumImagePixelFormat Dynamsoft.DBR.FrameDecodingParameters.ImagePixelFormat
```

**Value Range**     
    Any one value of [`ImagePixelFormat`]({{ site.dotnet_enumerations }}other-enums.html#imagepixelformat) Enumeration items.
      
**Default Value**     
    `EnumImagePixelFormat.IPF_GRAYSCALED`
      
### Region
The region definition of the frame to calculate the internal indicator.  

```csharp
RegionDefinition Dynamsoft.DBR.FrameDecodingParameters.Region
```

**Default Value**    
    `{ RegionLeft = 0, RegionRight = 100, RegionTop = 0, RegionBottom = 100, RegionMeasuredByPercentage = 1 }`
      
**See Also**       
    [`RegionDefinition`](../struct/RegionDefinition.md)
     
### Threshold
The threshold used for filtering frames.

```csharp
float Dynamsoft.DBR.FrameDecodingParameters.Threshold
```

**Value Range**     
    [0, 1]
      
**Default Value**     
    0.01
    
**Remarks**      
    The SDK will calculate an inner indicator for each frame from [`AppendFrame`](../BarcodeReader/video.md#appendframe), if the change rate of the indicators between the current frame and the history frames is larger than the given threshold, the current frame will not be added to the inner frame queue waiting for decoding.

### FPS
The frequency of calling [`AppendFrame`](../BarcodeReader/video.md#appendframe) per second.

```csharp
int Dynamsoft.DBR.FrameDecodingParameters.FPS
```

**Value Range**     
    [0,0x7fffffff]
      
**Default Value**     
    0  
    
**Remarks**      
    0 means the frequency will be calculated automatically by the SDK.

### AutoFilter
Sets whether to filter frames automatically.

```csharp
int Dynamsoft.DBR.FrameDecodingParameters.AutoFilter
```

**Value Range**     
    [0,1]
      
**Default Value**     
    1  
    
**Remarks**      
    0: Diable filtering frames automatically.  
    1: Enable filtering frames automatically. 
    

### ClarityCalculationMethod
Sets the method used for calculating the clarity of the frames.

```csharp
EnumClarityCalculationMethod Dynamsoft.DBR.FrameDecodingParameters.ClarityCalculationMethod
```

**Value Range**     
    Any one of the [`ClarityCalculationMethod`]({{ site.dotnet_enumerations }}frame-decoding-enums.html#claritycalculationmethod) Enumeration items.   
      
**Default Value**     
    EnumClarityCalculationMethod.ECCM_CONTRAST       

### ClarityFilterMode
Sets the mode used for filtering frames by calculated clarity.

```csharp
EnumClarityFilterMode Dynamsoft.DBR.FrameDecodingParameters.ClarityFilterMode
```

**Value Range**     
    Any one of the [`ClarityFilterMode`]({{ site.dotnet_enumerations }}frame-decoding-enums.html#clarityfiltermode) Enumeration items.   
      
**Default Value**     
    EnumClarityFilterMode.CFM_GENERAL   

### DuplicateForgetTime

Set the time period used to ignore duplicate results found in frames. Measured in ms.

```csharp
int Dynamsoft.DBR.FrameDecodingParameters.DuplicateForgetTime
```

**Value Range**

[0, 600000]

**Default Value**

3000

**Remarks**

The library keeps each barcode result (type and value) in the buffer for a period of time (set with DuplicateForgetTime) during which if a new result is an exact match, it's seen as a duplicate and will again be kept for that period of time while the old result is removed and so on.

### Orientation

Set the orientation of the frame image data. The value is the angle that the image needs to be rotated clockwise so it shows correctly on the display in its natural orientation. It can be 0, 90, 180, or 270.

```csharp
int Dynamsoft.DBR.FrameDecodingParameters.Orientation
```

**Value Range**

0, 90, 180, or 270

**Default Value**

0
