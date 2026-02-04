---
layout: default-layout
title: BarcodeResultItem Class - Dynamsoft Barcode Reader Module .NET Edition API Reference
description: Definition of BarcodeResultItem class in Dynamsoft Barcode Reader Module .NET Edition.
keywords: GetFormat, GetText, GetLocation, GetConfidence, GetModuleSize, BarcodeResultItem, api reference
---

# BarcodeResultItem Class

The `BarcodeResultItem` class represents a barcode result item decoded by barcode reader engine. It is derived from `CapturedResultItem`.

## Definition

*Namespace:* Dynamsoft.DBR


*Inheritance:* [CapturedResultItem]({{ site.dcvb_dotnet_api }}core/basic-classes/captured-result-item.html) -> BarcodeResultItem

```csharp
public class BarcodeResultItem : CapturedResultItem
```

## Methods

| Method               | Description |
|----------------------|-------------|
| [`GetFormat`](#getformat) | Gets the format of the decoded barcode result. |
| [`GetFormatString`](#getformatstring) | Gets the format string of the decoded barcode result. |
| [`GetText`](#gettext) | Gets the text result of the decoded barcode. |
| [`GetBytes`](#getbytes) | Gets the text bytes of the decoded barcode result. |
| [`GetLocation`](#getlocation) | Gets the location of the decoded barcode in a quadrilateral. |
| [`GetConfidence`](#getconfidence) | Gets the confidence of the decoded barcode result. |
| [`GetAngle`](#getangle) | Gets the angle of the decoded barcode result. |
| [`GetModuleSize`](#getmodulesize) | Gets the module size of the decoded barcode result. |
| [`GetDetails`](#getdetails) | Gets the details of the decoded barcode result. |
| [`IsDPM`](#isdpm) | Gets whether the decoded barcode is a DPM code. |
| [`IsMirrored`](#ismirrored) | Gets whether the decoded barcode is a mirrored barcode. |
| [`GetCapturedResultItemType`](#getcapturedresultitemtype) | Gets the type of the captured result item. |
| [`GetReferenceItem`](#getreferenceitem) | Gets the referenced item in the captured result item. |
| [`GetECISegments`](#getecisegments) | Gets all the ECI segments in the barcode. |

### GetFormat

Gets the format of the decoded barcode result.

```csharp
EnumBarcodeFormat GetFormat()
```

**Return Value**

Returns the format of the decoded barcode result.

**See Also**

[EnumBarcodeFormat]({{ site.dbr_dotnet_api }}enum-barcode-format.html)

### GetFormatString

Gets the format string of the decoded barcode result.

```csharp
string GetFormatString()
```

**Return Value**

Returns the format string of the decoded barcode result.

### GetText

Gets the text result of the decoded barcode.

```csharp
string GetText()
```

**Return Value**

Returns the text result of the decoded barcode.

### GetBytes

Gets the text bytes of the decoded barcode result.

```csharp
byte[] GetBytes()
```

**Return Value**

Returns the text bytes of the decoded barcode result.

### GetLocation

Gets the location of the decoded barcode in a quadrilateral.

```csharp
Quadrilateral GetLocation()
```

**Return Value**

Returns the location of the decoded barcode in a quadrilateral.

**See Also**

[Quadrilateral]({{ site.dcvb_dotnet_api }}core/basic-classes/quadrilateral.html)

### GetConfidence

Gets the confidence of the decoded barcode result.

```csharp
int GetConfidence()
```

**Return Value**

Returns the confidence of the decoded barcode result.

### GetAngle

Gets the angle of the decoded barcode result.

```csharp
int GetAngle()
```

**Return Value**

Returns the angle of the decoded barcode result.

**See Also**

[How the angle is calculated for different barcode types]({{site.features}}get-confidence-rotation.html?lang=csharp#barcode-rotation-angle)

### GetModuleSize

Gets the module size of the decoded barcode result.

```csharp
int GetModuleSize()
```

**Return Value**

Returns the module size of the decoded barcode result.

### GetDetails

Gets the details of the decoded barcode result.

```csharp
BarcodeDetails GetDetails()
```

**Return Value**

Returns the details of the decoded barcode result.

**See Also**

- [AztecDetails]({{ site.dbr_dotnet_api }}aztec-details.html)
- [BarcodeDetails]({{ site.dbr_dotnet_api }}barcode-details.html)
- [DataMatrixDetails]({{ site.dbr_dotnet_api }}datamatrix-details.html)
- [OneDCodeDetails]({{ site.dbr_dotnet_api }}oned-code-details.html)
- [PDF417Details]({{ site.dbr_dotnet_api }}pdf417-details.html)
- [QRCodeDetails]({{ site.dbr_dotnet_api }}qr-code-details.html)

### IsDPM

Gets whether the decoded barcode is a DPM code.

```csharp
bool IsDPM()
```

**Return Value**

Returns whether the decoded barcode is a DPM code.

### IsMirrored

Gets whether the decoded barcode is mirrored.

```csharp
bool IsMirrored()
```

**Return Value**

Returns whether the decoded barcode is mirrored.

### GetCapturedResultItemType

Gets the type of the captured result item.

```csharp
EnumCapturedResultItemType GetCapturedResultItemType()
```

**Return Value**

Returns the type of the captured result item.

**See Also**

[EnumCapturedResultItemType]({{ site.dcvb_dotnet_api }}core/enum-captured-result-item-type.html)

### GetReferenceItem

Gets the referenced item in the captured result item.

```csharp
CapturedResultItem GetReferenceItem()
```

**Return Value**

Returns the referenced item in the captured result item.

**See Also**

[CapturedResultItem]({{ site.dcvb_dotnet_api }}core/basic-classes/captured-result-item.html)

### GetECISegments

Gets all the ECI segments in the barcode.

```csharp
ECISegment[] GetECISegments()
```

**Return Value**

Returns an array of [`ECISegment`]({{ site.dbr_dotnet_api }}eci-segment.html) objects. Returns an empty array if no ECI information is present.

**See Also**

[ECISegment]({{ site.dbr_dotnet_api }}eci-segment.html)

**Remarks**

Introduced in Dynamsoft Barcode Reader SDK version 11.4.1000 and Dynamsoft Capture Vision version 3.4.1000.

