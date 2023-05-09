---
layout: default-layout
title: PDF417Details Class - Dynamsoft Barcode Reader SDK .NET Edition API Reference
description: This page shows the PDF417Details Class of Dynamsoft Barcode Reader SDK .NET Edition.
keywords: PDF417Details, class, api reference, .Net
needAutoGenerateSidebar: false
permalink: /programming/dotnet/api-reference/class/PDF417Details-v9.4.0.html
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
