---
layout: default-layout
title: CCandidateBarcodeZone Class
description: This page shows CCandidateBarcodeZone class definition of Dynamsoft Barcode Reader SDK C++ Edition.
keywords: GetLocation, SetLocation, GetPossibleFormats, SetPossibleFormats, CCandidateBarcodeZone, api reference
---
# CCandidateBarcodeZone Class

The `CCandidateBarcodeZone` class represents a candidate zone for barcode detection.

## Definition

*Namespace:* dynamsoft::dbr::intermediate_results

*Assembly:* DynamsoftBarcodeReader

```cpp
class CCandidateBarcodeZone
```

## Methods

| Method                            | Description |
|-----------------------------------|-------------|
| [`CCandidateBarcodeZone`](#ccandidatebarcodezone-default-constructor)           | Constructs a CCandidateBarcodeZone object with default parameters. |
| [`CCandidateBarcodeZone(const CQuadrilateral& location, unsigned long long possibleFormats)`](#ccandidatebarcodezone-constructor)           | Constructs a CCandidateBarcodeZone object with the specified parameters. |
| [`GetLocation`](#getlocation)           | Gets the location of the candidate barcode.|
| [`SetLocation`](#setlocation)           | Sets the location of the candidate barcode.|
| [`GetPossibleFormats`](#getpossibleformats)           | Gets the posssible formats of the candidate barcode. |
| [`SetPossibleFormats`](#setpossibleformats)           | Sets the posssible formats of the candidate barcode. |


### CCandidateBarcodeZone Default Constructor

Constructs a CCandidateBarcodeZone object with default parameters.

```cpp
CCandidateBarcodeZone()
```

### CCandidateBarcodeZone Constructor

Constructs a CCandidateBarcodeZone object with the specified parameters.

```cpp
CCandidateBarcodeZone(const CQuadrilateral& location, unsigned long long possibleFormats)
```

**Parameters**

`location` The location of the candidate barcode.

`possibleFormats` The posssible formats of the candidate barcode.

### GetLocation

Gets the location of the candidate barcode.

```cpp
CQuadrilateral GetLocation() const;
```

**Return value**

Returns the location of the candidate barcode.

**See Also**

[CQuadrilateral]({{ site.dcv_cpp_api }}core/basic-structures/quadrilateral.html)

### SetLocation

Sets the location of the candidate barcode.

```cpp
void SetLocation(const CQuadrilateral& loc); 
```

**Parameters**

`loc` The location of the candidate barcode. 

**See Also**

[CQuadrilateral]({{ site.dcv_cpp_api }}core/basic-structures/quadrilateral.html)

### GetPossibleFormats

Gets the posssible formats of the candidate barcode.

```cpp
unsigned long long GetPossibleFormats() const;
```

**Return value**

Returns the posssible formats of the candidate barcode.

**See Also**

[BarcodeFormat]({{ site.dcv_enumerations }}barcode-reader/barcode-format.html?src=cpp&&lang=cpp)

### SetPossibleFormats

Sets the posssible formats of the candidate barcode.

```cpp
void SetPossibleFormats(unsigned long long formats);
```

**Parameters**

`formats` The posssible formats of the candidate barcode.

**See Also**

[BarcodeFormat]({{ site.dcv_enumerations }}barcode-reader/barcode-format.html?src=cpp&&lang=cpp)