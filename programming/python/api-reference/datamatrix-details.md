---
layout: default-layout
title: DataMatrixDetails Class - Dynamsoft Barcode Reader Module Python Edition API Reference
description: Definition of DataMatrixDetails class in Dynamsoft Barcode Reader Module Python Edition.
keywords: rows, columns, data_region_rows, data_region_columns, data_region_number, DataMatrixDetails, api reference
---
# DataMatrixDetails

The `DataMatrixDetails` class represents the details of a DataMatrix barcode. It is derived from the `BarcodeDetails` class and contains various attributes related to the DataMatrix barcode. 

## Definition

*Module:* dynamsoft_barcode_reader

*Inheritance:* [BarcodeDetails]({{ site.dbr_python_api }}barcode-details.html) -> DataMatrixDetails

```python
class DataMatrixDetails(BarcodeDetails)
```

## Properties

| Property  | Type |
|---------- | ---- |
| [`rows`](#rows) | *int* |
| [`columns`](#columns) | *int* |
| [`data_region_rows`](#data_region_rows) | *int* |
| [`data_region_columns`](#data_region_columns) | *int* |
| [`data_region_number`](#data_region_number) | *int* |

### rows

The row count of the DataMatrix barcode.

### columns

The column count of the DataMatrix barcode.

### data_region_rows

The data region row count of the DataMatrix barcode.

### data_region_columns

The data region column count of the DataMatrix barcode.

### data_region_number

The data region count.
