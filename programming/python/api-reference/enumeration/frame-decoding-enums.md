---
layout: default-layout
title: Dynamsoft Barcode Reader Enumerations - Frame Decoding Enumerations
description: This article shows Frame Decoding Enumerations of Dynamsoft Barcode Reader.
keywords: ClarityCalculationMethod, ClarityFilterMode, frame decoding enumeration, enumeration
needGenerateH3Content: false
permalink: /programming/python/api-reference/enumeration/frame-decoding-enums.html
---


# Frame Decoding Enumeration

> Note:
>
> - Frame Decoding Enumerations are removed in 9.0 version.

  | Enumeration | Description |
  |-------------|-------------|
  | [`ClarityCalculationMethod`](#claritycalculationmethod) | Describes the clarity calculation method. |
  | [`ClarityFilterMode`](#clarityfiltermode) | Describes the clarity filter mode. |
  

## ClarityCalculationMethod
Describes the clarity calculation method.

### Declarations




```python
class EnumClarityCalculationMethod(IntEnum)
```



### Members

| Member | Value | Description |
| --------------------------  | ----- | ----------- |
| ECCM_CONTRAST | 0x01 | Calculates clarity using the contrast method. |



## ClarityFilterMode

Describes the clarity filter mode.

### Declarations




```python
class EnumClarityFilterMode(IntEnum)
```



### Members

| Member | Value | Description |
| --------------------------  | ----- | ----------- |
| CFM_GENERAL | 0x01 | Filters the frames using the general algorithm based on calculated clarity. |
