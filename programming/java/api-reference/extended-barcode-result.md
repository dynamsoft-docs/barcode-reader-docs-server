---
layout: default-layout
title: ExtendedBarcodeResult Class - Dynamsoft Barcode Reader Java Edition API Reference
description: This page shows ExtendedBarcodeResult class definition of Dynamsoft Barcode Reader SDK Java Edition.
keywords: getDeformation, getClarity, getSamplingImage, getExtendedBarcodeResultType, ExtendedBarcodeResult, api reference
---
# ExtendedBarcodeResult Class

The `ExtendedBarcodeResult` class represents an extended barcode result in a decoded barcode element. It contains information such as the type of extended barcode, deformation, clarity, and a sampling image of the barcode.

## Definition

*Package:* com.dynamsoft.dbr.intermediate_results

*Inheritance:* [DecodedBarcodeElement]({{ site.dbr_java_api }}decoded-barcode-element.html) -> ExtendedBarcodeResult

```java
public class ExtendedBarcodeResult extends DecodedBarcodeElement
```

## Methods

| Method | Description |
|--------|-------------|
| [`getExtendedBarcodeResultType`](#getextendedbarcoderesulttype) | Gets the type of extended barcode result. |
| [`getDeformation`](#getdeformation) | Gets the deformation of the barcode. |
| [`getClarity`](#getclarity) | Gets the clarity of the barcode. |
| [`getSamplingImage`](#getsamplingimage) | Gets the sampling image of the barcode. |

### getExtendedBarcodeResultType

Gets the type of extended barcode result.

```java
public @EnumExtendedBarcodeResultType int getExtendedBarcodeResultType()
```

**Return value**

Returns the type of the extended barcode result. This is one of the values of the `EnumExtendedBarcodeResultType` enumeration.

**See Also**

[EnumExtendedBarcodeResultType]({{ site.dbr_java_api }}enum-extended-barcode-result-type.html)

### getDeformation

Gets the deformation of the barcode.

```java
public int getDeformation()
```

**Return value**

Returns the deformation of the barcode.

### getClarity

Gets the clarity of the barcode.

```java
public int getClarity()
```

**Return value**

Returns the clarity of the barcode.

### getSamplingImage

Gets the sampling image of the barcode.

```java
public ImageData getSamplingImage()
```

**Return value**

Returns an `ImageData` object representing the sampling image of the barcode.

**See Also**

[ImageData]({{ site.dcvb_java_api }}core/basic-classes/image-data.html)
