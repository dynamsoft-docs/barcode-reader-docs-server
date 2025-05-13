---
layout: default-layout
title: CandidateBarcodeZone Class - Dynamsoft Barcode Reader .NET Edition API Reference
description: This page shows CandidateBarcodeZone class definition of Dynamsoft Barcode Reader SDK .NET Edition.
keywords: GetLocation, SetLocation, GetPossibleFormats, SetPossibleFormats, CandidateBarcodeZone, api reference
---
# CandidateBarcodeZone Class

The `CandidateBarcodeZone` class represents a candidate zone for barcode detection.

## Definition

*Namespace:* Dynamsoft.DBR.intermediate_results


```csharp
class CandidateBarcodeZone
```

## Methods

| Method                            | Description |
|-----------------------------------|-------------|
| [`CandidateBarcodeZone`](#CandidateBarcodeZone-constructor)           | Constructs a CandidateBarcodeZone object with default parameters. |
| [`CandidateBarcodeZone(Quadrilateral location, ulong possibleFormats)`](#CandidateBarcodeZone-constructor)           | Constructs a CandidateBarcodeZone object with the specified parameters. |
| [`GetLocation`](#getlocation)           | Gets the location of the candidate barcode.|
| [`SetLocation`](#setlocation)           | Sets the location of the candidate barcode.|
| [`GetPossibleFormats`](#getpossibleformats)           | Gets the posssible formats of the candidate barcode. |
| [`SetPossibleFormats`](#setpossibleformats)           | Sets the posssible formats of the candidate barcode. |


### CandidateBarcodeZone Constructor

Constructs a CandidateBarcodeZone object with the specified parameters.

```csharp
CandidateBarcodeZone();
CandidateBarcodeZone(Quadrilateral location, ulong possibleFormats);
```

**Parameters**

`location` The location of the candidate barcode.

`possibleFormats` The posssible formats of the candidate barcode.

**See Also**

[EnumBarcodeFormat]({{ site.dbr_dotnet_api }}enum-barcode-format.html)

### GetLocation

Gets the location of the candidate barcode.

```csharp
Quadrilateral GetLocation()
```

**Return value**

Returns the location of the candidate barcode.

**See Also**

[Quadrilateral]({{ site.dcvb_dotnet_api }}core/basic-classes/quadrilateral.html)

### SetLocation

Sets the location of the candidate barcode.

```csharp
void SetLocation(Quadrilateral loc)
```

**Parameters**

`loc` The location of the candidate barcode. 

**See Also**

[Quadrilateral]({{ site.dcvb_dotnet_api }}core/basic-classes/quadrilateral.html)

### GetPossibleFormats

Gets the posssible formats of the candidate barcode.

```csharp
ulong GetPossibleFormats()
```

**Return value**

Returns the posssible formats of the candidate barcode.

**See Also**

[EnumBarcodeFormat]({{ site.dbr_dotnet_api }}enum-barcode-format.html)

### SetPossibleFormats

Sets the posssible formats of the candidate barcode.

```csharp
void SetPossibleFormats(ulong formats)
```

**Parameters**

`formats` The posssible formats of the candidate barcode.

**See Also**

[EnumBarcodeFormat]({{ site.dbr_dotnet_api }}enum-barcode-format.html)