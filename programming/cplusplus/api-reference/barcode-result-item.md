---
layout: default-layout
title: CBarcodeResultItem Class - Dynamsoft Barcode Reader C++ Edition API Reference
description: This page shows CBarcodeResultItem class definition of Dynamsoft Barcode Reader SDK C++ Edition.
keywords: GetFormat, GetText, GetLocation, GetConfidence, GetModuleSize, CBarcodeResultItem, api reference
---

# CBarcodeResultItem Class

The `CBarcodeResultItem` class represents a barcode result item decoded by barcode reader engine. It is derived from `CCapturedResultItem`.

## Definition

*Namespace:* dynamsoft::dbr

*Assembly:* DynamsoftBarcodeReader

*Inheritance:* [CCapturedResultItem]({{ site.dcvb_cpp_api }}core/basic-structures/captured-result-item.html) -> CBarcodeResultItem

```cpp
class CBarcodeResultItem : public CCapturedResultItem
```

## Methods

| Method               | Description |
|----------------------|-------------|
| [`GetFormat`](#getformat) | Gets the format of the decoded barcode result. |
| [`GetFormatString`](#getformatstring) | Gets the format string of the decoded barcode result. |
| [`GetText`](#gettext) | Gets the text result of the decoded barcode. |
| [`GetBytes`](#getbytes) | Gets the text bytes of the decoded barcode result. |
| [`GetBytesLength`](#getbyteslength) | Gets the text length of the decoded barcode result. |
| [`GetLocation`](#getlocation) | Gets the location of the decoded barcode in a quadrilateral. |
| [`GetConfidence`](#getconfidence) | Gets the confidence of the decoded barcode result. |
| [`GetAngle`](#getangle) | Gets the angle of the decoded barcode result. |
| [`GetModuleSize`](#getmodulesize) | Gets the module size of the decoded barcode result. |
| [`GetDetails`](#getdetails) | Gets the details of the decoded barcode result. |
| [`IsDPM`](#isdpm) | Gets whether the decoded barcode is a DPM code. |
| [`IsMirrored`](#ismirrored) | Gets whether the decoded barcode is a mirrored barcode. |
| [`SetLocation`](#setlocation) | Set the location of the barcode item. |
| Inherited Methods from [CCapturedResultItem]({{ site.dcvb_cpp_api }}core/basic-structures/captured-result-item.html): | |
| [`GetType`]({{ site.dcvb_cpp_api }}core/basic-structures/captured-result-item.html#gettype) | Gets the type of the captured result item. |
| [`GetReferenceItem`]({{ site.dcvb_cpp_api }}core/basic-structures/captured-result-item.html#getreferenceitem) | Gets a pointer to the referenced item in the captured result. |
| [`GetTargetROIDefName`]({{ site.dcvb_cpp_api }}core/basic-structures/captured-result-item.html#gettargetroidefname) | Gets the name of the target ROI definition. |
| [`GetTaskName`]({{ site.dcvb_cpp_api }}core/basic-structures/captured-result-item.html#gettaskname) | Gets the name of the task. |
| [`Retain`]({{ site.dcvb_cpp_api }}core/basic-structures/captured-result-item.html#retain) | Increases the reference count of the `CCapturedResultItem` object. |
| [`Release`]({{ site.dcvb_cpp_api }}core/basic-structures/captured-result-item.html#release) | Decreases the reference count of the `CCapturedResultItem` object. |
| [`Clone`]({{ site.dcvb_cpp_api }}core/basic-structures/captured-result-item.html#clone) | Clone the captured result item. |

### GetFormat

It is used to get the format of the decoded barcode result.

```cpp
virtual BarcodeFormat GetFormat() const = 0;
```

**Return value**

Returns the format of the decoded barcode result.

**See Also**

[Enumeration BarcodeFormat]({{ site.dbr_cpp_api }}enum-barcode-format.html?src=cpp&&lang=cpp)

### GetFormatString

It is used to get the format string of the decoded barcode result.

```cpp
virtual const char* GetFormatString() const = 0;
```

**Return value**

Returns the format string of the decoded barcode result.

### GetText

It is used to get the text result of the decoded barcode.

```cpp
virtual const char* GetText() const = 0;
```

**Return value**

Returns the text result of the decoded barcode.

### GetBytes

It is used to get the text bytes of the decoded barcode result.

```cpp
virtual unsigned char* GetBytes() const = 0;
```

**Return value**

Returns the text bytes of the decoded barcode result.

### GetBytesLength

It is used to get the text bytes length of the decoded barcode result.

```cpp
virtual int GetBytesLength() const = 0;
```

**Return value**

Returns the text bytes length of the decoded barcode result.

### GetLocation

It is used to get the location of the decoded barcode in a quadrilateral.

```cpp
virtual CQuadrilateral GetLocation() const = 0;
```

**Return value**

Returns the location of the decoded barcode in a quadrilateral.

**See Also**

[CQuadrilateral]({{ site.dcvb_cpp_api }}core/basic-structures/quadrilateral.html)

### GetConfidence

It is used to get the confidence of the decoded barcode result.

```cpp
virtual int GetConfidence() const = 0;
```

**Return value**

Returns the confidence of the decoded barcode result.

### GetAngle

It is used to get the angle of the decoded barcode result.

```cpp
virtual int GetAngle() const = 0;
```

**Return value**

Returns the angle of the decoded barcode result.

**See Also**

[How the angle is calculated for different barcode types]({{site.features}}get-confidence-rotation.html?lang=cpp#barcode-rotation-angle)

### GetModuleSize

It is used to get the module size of the decoded barcode result.

```cpp
virtual int GetModuleSize() const = 0;
```

**Return value**

Returns the module size of the decoded barcode result.

### GetDetails

It is used to get the details of the decoded barcode result.

```cpp
virtual const CBarcodeDetails* GetDetails() const = 0;	
```

**Return value**

Returns the details of the decoded barcode result.

**See Also**

- [CAztecDetails]({{ site.dbr_cpp_api }}aztec-details.html)
- [CBarcodeDetails]({{ site.dbr_cpp_api }}barcode-details.html)
- [CDataMatrixDetails]({{ site.dbr_cpp_api }}datamatrix-details.html)
- [COneDCodeDetails]({{ site.dbr_cpp_api }}oned-code-details.html)
- [CPDF417Details]({{ site.dbr_cpp_api }}pdf417-details.html)
- [CQRCodeDetails]({{ site.dbr_cpp_api }}qr-code-details.html)

### IsDPM

It is used to get whether the decoded barcode is a DPM code.

```cpp
virtual bool IsDPM() const = 0;
```

**Return value**

Returns whether the decoded barcode is a DPM code.

### IsMirrored

It is used to get whether the decoded barcode is mirrored.

```cpp
virtual bool IsMirrored() const = 0;
```

**Return value**

Returns whether the decoded barcode is mirrored.

### SetLocation

Set the location of the barcode item.

```cpp
virtual int SetLocation(const CQuadrilateral& location) = 0;
```

**Parameters**

`[in] location` The location of the barcode item.

**Return value**

Returns an error code. Zero indicates success.

**See Also**

[CQuadrilateral]({{ site.dcvb_cpp_api }}core/basic-structures/quadrilateral.html)
