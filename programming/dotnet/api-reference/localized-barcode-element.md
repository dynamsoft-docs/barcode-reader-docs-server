---
layout: default-layout
title: LocalizedBarcodeElement Class - Dynamsoft Barcode Reader .NET Edition API Reference
description: This page shows LocalizedBarcodeElement class definition of Dynamsoft Barcode Reader SDK .NET Edition.
keywords: GetAngle, GetConfidence, GetPossibleFormats, GetPossibleFormatsString, GetModuleSize, SetPossibleFormats, LocalizedBarcodeElement, api reference
---
# LocalizedBarcodeElement Class

The `LocalizedBarcodeElement` class represents a localized barcode element detected in an image. It is inherited from `RegionObjectElement` class.

## Definition

*Namespace:* Dynamsoft.DBR


*Inheritance:* [RegionObjectElement]({{ site.dcvb_dotnet_api }}core/intermediate-results/region-object-element.html) -> LocalizedBarcodeElement

```csharp
class LocalizedBarcodeElement : RegionObjectElement
```

## Methods

| Method | Description |
|--------|-------------|
| [`GetAngle`](#getangle) | Gets the orientation angle of the barcode. |
| [`GetConfidence`](#getconfidence) | Gets the confidence score of the barcode localization result. |
| [`GetPossibleFormats`](#getpossibleformats) | Gets the possible format of the barcode. |
| [`GetPossibleFormatsString`](#getpossibleformatsstring) | Get all possible formats of the localized barcode in one string splited by ",". |
| [`GetModuleSize`](#getmodulesize) | Gets the module size of the barcode. |
| [`SetPossibleFormats`](#setpossibleformats) | Sets the posssible formats of the barcode. |
| [`SetLocation`](#setlocation) | Sets the location of the current object. |

### Inherited Methods

Checkout inherited methods from [RegionObjectElement]({{ site.dcvb_dotnet_api }}core/intermediate-results/region-object-element.html) for more details.

### GetAngle

It is used to get the orientation angle of the barcode.

```csharp
int GetAngle()
```

**Return value**

Returns the orientation angle of the barcode.

### GetConfidence

It is used to get the confidence score of the barcode localization result.

```csharp
int GetConfidence()
```

**Return value**

Returns the confidence score of the barcode recognition result. It represents the confidence that the positioning area is a barcode.

### GetPossibleFormats

It is used to get the format of the barcode.

```csharp
ulong GetPossibleFormats()
```

**Return value**

Returns the format of the barcode.

**See Also**

[EnumBarcodeFormat]({{ site.dbr_dotnet_api }}enum-barcode-format.html)

### GetPossibleFormatsString

It is used to get all possible formats of the localized barcode in one string splited by ",".

```csharp
string GetPossibleFormatsString()
```

**Return value**

Returns the string representation of the barcode format in one string splited by ",".

### GetModuleSize

It is used to get the module size of the barcode.

```csharp
int GetModuleSize()
```

**Return value**

Returns the module size of the barcode.

### SetPossibleFormats

Sets the posssible formats of the barcode.

```csharp
void SetPossibleFormats(EnumBarcodeFormat possibleFormats)
```

**Parameters**

`possibleFormats` The posssible formats of the barcode.

**See Also**

[EnumBarcodeFormat]({{ site.dbr_dotnet_api }}enum-barcode-format.html)

### SetLocation

Sets the location of the current object.

```csharp
void SetLocation(Quadrilateral location)
```

**Parameters**

`[in] location` The location of the barcode.

**See Also**

[Quadrilateral]({{ site.dcvb_dotnet_api }}core/basic-classes/quadrilateral.html)
