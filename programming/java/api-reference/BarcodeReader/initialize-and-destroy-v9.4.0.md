---
layout: default-layout
title: BarcodeReader Initialization and Destroy - Dynamsoft Barcode Reader SDK Java Edition API Reference
description: This page shows BarcodeReader Initialization and Destroy of Dynamsoft Barcode Reader SDK Java Edition API Reference.
keywords: BarcodeReader, destroy, initialization and destroy, api reference, java
needAutoGenerateSidebar: true
permalink: /programming/java/api-reference/BarcodeReader/initialize-and-destroy-v9.4.0.html
---

# Initialization and Destroy

  | Method               | Description |
  |----------------------|-------------|
  | [`BarcodeReader`](#barcodereader) | Initialization of `BarcodeReader` object.|
  | [`destroy`](#destroy) | Destroys an instance of `BarcodeReader` object.|






## BarcodeReader

Initialization of `BarcodeReader` object.

```java
com.dynamsoft.dbr.BarcodeReader.BarcodeReader() throws BarcodeReaderException
```

**Exception**  
[`BarcodeReaderException`](../class/BarcodeReaderException.md)




**Code Snippet**  
```java
BarcodeReader reader = new BarcodeReader();
```

**Remarks**  
If you initialize DynamsoftBarcodeReader by this method without license, the decoding results maybe unreliable.


Initialization of `BarcodeReader` with license.

```java
com.dynamsoft.dbr.BarcodeReader.BarcodeReader(String license)throws BarcodeReaderException
```

**Exception**  
[`BarcodeReaderException`](../class/BarcodeReaderException.md)


**Code Snippet**  
```java
BarcodeReader reader = new BarcodeReader("t0260NwAAAHV***************");
```




## Destroy

```java
void com.dynamsoft.dbr.BarcodeReader.destroy()	
```


**Code Snippet**  
```java
BarcodeReader reader = new BarcodeReader("t0260NwAAAHV***************");
reader.destroy();
```

