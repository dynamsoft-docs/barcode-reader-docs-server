---
layout: default-layout
title: LocalizationResult Class - Dynamsoft Barcode Reader SDK .NET Edition API Reference
description: This page shows the LocalizationResult Class of Dynamsoft Barcode Reader SDK .NET Edition.
keywords: LocalizationResult, class, api reference, .Net
needAutoGenerateSidebar: false
permalink: /programming/dotnet/api-reference/class/LocalizationResult-v7.6.0.html
---


# LocalizationResult
Stores the localization result.

```csharp
public class LocalizationResult
```  

## Attributes
  
| Attribute | Type |
|---------- | ---- |
| [`TerminatePhase`](#terminatephase) | [`EnumTerminatePhase`]({{ site.dbr_dotnet_enumerations }}parameter-mode-enums.html#terminatephase) |
| [`BarcodeFormat`](#barcodeformat) | [`EnumBarcodeFormat`]({{ site.dbr_dotnet_enumerations }}format-enums.html#barcodeformat) |
| [`BarcodeFormatString`](#barcodeformatstring) | *string* |
| [`BarcodeFormat_2 `](#barcodeformat_2 ) | [`EnumBarcodeFormat_2`]({{ site.dbr_dotnet_enumerations }}format-enums.html#barcodeformat_2) |
| [`BarcodeFormatString_2`](#barcodeformatstring_2) | *string* |
| [`ResultPoints`](#resultpoints) | *Point[ ]* |
| [`Angle`](#angle) | *int* |
| [`ModuleSize`](#modulesize) | *int* |
| [`PageNumber`](#pagenumber) | *int* |
| [`RegionName`](#regionname) | *string* |
| [`DocumentName`](#documentname)| *string* |
| [`ResultCoordinateType`](#resultcoordinatetype) | [`EnumResultCoordinateType`]({{ site.dbr_parameters_reference }}result-coordinate-type.html) |
| [`AccompanyingTextBytes`](#accompanyingtextbytes) | *byte[ ]* |
| [`Confidence`](#confidence) | *int* |


### TerminatePhase
The terminate phase of localization result.

```csharp
EnumTerminatePhase Dynamsoft.Barcode.LocalizationResult.TerminatePhase
```

### BarcodeFormat
Barcode type in BarcodeFormat group 1.

```csharp
EnumBarcodeFormat Dynamsoft.Barcode.LocalizationResult.BarcodeFormat
```

### BarcodeFormatString
Barcode type in BarcodeFormat group 1 as string.

```csharp
string Dynamsoft.Barcode.LocalizationResult.BarcodeFormatString
```

### BarcodeFormat_2
Barcode type in BarcodeFormat group 2.

```csharp
EnumBarcodeFormat_2 Dynamsoft.Barcode.LocalizationResult.BarcodeFormat_2
```

### BarcodeFormatString_2
Barcode type in BarcodeFormat group 2 as string.

```csharp
string Dynamsoft.Barcode.LocalizationResult.BarcodeFormatString_2
```

### ResultPoints
The array which stores the coordinates of four result points. 

```csharp
Point[] Dynamsoft.Barcode.LocalizationResult.ResultPoints
```

### Angle
The angle of a barcode. Values range is from 0 to 360.

```csharp
int Dynamsoft.Barcode.LocalizationResult.Angle
```

### ModuleSize
The barcode module size (the minimum bar width in pixel).

```csharp
int Dynamsoft.Barcode.LocalizationResult.ModuleSize
```

### PageNumber
The page number the barcode located in. The index is 0-based.

```csharp
int Dynamsoft.Barcode.LocalizationResult.PageNumber
```

### RegionName
The region name the barcode located in.

```csharp
string Dynamsoft.Barcode.LocalizationResult.RegionName
```

### DocumentName
The document name.

```csharp
string Dynamsoft.Barcode.LocalizationResult.DocumentName
```

### ResultCoordinateType
The coordinate type.

```csharp
EnumResultCoordinateType Dynamsoft.Barcode.LocalizationResult.ResultCoordinateType
```

### AccompanyingTextBytes
The accompanying text content in a byte array.

```csharp
byte[] Dynamsoft.Barcode.LocalizationResult.AccompanyingTextBytes
```

### Confidence
The confidence of the localization result.

```csharp
int Dynamsoft.Barcode.LocalizationResult.Confidence
```
