---
layout: default-layout
title: BarcodeReader General Methods - Dynamsoft Barcode Reader SDK .NET Edition API Reference
description: This page shows BarcodeReader general methods of Dynamsoft Barcode Reader SDK .NET Edition.
keywords: GetVersion, general methods, BarcodeReader, api reference, .Net
needAutoGenerateSidebar: true
permalink: /programming/dotnet/api-reference/BarcodeReader/general-v7.6.0.html
---

# .Net API Reference - BarcodeReader General Methods

  | Method               | Description |
  |----------------------|-------------|
  | [`GetVersion`](#getversion) | Get version information of SDK.|

  ---


## GetVersion

Get version information of SDK.

```csharp
string Dynamsoft.Barcode.BarcodeReader.GetVersion()
```

#### Return value
The version info string. 

#### Code Snippet
```csharp
BarcodeReader reader = new BarcodeReader();
string version = reader.GetVersion();
```
