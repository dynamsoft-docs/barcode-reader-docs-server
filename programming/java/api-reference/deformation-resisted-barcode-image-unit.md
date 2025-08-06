---
layout: default-layout
title: DeformationResistedBarcodeImageUnit Class - Dynamsoft Barcode Reader Java Edition API Reference
description: This page shows DeformationResistedBarcodeImageUnit class definition of Dynamsoft Barcode Reader SDK Java Edition.
keywords: getDeformationResistedBarcode, setDeformationResistedBarcode, DeformationResistedBarcodeImageUnit, api reference
---
# DeformationResistedBarcodeImageUnit Class

The `DeformationResistedBarcodeImageUnit` class represents a unit that contains deformation resisted barcode image data. It inherits from the `IntermediateResultUnit` class.

## Definition

*Package:* com.dynamsoft.dbr.intermediate_results

*Inheritance:* [IntermediateResultUnit]({{ site.dcvb_java_api }}core/intermediate-results/intermediate-result-unit.html) -> DeformationResistedBarcodeImageUnit

```java
public class DeformationResistedBarcodeImageUnit extends IntermediateResultUnit
```

## Methods

| Method                            | Description |
|-----------------------------------|-------------|
| [`getDeformationResistedBarcode`](#getdeformationresistedbarcode) | Gets the deformation resisted barcode object.|
| [`setDeformationResistedBarcode`](#setdeformationresistedbarcode) | Sets the deformation resisted barcode object.|

### getDeformationResistedBarcode

Gets the deformation resisted barcode object.

```java
public DeformationResistedBarcode getDeformationResistedBarcode()
```

**Return value**

Returns an instance of `DeformationResistedBarcode`.

**See Also**

[DeformationResistedBarcode]({{ site.dbr_java_api }}deformation-resisted-barcode.html)

### setDeformationResistedBarcode

Sets the deformation resisted barcode object.

```java
public void setDeformationResistedBarcode(DeformationResistedBarcode barcode) throws BarcodeReaderException
public void setDeformationResistedBarcode(DeformationResistedBarcode barcode, double[] matrixToOriginalImage) throws BarcodeReaderException
```

**Parameters**

`barcode` The deformation resisted barcode object.

`matrixToOriginalImage` The matrix to original image. The array length must be 9.

**Exceptions**

`BarcodeReaderException` If an error occurs while setting the deformation resisted barcode.

`IllegalArgumentException` If the `matrixToOriginalImage` array length is not 9.

**See Also**

[DeformationResistedBarcode]({{ site.dbr_java_api }}deformation-resisted-barcode.html)
