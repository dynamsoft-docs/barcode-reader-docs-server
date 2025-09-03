---
layout: default-layout
title: QRCodeDetails Class - Dynamsoft Barcode Reader SDK .NET Edition API Reference
description: This page shows the QRCodeDetails Class of Dynamsoft Barcode Reader SDK .NET Edition.
keywords: QRCodeDetails, class, api reference, .Net
needAutoGenerateSidebar: false
permalink: /programming/dotnet/api-reference/class/QRCodeDetails-v7.6.0.html
---


# QRCodeDetails
Stores the QRCode details.  


```csharp
public class QRCodeDetails
```  

## Attributes
  
| Attribute | Type |
|---------- | ---- |
| [`ModuleSize`](#modulesize) | *int* |
| [`Rows`](#rows) | *int* |
| [`Columns`](#columns) | *int* |
| [`ErrorCorrectionLevel`](#errorcorrectionlevel) | [`EnumQRCodeErrorCorrectionLevel`]({{ site.dbr_dotnet_enumerations }}other-enums.html#qrcodeerrorcorrectionlevel) |
| [`Version`](#version) | *int* |
| [`Model`](#model) | *int* |


### ModuleSize
The barcode module size (the minimum bar width in pixel).  

```csharp
int Dynamsoft.Barcode.QRCodeDetails.ModuleSize
```

### Rows
The row count of the barcode.  

```csharp
int Dynamsoft.Barcode.QRCodeDetails.Rows
```

### Columns
The column count of the barcode. 

```csharp
int Dynamsoft.Barcode.QRCodeDetails.Columns
```

### ErrorCorrectionLevel
The error correction level of the barcode.  

```csharp
EnumQRCodeErrorCorrectionLevel Dynamsoft.Barcode.QRCodeDetails.ErrorCorrectionLevel
```

### Version
The version of the QR Code.

```csharp
int Dynamsoft.Barcode.QRCodeDetails.Version
```

### Model
Number of the models.

```csharp
int Dynamsoft.Barcode.QRCodeDetails.Model
```
