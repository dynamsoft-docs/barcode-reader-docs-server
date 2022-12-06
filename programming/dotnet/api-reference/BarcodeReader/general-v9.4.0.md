---
layout: default-layout
title: BarcodeReader General Methods - Dynamsoft Barcode Reader SDK .NET Edition API Reference
description: This page shows BarcodeReader general methods of Dynamsoft Barcode Reader SDK .NET Edition.
keywords: GetVersion, general methods, BarcodeReader, api reference, .Net
needAutoGenerateSidebar: true
---

# General Methods

  | Method               | Description |
  |----------------------|-------------|
  | [`GetVersion`](#getversion) | Get version information of SDK.|



## GetVersion

Get version information of SDK.

```csharp
string Dynamsoft.DBR.BarcodeReader.GetVersion()
```

**Return Value**  
The version info string. 

**Code Snippet**  
```csharp
BarcodeReader reader = new BarcodeReader();
string version = reader.GetVersion();
```
