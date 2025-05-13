---
layout: default-layout
title: PDF417Details Class - Dynamsoft Barcode Reader Module .NET Edition API Reference
description: Definition of PDF417Details class in Dynamsoft Barcode Reader Module .NET Edition.
keywords: rows, columns, errorCorrectionLevel, PDF417Details, api reference
---
# PDF417Details

The `PDF417Details` class represents a barcode in PDF417 format. It inherits from the `BarcodeDetails` class and contains information about the row count, column count, and error correction level of the barcode.

## Definition

*Namespace:* Dynamsoft.DBR


*Inheritance:* [BarcodeDetails]({{ site.dbr_dotnet_api }}barcode-details.html) -> PDF417Details

```csharp
public class PDF417Details : BarcodeDetails
```

## Attributes

| Attribute | Type |
|---------- | ---- |
| [`rows`](#rows) | *int* |
| [`columns`](#columns) | *int* |
| [`errorCorrectionLevel`](#errorcorrectionlevel) | *int* |
| [`hasLeftRowIndicator`](#hasleftrowindicator) | *int* |
| [`hasRightRowIndicator`](#hasrightrowindicator) | *int* |
| [`codewords`](#codewords) | *uint[]* |

### rows

The number of rows in the PDF417 barcode.

```csharp
int rows;
```

### columns

The number of columns in the PDF417 barcode.

```csharp
int columns;
```

### errorCorrectionLevel

Specifies the error correction level of PDF417 code.

```csharp
int errorCorrectionLevel;
```

### hasLeftRowIndicator

Specifies whether the left row indicator of the PDF417 code exists.

```csharp
int hasLeftRowIndicator;
```

### hasRightRowIndicator

Specifies whether the right row indicator of the PDF417 code exists.

```csharp
int hasRightRowIndicator;
```

### codewords

Specifies  the codewords of the PDF417 barcode.

```csharp
uint[] codewords;
```
