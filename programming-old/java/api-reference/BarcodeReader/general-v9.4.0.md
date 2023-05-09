---
layout: default-layout
title: BarcodeReader General Methods - Dynamsoft Barcode Reader SDK Java Edition API Reference
description: This page shows BarcodeReader general methods of Dynamsoft Barcode Reader SDK Java Edition API Reference.
keywords: getVersion, general methods, BarcodeReader, api reference, java
needAutoGenerateSidebar: true
permalink: /programming/java/api-reference/BarcodeReader/general-v9.4.0.html
---

# General Methods

  | Method               | Description |
  |----------------------|-------------|
  | [`getVersion`](#getversion) | Get version information of SDK.|







## getVersion

Get version information of SDK.

```java
String com.dynamsoft.dbr.BarcodeReader.getVersion()	
```

**Return Value**  
The version information string.

**Code Snippet**  
```java
BarcodeReader.initLicense("YOUR-LICENSE-KEY");
BarcodeReader reader = new BarcodeReader();
String versionInfo = reader.getVersion();
reader.destroy();
```
