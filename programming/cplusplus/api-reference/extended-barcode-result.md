---
layout: default-layout
title: CExtendedBarcodeResult Class - Dynamsoft Barcode Reader C++ Edition API Reference
description: This page shows CExtendedBarcodeResult class definition of Dynamsoft Barcode Reader SDK C++ Edition.
keywords: GetDeformation, GetClarity, GetSamplingImage, GetExtendedBarcodeResultType, CExtendedBarcodeResult, api reference
---
# CExtendedBarcodeResult Class

The `CExtendedBarcodeResult` class represents an extended barcode result in a decoded barcode element. It contains information such as the type of extended barcode, deformation, clarity, and a sampling image of the barcode.

## Definition

*Namespace:* dynamsoft::dbr

*Assembly:* DynamsoftBarcodeReader

*Inheritance:* [CDecodedBarcodeElement]({{ site.dbr_cpp_api }}decoded-barcode-element.html) -> CExtendedBarcodeResult

```cpp
class CExtendedBarcodeResult : public CDecodedBarcodeElement
```

## Methods

| Method | Description |
|--------|-------------|
| [`GetExtendedBarcodeResultType`](#getextendedbarcoderesulttype) | Gets the type of extended barcode result. |
| [`GetDeformation`](#getdeformation) | Gets the deformation of the barcode. |
| [`GetClarity`](#getclarity) | Gets the clarity of the barcode. |
| [`GetSamplingImage`](#getsamplingimage) | Gets the sampling image of the barcode. |
| **Methods Inherited from [CDecodedBarcodeElement]({{ site.dbr_cpp_api }}decoded-barcode-element.html):** | |
| [`GetFormat`]({{ site.dbr_cpp_api }}decoded-barcode-element.html#getformat) | Gets the format of the barcode. |
| [`GetFormatString`]({{ site.dbr_cpp_api }}decoded-barcode-element.html#getformatstring) | Gets the string representation of the barcode format. |
| [`GetText`]({{ site.dbr_cpp_api }}decoded-barcode-element.html#gettext) | Gets the text of the decoded barcode. |
| [`GetBytes`]({{ site.dbr_cpp_api }}decoded-barcode-element.html#getbytes) | Gets the raw bytes of the decoded barcode. |
| [`GetBytesLength`]({{ site.dbr_cpp_api }}decoded-barcode-element.html#getbyteslength) | Gets the length of the raw bytes of the decoded barcode. |
| [`GetDetails`]({{ site.dbr_cpp_api }}decoded-barcode-element.html#getdetails) | Gets the details of the decoded barcode. |
| [`IsDPM`]({{ site.dbr_cpp_api }}decoded-barcode-element.html#isdpm) | Determines whether the decoded barcode is a DPM code. |
| [`IsMirrored`]({{ site.dbr_cpp_api }}decoded-barcode-element.html#ismirrored) | Determines whether the decoded barcode is mirrored. |
| [`GetAngle`]({{ site.dbr_cpp_api }}decoded-barcode-element.html#getangle) | Gets the orientation angle of the barcode. |
| [`GetModuleSize`]({{ site.dbr_cpp_api }}decoded-barcode-element.html#getmodulesize) | Gets the module size of the barcode. |
| [`GetConfidence`]({{ site.dbr_cpp_api }}decoded-barcode-element.html#getconfidence) | Gets the confidence score of the barcode recognition result. |

### GetExtendedBarcodeResultType

Gets the type of extended barcode result.

```cpp
virtual ExtendedBarcodeResultType GetExtendedBarcodeResultType() const = 0;
```

**Return value**

Returns the type of the extended barcode result.

**See Also**

[Enumeration ExtendedBarcodeResultType]({{ site.dbr_cpp_api }}enum-extended-barcode-result-type.html?src=cpp&&lang=cpp)

### GetDeformation

Gets the deformation of the barcode.

```cpp
virtual int GetDeformation() const = 0;
```

**Return value**

Returns the deformation of the barcode.

### GetClarity

Gets the clarity of the barcode.

```cpp
virtual int GetClarity() const = 0;
```

**Return value**

Returns the clarity of the barcode.

### GetSamplingImage

Gets the sampling image of the barcode.

```cpp
virtual const CImageData* GetSamplingImage() const = 0;
```

**Return value**

Returns a pointer to the sampling image of the barcode.

**See Also**

[CImageData]({{ site.dcvb_cpp_api }}core/basic-structures/image-data.html)
