---
layout: default-layout
title: LocalizationResult Class - Dynamsoft Barcode Reader SDK .NET Edition API Reference
description: This page shows the LocalizationResult Class of Dynamsoft Barcode Reader SDK .NET Edition.
keywords: LocalizationResult, class, api reference, .Net
needAutoGenerateSidebar: false
permalink: /programming/dotnet/api-reference/class/LocalizationResult-v9.2.0.html
---


# LocalizationResult
Stores the localization result.

```csharp
public class LocalizationResult
```  
  
  

## Attributes
  
| Attribute | Type |
|---------- | ---- |
| [`TerminatePhase`](#terminatephase) | [`EnumTerminatePhase`]({{ site.dotnet_enumerations }}parameter-mode-enums.html#terminatephase) |
| [`BarcodeFormat`](#barcodeformat) | [`EnumBarcodeFormat`]({{ site.dotnet_enumerations }}format-enums.html#barcodeformat) |
| [`BarcodeFormatString`](#barcodeformatstring) | *string* |
| [`BarcodeFormat_2 `](#barcodeformat_2 ) | [`EnumBarcodeFormat_2`]({{ site.dotnet_enumerations }}format-enums.html#barcodeformat_2) |
| [`BarcodeFormatString_2`](#barcodeformatstring_2) | *string* |
| [`ResultPoints`](#resultpoints) | *Point[ ]* |
| [`Angle`](#angle) | *int* |
| [`ModuleSize`](#modulesize) | *int* |
| [`PageNumber`](#pagenumber) | *int* |
| [`RegionName`](#regionname) | *string* |
| [`DocumentName`](#documentname)| *string* |
| [`ResultCoordinateType`](#resultcoordinatetype) | [`EnumResultCoordinateType`]({{ site.parameters_reference }}result-coordinate-type.html) |
| [`AccompanyingTextBytes`](#accompanyingtextbytes) | *byte[ ]* |
| [`Confidence`](#confidence) | *int* |


### TerminatePhase
The terminate phase of localization result.

```csharp
EnumTerminatePhase Dynamsoft.LocalizationResult.TerminatePhase
```

### BarcodeFormat
Barcode type in BarcodeFormat group 1.

```csharp
EnumBarcodeFormat Dynamsoft.LocalizationResult.BarcodeFormat
```

### BarcodeFormatString
Barcode type in BarcodeFormat group 1 as string.

```csharp
string Dynamsoft.LocalizationResult.BarcodeFormatString
```

### BarcodeFormat_2
Barcode type in BarcodeFormat group 2.

```csharp
EnumBarcodeFormat_2 Dynamsoft.LocalizationResult.BarcodeFormat_2
```

### BarcodeFormatString_2
Barcode type in BarcodeFormat group 2 as string.

```csharp
string Dynamsoft.LocalizationResult.BarcodeFormatString_2
```

### ResultPoints
The array which stores the coordinates of four result points. 

```csharp
Point[] Dynamsoft.LocalizationResult.ResultPoints
```

### Angle
The angle of a barcode. Values range is from 0 to 360.

```csharp
int Dynamsoft.LocalizationResult.Angle
```

### ModuleSize
The barcode module size (the minimum bar width in pixel).

```csharp
int Dynamsoft.LocalizationResult.ModuleSize
```

### PageNumber
The page number the barcode located in. The index is 0-based.

```csharp
int Dynamsoft.LocalizationResult.PageNumber
```

### RegionName
The region name the barcode located in.

```csharp
string Dynamsoft.LocalizationResult.RegionName
```

### DocumentName
The document name.

```csharp
string Dynamsoft.LocalizationResult.DocumentName
```

### ResultCoordinateType
The coordinate type.

```csharp
EnumResultCoordinateType Dynamsoft.LocalizationResult.ResultCoordinateType
```

### AccompanyingTextBytes
The accompanying text content in a byte array.

```csharp
byte[] Dynamsoft.LocalizationResult.AccompanyingTextBytes
```

### Confidence
The confidence of the localization result.

```csharp
int Dynamsoft.LocalizationResult.Confidence
```
