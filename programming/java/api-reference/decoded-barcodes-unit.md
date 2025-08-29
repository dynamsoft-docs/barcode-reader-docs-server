---
layout: default-layout
title: DecodedBarcodesUnit Class - Dynamsoft Barcode Reader Java Edition API Reference
description: This page shows DecodedBarcodesUnit class definition of Dynamsoft Barcode Reader SDK Java Edition.
keywords: getCount, getDecodedBarcode, removeAllDecodedBarcodes, setDecodedBarcode, DecodedBarcodesUnit, api reference
---
# DecodedBarcodesUnit Class

The `DecodedBarcodesUnit` class represents a unit that contains decoded barcode elements. It inherits from the `IntermediateResultUnit` class.

## Definition

*Package:* com.dynamsoft.dbr.intermediate_results

*Inheritance:* [IntermediateResultUnit]({{ site.dcvb_java_api }}core/intermediate-results/intermediate-result-unit.html) -> DecodedBarcodesUnit

```java
public class DecodedBarcodesUnit extends IntermediateResultUnit
```

## Methods

| Method                            | Description |
|-----------------------------------|-------------|
| [`getCount`](#getcount)           | Gets the number of decoded barcodes in the unit.|
| [`getDecodedBarcode`](#getdecodedbarcode)           | Gets the `DecodedBarcodeElement` object at the specified index.|
| [`getDecodedBarcodes`](#getdecodedbarcodes)           | Gets all decoded barcode elements.|
| [`removeAllDecodedBarcodes`](#removealldecodedbarcodes)           | Removes all the decoded barcodes in the unit.|
| [`setDecodedBarcode`](#setdecodedbarcode)           | Sets the decoded barcode.|

### getCount

Gets the number of decoded barcodes in the unit.

```java
public int getCount()
```

**Return value**

Returns the number of decoded barcodes in the unit.

### getDecodedBarcode

Gets the `DecodedBarcodeElement` object at the specified index.

```java
public DecodedBarcodeElement getDecodedBarcode(int index) throws BarcodeReaderException
```

**Parameter**

`index` The index of the desired `DecodedBarcodeElement` object.

**Return value**

Returns the `DecodedBarcodeElement` object at the specified index.

**Exceptions**

`BarcodeReaderException` If an error occurs while retrieving the decoded barcode element.

**See Also**

[BarcodeReaderException]({{ site.dbr_java_api }}barcode-reader-exception.html)

[DecodedBarcodeElement]({{ site.dbr_java_api }}decoded-barcode-element.html)

### getDecodedBarcodes

Gets all decoded barcode elements.

```java
public DecodedBarcodeElement[] getDecodedBarcodes()
```

**Return value**

Returns an array of all `DecodedBarcodeElement` objects.

**See Also**

[DecodedBarcodeElement]({{ site.dbr_java_api }}decoded-barcode-element.html)

### removeAllDecodedBarcodes

Removes all the decoded barcodes in the unit.

```java
public void removeAllDecodedBarcodes()
```

### setDecodedBarcode

Sets the decoded barcode.

```java
public void setDecodedBarcode(DecodedBarcodeElement element) throws BarcodeReaderException
public void setDecodedBarcode(DecodedBarcodeElement element, double[] matrixToOriginalImage) throws BarcodeReaderException
```

**Parameters**

`element` The decoded barcode element.

`matrixToOriginalImage` The matrix to original image. The array length must be 9.

**Exceptions**

`BarcodeReaderException` If an error occurs while setting the decoded barcode element.

`IllegalArgumentException` If the `matrixToOriginalImage` array length is not 9.

**See Also**

[BarcodeReaderException]({{ site.dbr_java_api }}barcode-reader-exception.html)

[DecodedBarcodeElement]({{ site.dbr_java_api }}decoded-barcode-element.html)
