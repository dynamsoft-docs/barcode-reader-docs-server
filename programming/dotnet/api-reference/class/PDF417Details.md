---
layout: default-layout
title: Dynamsoft Barcode Reader .NET API Reference - PDF417Details Class
description: This page shows the PDF417Details Class of Dynamsoft Barcode Reader for .NET SDK.
keywords: PDF417Details, class, api reference, .Net
needAutoGenerateSidebar: false
---


# PDF417Details
Stores the PDF417 details.

```csharp
public class PDF417Details
```  

## Attributes
  
| Attribute | Type |
|---------- | ---- |
| [`ModuleSize`](#modulesize) | *int* |
| [`Rows`](#rows) | *int* |
| [`Columns`](#columns) | *int* |
| [`ErrorCorrectionLevel`](#errorcorrectionlevel) | *int* |
| [`HasLeftRowIndicator`](#hasleftrowindicator) | *int* |
| [`HasRightRowIndicator`](#hasrightrowindicator) | *int* |

### ModuleSize

The barcode module size (the minimum bar width in pixel).

```csharp
int Dynamsoft.PDF417Details.ModuleSize
```

### Rows

The row count of the barcode.

```csharp
int Dynamsoft.PDF417Details.Rows
```

### Columns

The column count of codewords between the left and right row indicators, where the actual data and the ECC is encoded.

```csharp
int Dynamsoft.PDF417Details.Columns
```

### ErrorCorrectionLevel

The error correction level of the barcode.

```csharp
int Dynamsoft.PDF417Details.ErrorCorrectionLevel
```

### HasLeftRowIndicator

Whether the left row indicator of the PDF417 code exists.

- 0: left row indicator does not exist
- 1: left row indicator exists

```csharp
int Dynamsoft.PDF417Details.HasLeftRowIndicator
```

### HasRightRowIndicator

Whether the right row indicator of the PDF417 code exists.

- 0: right row indicator does not exist
- 1: right row indicator exists

```csharp
int Dynamsoft.PDF417Details.HasRightRowIndicator
```
