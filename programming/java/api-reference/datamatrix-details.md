---
layout: default-layout
title: DataMatrixDetails Class - Dynamsoft Barcode Reader Java Edition API Reference
description: Definition of DataMatrixDetails class in Dynamsoft Barcode Reader Java Edition.
keywords: rows, columns, dataRegionRows, dataRegionColumns, dataRegionNumber, DataMatrixDetails, api reference
---
# DataMatrixDetails

The `DataMatrixDetails` class represents the details of a DataMatrix barcode. It is derived from the `BarcodeDetails` class and contains various attributes related to the DataMatrix barcode. 

## Definition

*Package:* com.dynamsoft.dbr

*Inheritance:* [BarcodeDetails]({{ site.dbr_java_api }}barcode-details.html) -> DataMatrixDetails

```java
public class DataMatrixDetails extends BarcodeDetails
```

## Attributes

| Attribute | Type | Description |
|---------- | ---- | ----------- |
| [`rows`](#rows) | *int* | The row count of the DataMatrix barcode. |
| [`columns`](#columns) | *int* | The column count of the DataMatrix barcode. |
| [`dataRegionRows`](#dataregionrows) | *int* | The data region row count of the DataMatrix barcode. |
| [`dataRegionColumns`](#dataregioncolumns) | *int* | The data region column count of the DataMatrix barcode. |
| [`dataRegionNumber`](#dataregionnumber) | *int* | The data region count. |

## Constructors

| Constructor | Description |
|------------ | ----------- |
| [`DataMatrixDetails()`](#datamatrixdetails) | Default constructor. |
| [`DataMatrixDetails(int rows, int columns, int dataRegionRows, int dataRegionColumns, int dataRegionNumber)`](#datamatrixdetailsint-rows-int-columns-int-dataregionrows-int-dataregioncolumns-int-dataregionnumber) | Constructor with parameters. |

## Attribute Details

### rows

The row count of the DataMatrix barcode.

```java
public int rows
```

### columns

The column count of the DataMatrix barcode.

```java
public int columns
```

### dataRegionRows

The data region row count of the DataMatrix barcode.

```java
public int dataRegionRows
```

### dataRegionColumns

The data region column count of the DataMatrix barcode.

```java
public int dataRegionColumns
```

### dataRegionNumber

The data region count.

```java
public int dataRegionNumber
```

## Constructor Details

### DataMatrixDetails()

Default constructor. Initializes a new instance of the DataMatrixDetails class with default values (-1, -1, -1, -1, -1).

```java
public DataMatrixDetails()
```

### DataMatrixDetails(int rows, int columns, int dataRegionRows, int dataRegionColumns, int dataRegionNumber)

Constructor with parameters. Initializes a new instance of the DataMatrixDetails class with specified values.

```java
public DataMatrixDetails(int rows, int columns, int dataRegionRows, int dataRegionColumns, int dataRegionNumber)
```

**Parameters**

`rows`: The row count of the DataMatrix barcode.

`columns`: The column count of the DataMatrix barcode.

`dataRegionRows`: The data region row count of the DataMatrix barcode.

`dataRegionColumns`: The data region column count of the DataMatrix barcode.

`dataRegionNumber`: The data region count.
