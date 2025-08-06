---
layout: default-layout
title: DeformationResistedBarcode Class - Dynamsoft Barcode Reader Java Edition API Reference
description: This page shows DeformationResistedBarcode class definition of Dynamsoft Barcode Reader SDK Java Edition.
keywords: getLocation, setLocation, getFormat, setFormat, getImageData, setImageData, DeformationResistedBarcode, api reference
---
# DeformationResistedBarcode Class

The `DeformationResistedBarcode` class represents a deformation resisted barcode.

## Definition

*Package:* com.dynamsoft.dbr.intermediate_results

```java
public class DeformationResistedBarcode
```

## Methods

| Method                            | Description |
|-----------------------------------|-------------|
| [`DeformationResistedBarcode`](#deformationresistedbarcode) | Initializes a new instance of the `DeformationResistedBarcode` class. |
| [`getFormat`](#getformat)           | Gets the format of the deformation resisted barcode. |
| [`setFormat`](#setformat)           | Sets the format of the deformation resisted barcode. |
| [`getImageData`](#getimagedata)           | Gets the deformation resisted barcode image. |
| [`setImageData`](#setimagedata)           | Sets the deformation resisted barcode image. |
| [`getLocation`](#getlocation)           | Gets the location of the deformation resisted barcode.|
| [`setLocation`](#setlocation)           | Sets the location of the deformation resisted barcode.|


### DeformationResistedBarcode

Initializes a new instance of the `DeformationResistedBarcode` class.

```java
public DeformationResistedBarcode()
public DeformationResistedBarcode(ImageData img, Quadrilateral location, long format)
```

**Parameters**

`img` The barcode image data.

`location` The location of the deformation resisted barcode.

`format` The format of the deformation resisted barcode.

**See Also**

[ImageData]({{ site.dcvb_java_api }}core/basic-classes/image-data.html)

[Quadrilateral]({{ site.dcvb_java_api }}core/basic-classes/quadrilateral.html)

[EnumBarcodeFormat]({{ site.dbr_java_api }}enum-barcode-format.html)

### getFormat

Gets the format of the deformation resisted barcode.

```java
public @EnumBarcodeFormat long getFormat()
```

**Return value**

Returns the format of the deformation resisted barcode.

**See Also**

[EnumBarcodeFormat]({{ site.dbr_java_api }}enum-barcode-format.html)

### setFormat

Sets the format of the deformation resisted barcode.

```java
public void setFormat(long format)
```

**Parameters**

`format` The format of the deformation resisted barcode.

**See Also**

[EnumBarcodeFormat]({{ site.dbr_java_api }}enum-barcode-format.html)

### getImageData

Gets the deformation resisted barcode image.

```java
public ImageData getImageData()
```

**Return value**

Returns the deformation resisted barcode image.

**See Also**

[ImageData]({{ site.dcvb_java_api }}core/basic-classes/image-data.html)

### setImageData

Sets the deformation resisted barcode image.

```java
public void setImageData(ImageData imgData)
```

**Parameters**

`imgData` The deformation resisted barcode image.

**See Also**

[ImageData]({{ site.dcvb_java_api }}core/basic-classes/image-data.html)

### getLocation

Gets the location of the deformation resisted barcode.

```java
public Quadrilateral getLocation()
```

**Return value**

Returns the location of the deformation resisted barcode.

**See Also**

[Quadrilateral]({{ site.dcvb_java_api }}core/basic-classes/quadrilateral.html)

### setLocation

Sets the location of the deformation resisted barcode.

```java
public void setLocation(Quadrilateral location)
```

**Parameters**

`location` The location of the deformation resisted barcode. 

**See Also**

[Quadrilateral]({{ site.dcvb_java_api }}core/basic-classes/quadrilateral.html)

