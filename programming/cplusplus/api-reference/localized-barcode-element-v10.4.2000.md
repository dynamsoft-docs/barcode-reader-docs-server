---
layout: default-layout
title: CLocalizedBarcodeElement Class - Dynamsoft Barcode Reader C++ Edition API Reference
description: This page shows CLocalizedBarcodeElement class definition of Dynamsoft Barcode Reader SDK C++ Edition.
keywords: GetAngle, GetConfidence, GetPossibleFormats, GetPossibleFormatsString, GetModuleSize, SetPossibleFormats, CLocalizedBarcodeElement, api reference
---
# CLocalizedBarcodeElement Class

The `CLocalizedBarcodeElement` class represents a localized barcode element detected in an image. It is inherited from `CRegionObjectElement` class.

## Definition

*Namespace:* dynamsoft::dbr

*Assembly:* DynamsoftBarcodeReader

*Inheritance:* [CRegionObjectElement]({{ site.dcvb_cpp_api }}core/intermediate-results/region-object-element.html) -> CLocalizedBarcodeElement

```cpp
class CLocalizedBarcodeElement : public CRegionObjectElement
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

### Inherited Methods

{%- include inherited-methods/region-object-element.md -%}

### GetAngle

It is used to get the orientation angle of the barcode.

```cpp
int GetAngle() const
```

**Return value**

Returns the orientation angle of the barcode.

### GetConfidence

It is used to get the confidence score of the barcode localization result.

```cpp
int GetConfidence() const
```

**Return value**

Returns the confidence score of the barcode recognition result. It represents the confidence that the positioning area is a barcode.

### GetPossibleFormats

It is used to get the format of the barcode.

```cpp
unsigned long long GetPossibleFormats()
```

**Return value**

Returns the format of the barcode.

**See Also**

[Enumeration BarcodeFormat]({{ site.dbr_cpp_api }}enum-barcode-format.html?src=cpp&&lang=cpp)

### GetPossibleFormatsString

It is used to get all possible formats of the localized barcode in one string splited by ",".

```cpp
const char* GetPossibleFormatsString() const
```

**Return value**

Returns the string representation of the barcode format in one string splited by ",".

### GetModuleSize

It is used to get the module size of the barcode.

```cpp
int GetModuleSize() const
```

**Return value**

Returns the module size of the barcode.

### SetPossibleFormats

Sets the posssible formats of the barcode.

```cpp
virtual void SetPossibleFormats(unsigned long long possibleFormats) = 0;
```

**Parameters**

`possibleFormats` The posssible formats of the barcode.

**See Also**

[BarcodeFormat]({{ site.dbr_cpp_api }}enum-barcode-format.html?src=cpp&&lang=cpp)