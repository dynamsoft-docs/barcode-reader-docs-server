---
layout: default-layout
title: BarcodeReader Initialization and Destroy - Dynamsoft Barcode Reader SDK Java Edition API Reference
description: This page shows BarcodeReader Initialization and Destroy of Dynamsoft Barcode Reader SDK Java Edition API Reference.
keywords: BarcodeReader, destroy, initialization and destroy, api reference, java
needAutoGenerateSidebar: true
---

# Java API Reference - BarcodeReader Initialization and Destroy

  | Method               | Description |
  |----------------------|-------------|
  | [`BarcodeReader`](#barcodereader) | Initialization of `BarcodeReader` object.|
  | [`destroy`](#destroy) | Destroys an instance of `BarcodeReader` object.|

---





## BarcodeReader

Initialization of `BarcodeReader` object.

```java
com.dynamsoft.barcode.BarcodeReader.BarcodeReader() throws BarcodeReaderException
```

#### Exceptions
[`BarcodeReaderException`](../class/BarcodeReaderException.md)


#### Remarks
If you initialize DynamsoftBarcodeReader by this method without license, the decoding results maybe unreliable.


#### Code Snippet
```java
BarcodeReader reader = new BarcodeReader();
```



Initialization of `BarcodeReader` with license.

```java
com.dynamsoft.barcode.BarcodeReader.BarcodeReader(String license)throws BarcodeReaderException
```

#### Exceptions
[`BarcodeReaderException`](../class/BarcodeReaderException.md)


#### Code Snippet
```java
BarcodeReader reader = new BarcodeReader("t0260NwAAAHV***************");
```




## Destroy

```java
void com.dynamsoft.barcode.BarcodeReader.destroy()	
```


#### Code Snippet
```java
BarcodeReader reader = new BarcodeReader("t0260NwAAAHV***************");
reader.destroy();
```

