---
layout: default-layout
title: AztecDetails Class - Dynamsoft Barcode Reader Module .NET Edition API Reference
description: Definition of AztecDetails class in Dynamsoft Barcode Reader Module .NET Edition.
keywords: rows, columns, layerNumber, AztecDetails, api reference
---

# AztecDetails

The `AztecDetails` class represents a barcode in Aztec format. It inherits from the `BarcodeDetails` class and contains information about the row count, column count, and layer number of the barcode.

## Definition

*Namespace:* Dynamsoft.DBR


*Inheritance:* [BarcodeDetails]({{ site.dbr_dotnet_api }}barcode-details.html) -> AztecDetails

```csharp
public class AztecDetails : BarcodeDetails
```

## Attributes

| Attribute | Type |
|---------- | ---- |
| [`rows`](#rows) | *int* |
| [`columns`](#columns) | *int* |
| [`layerNumber`](#layernumber) | *int* |

### rows

The number of rows in the Aztec barcode.

```csharp
int rows;
```

### columns

The number of columns in the Aztec barcode.

```csharp
int columns;
```

### layerNumber

Specifies the layer number of the Aztec barcode. A negative number (-1, -2, -3, -4) specifies a compact Aztec code. A positive number (1, 2, .. 32) specifies a normal (full-range) Aztec code.

```csharp
int layerNumber;
```
