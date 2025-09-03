---
layout: default-layout
title: Frame Decoding Enumerations - Dynamsoft Barcode Reader SDK .NET Edition
description: This article shows Frame Decoding Enumerations of Dynamsoft Barcode Reader.
keywords: ClarityCalculationMethod, ClarityFilterMode, frame decoding enumeration, enumeration
needGenerateH3Content: false
permalink: /programming/dotnet/api-reference/enumeration/frame-decoding-enums-v7.6.0.html
---


# Frame Decoding Enumeration

  | Enumeration | Description |
  |-------------|-------------|
  | [`ClarityCalculationMethod`](#claritycalculationmethod) | Describes the clarity calculation method. |
  | [`ClarityFilterMode`](#clarityfiltermode) | Describes the clarity filter mode. |
  

## ClarityCalculationMethod
Describes the clarity calculation method.

### Declarations
   
```csharp
enum Dynamsoft.Barcode.EnumClarityCalculationMethod
```





### Members
   
| Member | Value | Description |
| --------------------------  | ----- | ----------- |
| ECCM_CONTRAST | 0x01 | Calculates clarity using the contrast method. |





## ClarityFilterMode
Describes the clarity filter mode 

### Declarations
   
```csharp
enum Dynamsoft.Barcode.EnumClarityFilterMode
```





### Members
   
| Member | Value | Description |
| --------------------------  | ----- | ----------- |
| CFM_GENERAL | 0x01 | Filters the frames using the general algorithm based on calculated clarity. |
