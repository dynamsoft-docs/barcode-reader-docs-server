---
layout: default-layout
title: DecodedBarcodeElement Class - Dynamsoft Barcode Reader .NET Edition API Reference
description: This page shows DecodedBarcodeElement class definition of Dynamsoft Barcode Reader SDK .NET Edition.
keywords: GetFormat, GetText, GetBytes, GetAngle, GetConfidence, IsDPM, DecodedBarcodeElement, api reference
---
# DecodedBarcodeElement Class

The `DecodedBarcodeElement` class represents a decoded barcode element. It inherits from the `RegionObjectElement` class and provides additional functionality for retrieving information about the decoded barcode.

## Definition

*Namespace:* Dynamsoft.DBR


*Inheritance:* [RegionObjectElement]({{ site.dcvb_dotnet_api }}core/intermediate-results/region-object-element.html) -> DecodedBarcodeElement

```csharp
class DecodedBarcodeElement : RegionObjectElement
```

## Methods

| Method | Description |
| --- | --- |
| [`GetFormat`](#getformat) | Gets the format of the barcode. |
| [`GetFormatString`](#getformatstring) | Gets the string representation of the barcode format. |
| [`GetText`](#gettext) | Gets the text of the decoded barcode. |
| [`GetBytes`](#getbytes)| Gets the raw bytes of the decoded barcode.|
| [`GetBytesLength`](#getbyteslength)  | Gets the length of the raw bytes of the decoded barcode.|
| [`GetDetails`](#getdetails) | Gets the details of the decoded barcode.|
| [`IsDPM`](#isdpm)| Determines whether the decoded barcode is a DPM (Direct Part Marking) code.|
| [`IsMirrored`](#ismirrored)| Determines whether the decoded barcode is mirrored.|
| [`GetAngle`](#getangle) | Gets the orientation angle of the barcode. |
| [`GetModuleSize`](#getmodulesize) | Gets the module size of the barcode. |
| [`GetConfidence`](#getconfidence) | Gets the confidence score of the barcode recognition result. |
| [`GetExtendedBarcodeResultsCount`](#getextendedbarcoderesultscount) | Gets the number of extended barcode results for the decoded barcode.|
| [`GetExtendedBarcodeResult`](#getextendedbarcoderesult) | Gets the extended barcode result at the specified index for the decoded barcode.|
| [`GetExtendedBarcodeResults`](#getextendedbarcoderesults) | Gets all the extended barcode results.|
| [`SetFormat`](#setformat) | Sets the format of the barcode. |
| [`SetText`](#settext) | Sets the text of the decoded barcode. |
| [`SetBytes`](#setbytes)| Sets the raw bytes of the decoded barcode.|
| [`SetConfidence`](#setconfidence) | Sets the confidence score of the barcode recognition result. |
| [`SetLocation`](#setlocation) | Sets the location of the current object. |
| [`GetECISegments`](#getecisegments) | Gets all the ECI segments in the barcode. |

### Inherited Methods

Checkout inherited methods from [RegionObjectElement]({{ site.dcvb_dotnet_api }}core/intermediate-results/region-object-element.html) for more details.

### GetFormat

It is used to get the format of the barcode.

```csharp
EnumBarcodeFormat GetFormat()
```

**Return value**

Returns the format of the barcode.

**See Also**

[EnumBarcodeFormat]({{ site.dbr_dotnet_api }}enum-barcode-format.html)

### GetFormatString

It is used to get the string representation of the barcode format.

```csharp
string GetFormatString()
```

**Return value**

Returns the string representation of the barcode format.

### GetText

Gets the text of the decoded barcode.

```csharp
string GetText()
```

**Return value**

Returns the text of the decoded barcode.

### GetBytes

Gets the raw bytes of the decoded barcode.

```csharp
byte[] GetBytes()
```

**Return value**

Returns the raw bytes of the decoded barcode.

### GetBytesLength

Gets the length of the raw bytes of the decoded barcode.

```csharp
int GetBytesLength()
```

**Return value**

Returns the length of the raw bytes of the decoded barcode.

### GetDetails

Gets the details of the decoded barcode.

```csharp
BarcodeDetails* GetDetails()
```

**Return value**

Returns the details of the decoded barcode.

**See Also**

- [AztecDetails]({{ site.dbr_dotnet_api }}aztec-details.html)
- [BarcodeDetails]({{ site.dbr_dotnet_api }}barcode-details.html)
- [DataMatrixDetails]({{ site.dbr_dotnet_api }}datamatrix-details.html)
- [OneDCodeDetails]({{ site.dbr_dotnet_api }}oned-code-details.html)
- [PDF417Details]({{ site.dbr_dotnet_api }}pdf417-details.html)
- [QRCodeDetails]({{ site.dbr_dotnet_api }}qr-code-details.html)

### IsDPM

Determines whether the decoded barcode is a DPM (Direct Part Marking) code.

```csharp
bool IsDPM()
```

**Return value**

Returns true if the decoded barcode is a DPM code, false otherwise.

### IsMirrored

Determines whether the decoded barcode is mirrored.

```csharp
bool IsMirrored()
```

**Return value**

Returns true if the decoded barcode is mirrored, false otherwise.

### GetAngle

It is used to get the orientation angle of the barcode.

```csharp
int GetAngle()
```

**Return value**

Returns the orientation angle of the barcode.

### GetModuleSize

It is used to get the module size of the barcode.

```csharp
int GetModuleSize()
```

**Return value**

Returns the module size of the barcode.

### GetConfidence

It is used to get the confidence score of the barcode recognition result.

```csharp
int GetConfidence()
```

**Return value**

Returns the confidence score of the barcode recognition result.

### GetExtendedBarcodeResultsCount

Gets the number of extended barcode results for the decoded barcode.

```csharp
int GetExtendedBarcodeResultsCount()
```

**Return value**

Returns the number of extended barcode results for the decoded barcode.

### GetExtendedBarcodeResult

Gets the extended barcode result at the specified index for the decoded barcode.

```csharp
ExtendedBarcodeResult GetExtendedBarcodeResult(int index)
```

**Parameters**

`[in] index` The index of the extended barcode result to retrieve.

**Return value**

Returns the extended barcode result at the specified index for the decoded barcode.

**See Also**

[ExtendedBarcodeResult]({{ site.dbr_dotnet_api }}extended-barcode-result.html)

### GetExtendedBarcodeResults

Gets all the extended barcode results.

```csharp
ExtendedBarcodeResult[] GetExtendedBarcodeResults()
```

**Return value**

Returns all the extended barcode results.

**See Also**

[ExtendedBarcodeResult]({{ site.dbr_dotnet_api }}extended-barcode-result.html)

### SetFormat

Sets the format of the barcode.

```csharp
void SetFormat(EnumBarcodeFormat format)
```

**Parameters**

`[in] format` The format of the barcode.

**See Also**

[EnumBarcodeFormat]({{ site.dbr_dotnet_api }}enum-barcode-format.html)

### SetText

Sets the text of the barcode.

```csharp
void SetText(string text)
```

**Parameters**

`[in] text` The text of the barcode.

### SetBytes

Sets the raw bytes of the barcode.

```csharp
void SetBytes(byte[] bytes)
```

**Parameters**

`[in] bytes` The raw bytes of the barcode.

### SetConfidence

Sets the confidence of the barcode.

```csharp
void SetConfidence(int confidence)
```

**Parameters**

`[in] confidence` The confidence of the barcode.

### SetLocation

Sets the location of the current object.

```csharp
void SetLocation(Quadrilateral location)
```

**Parameters**

`[in] location` The location of the barcode.

**See Also**

[Quadrilateral]({{ site.dcvb_dotnet_api }}core/basic-classes/quadrilateral.html)

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

