---
layout: default-layout
title: Dynamsoft Barcode Reader Java API Reference - BarcodeReader General Methods
description: This page shows BarcodeReader general methods of Dynamsoft Barcode Reader for Java SDK API Reference.
keywords: getVersion, general methods, BarcodeReader, api reference, java
needAutoGenerateSidebar: true
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
