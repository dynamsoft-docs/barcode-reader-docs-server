---
layout: default-layout
title: FrameDecodingParameters Struct - Dynamsoft Barcode Reader SDK C & C++ Edition
description: This page shows the FrameDecodingParameters struct of Dynamsoft Barcode Reader SDK C & C++ Edition.
keywords: FrameDecodingParameters, struct, c, c++
needAutoGenerateSidebar: false
permalink: /programming/c-cplusplus/struct/FrameDecodingParameters.html
---


# FrameDecodingParameters

Defines a struct to configure the frame decoding Parameters.  

## Typedefs

```cpp
typedef struct tagFrameDecodingParameters  FrameDecodingParameters
```

## Attributes

| Attribute | Type |
|---------- | ---- |
| [`maxQueueLength`](#maxqueuelength) | *int* |
| [`maxResultQueueLength`](#maxresultqueuelength) | *int* |
| [`width`](#width) | *int* |
| [`height`](#height) | *int* |
| [`stride`](#stride) | *int* |
| [`imagePixelFormat`](#imagepixelformat) | [`ImagePixelFormat`]({{ site.dbr_c_cpp_enumerations }}other-enums.html#imagepixelformat) |
| [`region`](#region) | [`RegionDefinition`](RegionDefinition.md) |
| [`threshold`](#threshold) | *float* |
| [`fps`](#fps) | *int* |
| [`autoFilter`](#autofilter) | *int* |
| [`clarityCalculationMethod`](#claritycalculationmethod) | [`ClarityCalculationMethod`]({{ site.dbr_c_cpp_enumerations }}frame-decoding-enums.html#claritycalculationmethod) |
| [`clarityFilterMode`](#clarityfiltermode) | [`ClarityFilterMode`]({{ site.dbr_c_cpp_enumerations }}frame-decoding-enums.html#clarityfiltermode) |
| [`duplicateForgetTime`](#duplicateforgettime) | *int* |
| [`orientation`](#orientation) | *int* |
| [`reserved`](#reserved) | *char\[12\]* |

### maxQueueLength

The maximum number of frames waiting for decoding.

```cpp
int tagFrameDecodingParameters::maxQueueLength
```

**Value Range**

[0,0x7fffffff]

**Default Value**

3

### maxResultQueueLength

The maximum number of frames whose results (text result/localization result) will be kept for further reference.

```cpp
int tagFrameDecodingParameters::maxResultQueueLength
```

**Value Range**

[0,0x7fffffff]

**Default Value**

10  

### width

The width of the frame image in pixels.

```cpp
int tagFrameDecodingParameters::width
```

**Value Range**

[0,0x7fffffff]

**Default Value**

0  

### height

The height of the frame image in pixels.

```cpp
int tagFrameDecodingParameters::height
```

**Value Range**

[0,0x7fffffff]

**Default Value**

0  

### stride

The stride (or scan width) of the frame image.

```cpp
int tagFrameDecodingParameters::stride
```

**Value Range**

[0,0x7fffffff]

**Default Value**

0

### imagePixelFormat

The image pixel format used in the image byte array.

```cpp
ImagePixelFormat tagFrameDecodingParameters::imagePixelFormat
```

**Value Range**

A value of [`ImagePixelFormat`]({{ site.dbr_c_cpp_enumerations }}other-enums.html#imagepixelformat) Enumeration items.

**Default Value**

`IPF_GRAYSCALED`

**See Also**

[`ImagePixelFormat`]({{ site.dbr_c_cpp_enumerations }}other-enums.html#imagepixelformat)

### region

The region definition of the frame to calculate the internal indicator.

```cpp
RegionDefinition tagFrameDecodingParameters::region
```

**Default Value**

`{ regionLeft = 0, regionRight = 100, regionTop = 0, regionBottom = 100, regionMeasuredByPercentage = 1 }`

**See Also**

[`RegionDefinition`](RegionDefinition.md)

### threshold

The threshold used for filtering frames.

```cpp
float tagFrameDecodingParameters::threshold
```

**Value Range**

[0, 1]

**Default Value**

0.01

**Remarks**

The SDK will calculate an inner indicator for each frame from [`AppendFrame`]({{ site.dbr_cpp_methods }}video.html#appendframe) or  [`DBR_AppendFrame`]({{ site.dbr_c_methods }}video.html#dbr_appendframe), if the change rate of the indicators between the current frame and the history frames is larger than the given threshold, the current frame will not be added to the inner frame queue waiting for decoding.

### fps

The frequency of calling [`AppendFrame`]({{ site.dbr_cpp_methods }}video.html#appendframe) or  [`DBR_AppendFrame`]({{ site.dbr_c_methods }}video.html#dbr_appendframe) per second.

```cpp
int tagFrameDecodingParameters::fps
```

**Value Range**

[0,0x7fffffff]

**Default Value**

0  

**Remarks**

0 means the frequency will be calculated automatically by the SDK.

### autoFilter

Sets whether to filter frames automatically.

```cpp
int tagFrameDecodingParameters::autoFilter
```

**Value Range**

[0,1]

**Default Value**

1  

**Remarks**

0: Diable filtering frames automatically. 1: Enable filtering frames automatically.

### clarityCalculationMethod

Sets the method used for calculating the clarity of the frames.

```cpp
ClarityCalculationMethod tagFrameDecodingParameters::clarityCalculationMethod
```

**Value Range**

Any one of the [`ClarityCalculationMethod`]({{ site.dbr_c_cpp_enumerations }}frame-decoding-enums.html#claritycalculationmethod) Enumeration items.

**Default Value**

ECCM_CONTRAST

**See Also**

[`ClarityCalculationMethod`]({{ site.dbr_c_cpp_enumerations }}frame-decoding-enums.html#claritycalculationmethod)

### clarityFilterMode

Sets the mode used for filtering frames by calculated clarity.

```cpp
ClarityFilterMode tagFrameDecodingParameters::clarityFilterMode
```

**Value Range**

Any one of the [`ClarityFilterMode`]({{ site.dbr_c_cpp_enumerations }}frame-decoding-enums.html#clarityfiltermode) Enumeration items.

**Default Value**

CFM_GENERAL

**See Also**

[`ClarityFilterMode`]({{ site.dbr_c_cpp_enumerations }}frame-decoding-enums.html#clarityfiltermode)

### duplicateForgetTime

Set the time period used to ignore duplicate results found in frames. Measured in ms.

```cpp
int tagFrameDecodingParameters::duplicateForgetTime
```

**Value Range**

[0, 600000]

**Default Value**

3000

**Remarks**

The library keeps each barcode result (type and value) in the buffer for a period of time (set with duplicateForgetTime) during which if a new result is an exact match, it's seen as a duplicate and will again be kept for that period of time while the old result is removed and so on.

### orientation

Set the orientation of the frame image data. The value is the angle that the image needs to be rotated clockwise so it shows correctly on the display in its natural orientation. It can be 0, 90, 180, or 270.

```cpp
int tagFrameDecodingParameters::orientation
```

**Value Range**

0, 90, 180, or 270

**Default Value**

0

### reserved

Reserved memory for the struct. The length of this array indicates the size of the memory reserved for this struct

```cpp
char tagFrameDecodingParameters::reserved[12]
```
