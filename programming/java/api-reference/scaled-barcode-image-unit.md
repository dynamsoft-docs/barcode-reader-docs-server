---
layout: default-layout
title: ScaledBarcodeImageUnit Class - Dynamsoft Barcode Reader Java Edition API Reference
description: This page shows ScaledBarcodeImageUnit class definition of Dynamsoft Barcode Reader SDK Java Edition.
keywords: getImageData, setImageData, ScaledBarcodeImageUnit, api reference
---
# ScaledBarcodeImageUnit Class

The `ScaledBarcodeImageUnit` class represents a unit that contains scaled barcode image. It inherits from the `IntermediateResultUnit` class.

## Definition

*Package:* com.dynamsoft.dbr.intermediate_results

*Inheritance:* [IntermediateResultUnit]({{ site.dcvb_java_api }}core/intermediate-results/intermediate-result-unit.html) -> ScaledBarcodeImageUnit

```java
public class ScaledBarcodeImageUnit extends IntermediateResultUnit
```

## Methods

| Method                            | Description |
|-----------------------------------|-------------|
| [`getImageData`](#getimagedata)           | Gets the scaled barcode image data.|
| [`setImageData`](#setimagedata)           | Sets the scaled image data.|

### getImageData

Gets the scaled barcode image data.

```java
public ImageData getImageData()
```

**Return value**

Returns the scaled image of the barcode.

**See Also**

[ImageData]({{ site.dcvb_java_api }}core/basic-classes/image-data.html)

### setImageData

Sets the scaled image data.

```java
public void setImageData(ImageData imgData) throws BarcodeReaderException
```

**Parameters**

`imgData` The scaled image data.

**Exceptions**

`BarcodeReaderException` If an error occurs while setting the image data.

**See Also**

[BarcodeReaderException]({{ site.dbr_java_api }}barcode-reader-exception.html)

[ImageData]({{ site.dcvb_java_api }}core/basic-classes/image-data.html)
