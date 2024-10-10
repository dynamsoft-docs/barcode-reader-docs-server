---
layout: default-layout
title: CDecodedBarcodeElement Class - Dynamsoft Barcode Reader C++ Edition API Reference
description: This page shows CDecodedBarcodeElement class definition of Dynamsoft Barcode Reader SDK C++ Edition.
keywords: GetFormat, GetText, GetBytes, GetAngle, GetConfidence, IsDPM, CDecodedBarcodeElement, api reference
---
# CDecodedBarcodeElement Class

The `CDecodedBarcodeElement` class represents a decoded barcode element. It inherits from the `CRegionObjectElement` class and provides additional functionality for retrieving information about the decoded barcode.

## Definition

*Namespace:* dynamsoft::dbr

*Assembly:* DynamsoftBarcodeReader

*Inheritance:* [CRegionObjectElement]({{ site.dcvb_cpp_api }}core/intermediate-results/region-object-element.html) -> CDecodedBarcodeElement

```cpp
class CDecodedBarcodeElement : public CRegionObjectElement
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
| [`SetFormat`](#setformat) | Sets the format of the barcode. |
| [`SetText`](#settext) | Sets the text of the decoded barcode. |
| [`SetBytes`](#setbytes)| Sets the raw bytes of the decoded barcode.|
| [`SetConfidence`](#setconfidence) | Sets the confidence score of the barcode recognition result. |

### Inherited Methods

{%- include inherited-methods/region-object-element.md -%}

### GetFormat

It is used to get the format of the barcode.

```cpp
BarcodeFormat GetFormat()
```

**Return value**

Returns the format of the barcode.

**See Also**

[Enumeration BarcodeFormat]({{ site.dcvb_enumerations }}barcode-reader/barcode-format.html?src=cpp&&lang=cpp)

### GetFormatString

It is used to get the string representation of the barcode format.

```cpp
const char* GetFormatString() const
```

**Return value**

Returns the string representation of the barcode format.

### GetText

Gets the text of the decoded barcode.

```cpp
virtual const char* GetText() const = 0;
```

**Return value**

Returns a pointer to the text of the decoded barcode.

### GetBytes

Gets the raw bytes of the decoded barcode.

```cpp
virtual unsigned char* GetBytes() const = 0;
```

**Return value**

Returns a pointer to the raw bytes of the decoded barcode.

### GetBytesLength

Gets the length of the raw bytes of the decoded barcode.

```cpp
virtual int GetBytesLength() const = 0;
```

**Return value**

Returns the length of the raw bytes of the decoded barcode.

### GetDetails

Gets the details of the decoded barcode.

```cpp
virtual const CBarcodeDetails* GetDetails() const = 0;
```

**Return value**

Returns a pointer to the details of the decoded barcode.

**See Also**

- [CAztecDetails]({{ site.dbr_cpp_api }}aztec-details.html)
- [CBarcodeDetails]({{ site.dbr_cpp_api }}barcode-details.html)
- [CDataMatrixDetails]({{ site.dbr_cpp_api }}datamatrix-details.html)
- [COneDCodeDetails]({{ site.dbr_cpp_api }}oned-code-details.html)
- [CPDF417Details]({{ site.dbr_cpp_api }}pdf417-details.html)
- [CQRCodeDetails]({{ site.dbr_cpp_api }}qr-code-details.html)

### IsDPM

Determines whether the decoded barcode is a DPM (Direct Part Marking) code.

```cpp
virtual bool IsDPM() const = 0;
```

**Return value**

Returns true if the decoded barcode is a DPM code, false otherwise.

### IsMirrored

Determines whether the decoded barcode is mirrored.

```cpp
virtual bool IsMirrored() const = 0;
```

**Return value**

Returns true if the decoded barcode is mirrored, false otherwise.

### GetAngle

It is used to get the orientation angle of the barcode.

```cpp
int GetAngle() const
```

**Return value**

Returns the orientation angle of the barcode.

### GetModuleSize

It is used to get the module size of the barcode.

```cpp
int GetModuleSize() const
```

**Return value**

Returns the module size of the barcode.

### GetConfidence

It is used to get the confidence score of the barcode recognition result.

```cpp
int GetConfidence() const
```

**Return value**

Returns the confidence score of the barcode recognition result.

### GetExtendedBarcodeResultsCount

Gets the number of extended barcode results for the decoded barcode.

```cpp
virtual int GetExtendedBarcodeResultsCount() const = 0;
```

**Return value**

Returns the number of extended barcode results for the decoded barcode.

### GetExtendedBarcodeResult

Gets the extended barcode result at the specified index for the decoded barcode.

```cpp
virtual const CExtendedBarcodeResult* GetExtendedBarcodeResult(int index) const = 0;
```

**Parameters**

`[in] index` The index of the extended barcode result to retrieve.

**Return value**

Returns a pointer to the extended barcode result at the specified index for the decoded barcode.

**See Also**

[CExtendedBarcodeResult]({{ site.dbr_cpp_api }}extended-barcode-result.html)

### SetFormat

Sets the format of the barcode.

```cpp
virtual void SetFormat(BarcodeFormat format) = 0;
```

**Parameters**

`[in] format` The format of the barcode.

**See Also**

[Enumeration BarcodeFormat]({{ site.dcvb_enumerations }}barcode-reader/barcode-format.html?src=cpp&&lang=cpp)

### SetText

Sets the text of the barcode.

```cpp
virtual void SetText(const char* text) = 0;
```

**Parameters**

`[in] text` The text of the barcode.

### SetBytes

Sets the raw bytes of the barcode.

```cpp
virtual void SetBytes(unsigned char* bytes, int bytesLength) = 0;
```

**Parameters**

`[in] bytes` The raw bytes of the barcode.

`[in] bytesLength` The length of the raw bytes of the decoded barcode.

### SetConfidence

Sets the confidence of the barcode.

```cpp
virtual void SetConfidence(int confidence) = 0;
```

**Parameters**

`[in] confidence` The confidence of the barcode.

