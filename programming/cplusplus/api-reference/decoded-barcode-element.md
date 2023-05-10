---
layout: default-layout
title: CDecodedBarcodeElement Class
description: This page shows CDecodedBarcodeElement class definition of Dynamsoft Barcode Reader SDK C++ Edition.
keywords: GetText, GetBytes, GetBytesLength, CDecodedBarcodeElement, api reference
permalink: /programming/cplusplus/api-reference/decoded-barcode-element.html
---
# CDecodedBarcodeElement Class

The `CDecodedBarcodeElement` class represents a decoded barcode element. It inherits from the `CRegionObjectElement` class and provides additional functionality for retrieving information about the decoded barcode.

## Definition

*Namespace:* dynamsoft::dbr

*Assembly:* DynamsoftBarcodeReader.dll

```cpp
class CDecodedBarcodeElement : public CRegionObjectElement
```

## Methods

| Method | Description |
| --- | --- |
| [`~CDecodedBarcodeElement`](#cdecodedbarcodeelement) | Destructor. |
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

### ~CDecodedBarcodeElement

Destructor.

```cpp
virtual ~CDecodedBarcodeElement() {}
```

### GetFormat

It is used to get the format of the barcode.

```cpp
BarcodeFormat GetFormat()
```

**Return value**

Returns the format of the barcode.

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
