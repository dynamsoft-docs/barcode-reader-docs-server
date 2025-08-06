---
layout: default-layout
title: LocalizedBarcodesUnit Class - Dynamsoft Barcode Reader Java Edition API Reference
description: This page shows LocalizedBarcodesUnit class definition of Dynamsoft Barcode Reader SDK Java Edition.
keywords: getCount, getLocalizedBarcode, addLocalizedBarcode, removeAllLocalizedBarcodes, removeLocalizedBarcode, setLocalizedBarcode, LocalizedBarcodesUnit, api reference
---
# LocalizedBarcodesUnit Class

The `LocalizedBarcodesUnit` class represents a unit that contains localized barcodes unit. It inherits from the `IntermediateResultUnit` class.

## Definition

*Package:* com.dynamsoft.dbr.intermediate_results

*Inheritance:* [IntermediateResultUnit]({{ site.dcvb_java_api }}core/intermediate-results/intermediate-result-unit.html) -> LocalizedBarcodesUnit

```java
public class LocalizedBarcodesUnit extends IntermediateResultUnit
```

## Methods

| Method                            | Description |
|-----------------------------------|-------------|
| [`addLocalizedBarcode`](#addlocalizedbarcode)           | Adds a localized barcode.|
| [`getCount`](#getcount)           | Gets the number of localized barcodes in the unit.|
| [`getLocalizedBarcode`](#getlocalizedbarcode)           | Gets the localized barcode at the specified index.|
| [`getLocalizedBarcodes`](#getlocalizedbarcodes)           | Gets all localized barcodes.|
| [`removeAllLocalizedBarcodes`](#removealllocalizedbarcodes)           | Removes all localized barcodes.|
| [`removeLocalizedBarcode`](#removelocalizedbarcode)           | Removes the localized barcode at the specified index.|
| [`setLocalizedBarcode`](#setlocalizedbarcode)           | Sets the localized barcode at the specified index.|

### addLocalizedBarcode

Adds a localized barcode to the unit.

```java
public void addLocalizedBarcode(LocalizedBarcodeElement localizedBarcode) throws BarcodeReaderException
public void addLocalizedBarcode(LocalizedBarcodeElement localizedBarcode, double[] matrixToOriginalImage) throws BarcodeReaderException
```

**Parameters**

`localizedBarcode` The localized barcode element to add.

`matrixToOriginalImage` The matrix to original image. The array length must be 9.

**Exceptions**

`BarcodeReaderException` If an error occurs while adding the localized barcode.

`IllegalArgumentException` If the `matrixToOriginalImage` array length is not 9.

**See Also**

[LocalizedBarcodeElement]({{ site.dbr_java_api }}localized-barcode-element.html)

### getCount

Gets the number of localized barcodes in the unit.

```java
public int getCount()
```

**Return value**

Returns the number of localized barcodes in the unit.

### getLocalizedBarcode

Gets the localized barcode at the specified index.

```java
public LocalizedBarcodeElement getLocalizedBarcode(int index) throws BarcodeReaderException
```

**Parameters**

`index` The index of the localized barcode to retrieve.

**Return value**

Returns a `LocalizedBarcodeElement` object at the specified index.

**Exceptions**

`BarcodeReaderException` If an error occurs while retrieving the localized barcode.

**See Also**

[LocalizedBarcodeElement]({{ site.dbr_java_api }}localized-barcode-element.html)

### getLocalizedBarcodes

Gets all localized barcodes.

```java
public LocalizedBarcodeElement[] getLocalizedBarcodes()
```

**Return value**

Returns an array of all `LocalizedBarcodeElement` objects.

**See Also**

[LocalizedBarcodeElement]({{ site.dbr_java_api }}localized-barcode-element.html)

### removeAllLocalizedBarcodes

Removes all localized barcodes from the unit.

```java
public void removeAllLocalizedBarcodes()
```

### removeLocalizedBarcode

Removes the localized barcode at the specified index.

```java
public void removeLocalizedBarcode(int index) throws BarcodeReaderException
```

**Parameters**

`index` The index of the localized barcode to remove.

**Exceptions**

`BarcodeReaderException` If an error occurs while removing the localized barcode.

### setLocalizedBarcode

Sets the localized barcode at the specified index.

```java
public void setLocalizedBarcode(int index, LocalizedBarcodeElement localizedBarcode) throws BarcodeReaderException
public void setLocalizedBarcode(int index, LocalizedBarcodeElement localizedBarcode, double[] matrixToOriginalImage) throws BarcodeReaderException
```

**Parameters**

`index` The index at which to set the localized barcode.

`localizedBarcode` The localized barcode element to set.

`matrixToOriginalImage` The matrix to original image. The array length must be 9.

**Exceptions**

`BarcodeReaderException` If an error occurs while setting the localized barcode.

`IllegalArgumentException` If the `matrixToOriginalImage` array length is not 9.

**See Also**

[LocalizedBarcodeElement]({{ site.dbr_java_api }}localized-barcode-element.html)

