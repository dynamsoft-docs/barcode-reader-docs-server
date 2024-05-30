---
layout: default-layout
title: DataMatrixDetails Class - Dynamsoft Barcode Reader Module .NET Edition API Reference
description: Definition of DataMatrixDetails class in Dynamsoft Barcode Reader Module .NET Edition.
keywords: rows, columns, dataRegionRows, dataRegionColumns, dataRegionNumber, DataMatrixDetails, api reference
---
# DataMatrixDetails

The `DataMatrixDetails` class represents the details of a DataMatrix barcode. It is derived from the `BarcodeDetails` class and contains various attributes related to the DataMatrix barcode. 

## Definition

*Namespace:* Dynamsoft.DBR

*Assembly:* Dynamsoft.BarcodeReader.dll

*Inheritance:* [BarcodeDetails]({{ site.dbr_dotnet_api }}barcode-details.html) -> DataMatrixDetails

```csharp
public class DataMatrixDetails : BarcodeDetails
```

## Attributes

| Attribute | Type |
|---------- | ---- |
| [`rows`](#rows) | *int* |
| [`columns`](#columns) | *int* |
| [`dataRegionRows`](#dataregionrows) | *int* |
| [`dataRegionColumns`](#dataregioncolumns) | *int* |
| [`dataRegionNumber`](#dataregionnumber) | *int* |

### rows

The row count of the DataMatrix barcode.

```csharp
int rows;
```

### columns

The column count of the DataMatrix barcode.

```csharp
int columns;
```

### dataRegionRows

The data region row count of the DataMatrix barcode.

```csharp
int dataRegionRows;
```

### dataRegionColumns

The data region column count of the DataMatrix barcode.

```csharp
int dataRegionColumns;
```

### dataRegionNumber

The data region count.

```csharp
int dataRegionNumber;
```
