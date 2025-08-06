---
layout: default-layout
title: AztecDetails Class - Dynamsoft Barcode Reader Java Edition API Reference
description: Definition of AztecDetails class in Dynamsoft Barcode Reader Java Edition.
keywords: rows, columns, layerNumber, AztecDetails, api reference
---

# AztecDetails

The `AztecDetails` class represents a barcode in Aztec format. It inherits from the `BarcodeDetails` class and contains information about the row count, column count, and layer number of the barcode.

## Definition

*Package:* com.dynamsoft.dbr

*Inheritance:* [BarcodeDetails]({{ site.dbr_java_api }}barcode-details.html) -> AztecDetails

```java
public class AztecDetails extends BarcodeDetails
```

## Attributes

| Attribute | Type | Description |
|---------- | ---- | ----------- |
| [`rows`](#rows) | *int* | The number of rows in the Aztec barcode. |
| [`columns`](#columns) | *int* | The number of columns in the Aztec barcode. |
| [`layerNumber`](#layernumber) | *int* | The layer number of the Aztec barcode. |

## Constructors

| Constructor | Description |
|------------ | ----------- |
| [`AztecDetails()`](#aztecdetails) | Default constructor. |
| [`AztecDetails(int rows, int columns, int layerNumber)`](#aztecdetailsint-rows-int-columns-int-layernumber) | Constructor with parameters. |

## Attribute Details

### rows

The number of rows in the Aztec barcode.

```java
public int rows
```

### columns

The number of columns in the Aztec barcode.

```java
public int columns
```

### layerNumber

Specifies the layer number of the Aztec barcode. A negative number (-1, -2, -3, -4) specifies a compact Aztec code, while a positive number (1, 2, .. 32) specifies a normal (full-range) Aztec code.

```java
public int layerNumber
```

## Constructor Details

### AztecDetails()

Default constructor. Initializes a new instance of the AztecDetails class with default values (-1, -1, -1).

```java
public AztecDetails()
```

### AztecDetails(int rows, int columns, int layerNumber)

Constructor with parameters. Initializes a new instance of the AztecDetails class with specified values.

```java
public AztecDetails(int rows, int columns, int layerNumber)
```

**Parameters**

`rows`: The number of rows in the Aztec barcode.

`columns`: The number of columns in the Aztec barcode.

`layerNumber`: The layer number of the Aztec barcode.
