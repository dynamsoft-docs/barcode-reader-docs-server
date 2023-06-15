---
layout: default-layout
title: CLocalizedBarcodeElement Class
description: This page shows CLocalizedBarcodeElement class definition of Dynamsoft Barcode Reader SDK C++ Edition.
keywords: GetAngle, GetConfidence, GetFormat, GetFormatString, GetModuleSize, CLocalizedBarcodeElement, api reference
permalink: /programming/cplusplus/api-reference/localized-barcode-element.html
---
# CLocalizedBarcodeElement Class

The `CLocalizedBarcodeElement` class represents a localized barcode element detected in an image. It is inherited from `CRegionObjectElement` class.

## Definition

*Namespace:* dynamsoft::dbr

*Assembly:* DynamsoftBarcodeReader

```cpp
class CLocalizedBarcodeElement : public CRegionObjectElement
```

## Methods

| Method | Description |
|--------|-------------|
| [`GetAngle`](#getangle) | Gets the orientation angle of the barcode. |
| [`GetConfidence`](#getconfidence) | Gets the confidence score of the barcode recognition result. |
| [`GetPossibleFormats`](#getpossibleformats) | Gets the possible format of the barcode. |
| [`GetPossibleFormatsString`](#getpossibleformatsstring) | Gets the string representation of the possible barcode format. |
| [`GetModuleSize`](#getmodulesize) | Gets the module size of the barcode. |

### GetAngle

It is used to get the orientation angle of the barcode.

```cpp
int GetAngle() const
```

**Return value**

Returns the orientation angle of the barcode.

### GetConfidence

It is used to get the confidence score of the barcode recognition result.

```cpp
int GetConfidence() const
```

**Return value**

Returns the confidence score of the barcode recognition result.

### GetPossibleFormats

It is used to get the format of the barcode.

```cpp
unsigned long long GetPossibleFormats()
```

**Return value**

Returns the format of the barcode.

### GetPossibleFormatsString

It is used to get the string representation of the barcode format.

```cpp
const char* GetPossibleFormatsString() const
```

**Return value**

Returns the string representation of the barcode format.

### GetModuleSize

It is used to get the module size of the barcode.

```cpp
int GetModuleSize() const
```

**Return value**

Returns the module size of the barcode.
