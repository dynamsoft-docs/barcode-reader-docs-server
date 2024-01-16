---
layout: default-layout
title: CDeformationResistedBarcode Class
description: This page shows CDeformationResistedBarcode class definition of Dynamsoft Barcode Reader SDK C++ Edition.
keywords: GetLocation, SetLocation, GetFormat, SetFormat, GetImageData, SetImageData, CDeformationResistedBarcode, api reference
---
# CDeformationResistedBarcode Class

The `CDeformationResistedBarcode` class represents a deformation resisted barcode.

## Definition

*Namespace:* dynamsoft::dbr::intermediate_results

*Assembly:* DynamsoftBarcodeReader

```cpp
class CDeformationResistedBarcode
```

## Methods

| Method                            | Description |
|-----------------------------------|-------------|
| [`CDeformationResistedBarcode`](#cdeformationresistedbarcode-default-constructor)           | Constructs a `CDeformationResistedBarcode` object with default parameters. |
| [`CDeformationResistedBarcode(CDeformationResistedBarcode&& barcode)`](#cdeformationresistedbarcode-move-constructor)           | Move constructor for `CDeformationResistedBarcode`. |
| [`CDeformationResistedBarcode(const CImageData* img, FreeImageFunc freeImageFunc, const CQuadrilateral& location, BarcodeFormat format)`](#cdeformationresistedbarcode-constructor)           | Constructs a new `CDeformationResistedBarcode` object with the specified parameters. |
| [`GetFormat`](#getformat)           | Gets the format of the deformation resisted barcode. |
| [`SetFormat`](#setformat)           | Sets the format of the deformation resisted barcode. |
| [`GetImageData`](#getimagedata)           | Gets the deformation resisted barcode image. |
| [`SetImageData`](#setimagedata)           | Sets the deformation resisted barcode image. |
| [`GetLocation`](#getlocation)           | Gets the location of the deformation resisted barcode.|
| [`SetLocation`](#setlocation)           | Sets the location of the deformation resisted barcode.|
| [`operator=`](#operator)           | Move assignment operator for `CDeformationResistedBarcode`.|


### CDeformationResistedBarcode Default Constructor

Constructs a `CDeformationResistedBarcode` object with default parameters.

```cpp
CDeformationResistedBarcode();
```

### CDeformationResistedBarcode Move Constructor

Move constructor for `CDeformationResistedBarcode`.

```cpp
CDeformationResistedBarcode(CDeformationResistedBarcode&& barcode);
```

### CDeformationResistedBarcode Constructor

Constructs a `CDeformationResistedBarcode` object with the specified parameters.

```cpp
CDeformationResistedBarcode(const CImageData* img, FreeImageFunc freeImageFunc, const CQuadrilateral& location, BarcodeFormat format);
```

**Parameters**

`img` The pointer to the deformation resisted barcode image.

`freeImageFunc` The function pointer to free image.

`location` The location of the deformation resisted barcode.

`format` The format of the deformation resisted barcode.

### GetFormat

Gets the format of the deformation resisted barcode.

```cpp
BarcodeFormat GetFormat() const;
```

**Return value**

Returns the format of the deformation resisted barcode.

**See Also**

[BarcodeFormat]({{ site.dcv_enumerations }}barcode-reader/barcode-format.html?src=cpp&&lang=cpp)

### SetFormat

Sets the format of the deformation resisted barcode.

```cpp
void SetFormat(BarcodeFormat format);
```

**Parameters**

`format` The format of the deformation resisted barcode.

**See Also**

[BarcodeFormat]({{ site.dcv_enumerations }}barcode-reader/barcode-format.html?src=cpp&&lang=cpp)

### GetImageData

Gets the deformation resisted barcode image.

```cpp
const CImageData* GetImageData() const;
```

**Return value**

Returns the pointer to the deformation resisted barcode image.

**See Also**

[CImageData]({{ site.dcv_cpp_api }}core/basic-structures/image-data.html)

### SetImageData

Sets the deformation resisted barcode image.

```cpp
void SetImageData(const CImageData* img, FreeImageFunc freeImageFunc);
```

**Parameters**

`img` The pointer to the deformation resisted barcode image.

`freeImageFunc` The function pointer to free image.

**See Also**

[CImageData]({{ site.dcv_cpp_api }}core/basic-structures/image-data.html)

### GetLocation

Gets the location of the deformation resisted barcode.

```cpp
CQuadrilateral GetLocation() const;
```

**Return value**

Returns the location of the deformation resisted barcode.

**See Also**

[CQuadrilateral]({{ site.dcv_cpp_api }}core/basic-structures/quadrilateral.html)

### SetLocation

Sets the location of the deformation resisted barcode.

```cpp
void SetLocation(const CQuadrilateral& loc); 
```

**Parameters**

`loc` The location of the deformation resisted barcode. 

**See Also**

[CQuadrilateral]({{ site.dcv_cpp_api }}core/basic-structures/quadrilateral.html)

### operator=

Move assignment operator for `CDeformationResistedBarcode`.

```cpp
CDeformationResistedBarcode& operator=(CDeformationResistedBarcode&& barcode);
```

**Parameters**

`barcode` The rvalue reference to another `CDeformationResistedBarcode` object. 

**Return value**

A reference to the moved `CDeformationResistedBarcode` object.
