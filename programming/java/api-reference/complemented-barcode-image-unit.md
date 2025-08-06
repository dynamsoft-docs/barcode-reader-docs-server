---
layout: default-layout
title: ComplementedBarcodeImageUnit Class - Dynamsoft Barcode Reader Java Edition API Reference
description: This page shows ComplementedBarcodeImageUnit class definition of Dynamsoft Barcode Reader SDK Java Edition.
keywords: getImageData, getLocation, setLocation, ComplementedBarcodeImageUnit, api reference
---
# ComplementedBarcodeImageUnit Class
The `ComplementedBarcodeImageUnit` class represents a unit that contains complemented barcode image data. It inherits from the `IntermediateResultUnit` class.

## Definition

*Package:* com.dynamsoft.dbr.intermediate_results

*Inheritance:* [IntermediateResultUnit]({{ site.dcvb_java_api }}core/intermediate-results/intermediate-result-unit.html) -> ComplementedBarcodeImageUnit

```java
public class ComplementedBarcodeImageUnit extends IntermediateResultUnit
```

## Methods

| Method                            | Description |
|-----------------------------------|-------------|
| [`getImageData`](#getimagedata) | Gets the complemented barcode image data.|
| [`getLocation`](#getlocation) | Gets the location of the complemented barcode in a quadrilateral.|
| [`setLocation`](#setlocation) | Sets the location of the complemented barcode in a quadrilateral.|

### getImageData

Gets the complemented barcode image data.

```java
public ImageData getImageData()
```

**Return value**

Returns the complemented image of the barcode.

**See Also**

[ImageData]({{ site.dcvb_java_api }}core/basic-classes/image-data.html)

### getLocation

Gets the location of the complemented barcode in a quadrilateral.

```java
public Quadrilateral getLocation()
```

**Return value**

Returns the location of the complemented barcode in a quadrilateral.

**See Also**

[Quadrilateral]({{ site.dcvb_java_api }}core/basic-classes/quadrilateral.html)

### setLocation

Sets the location of the complemented barcode in a quadrilateral.

```java
public void setLocation(Quadrilateral location)
public void setLocation(Quadrilateral location, double[] matrixToOriginalImage)
```

**Parameters**

`location` The location of the complemented barcode.

`matrixToOriginalImage` The matrix to original image. The array length must be 9.

**Exceptions**

`IllegalArgumentException` If the `matrixToOriginalImage` array length is not 9.

**See Also**

[Quadrilateral]({{ site.dcvb_java_api }}core/basic-classes/quadrilateral.html)

