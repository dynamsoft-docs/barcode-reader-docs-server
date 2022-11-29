---
layout: default-layout
title: Dynamsoft Barcode Reader Java API Reference - BarcodeReader Initialization and Destroy
description: This page shows BarcodeReader Initialization and Destroy of Dynamsoft Barcode Reader for Java SDK API Reference.
keywords: BarcodeReader, destroy, initialization and destroy, api reference, java
needAutoGenerateSidebar: true
---

# Initialization and Destroy

  | Method               | Description |
  |----------------------|-------------|
  | [`BarcodeReader`](#barcodereader) | Initialization of `BarcodeReader` object.|
  | [`destroy`](#destroy) | Destroys an instance of `BarcodeReader` object.|
  | [`getInstance`](#getinstance) | Gets an idle Dynamsoft Barcode Reader instance running on concurrent instance mode. |
  | [`recycle`](#recycle) | Recycles a Dynamsoft Barcode Reader instance running on concurrent instance mode. |






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

Destroys an instance of `BarcodeReader` object.

```java
void com.dynamsoft.dbr.BarcodeReader.destroy()	
```


**Code Snippet**  
```java
BarcodeReader reader = new BarcodeReader("t0260NwAAAHV***************");
reader.destroy();
```

## GetInstance

Gets an idle Dynamsoft Barcode Reader instance running on concurrent instance mode.

```java
static BarcodeReader com.dynamsoft.dbr.BarcodeReader.getInstance()
```

**Return Value**  
Returns an idle Dynamsoft Barcode Reader instance running on concurrent instance mode. If failed, returns `NULL`.

**Code Snippet**  

```java
BarcodeReader.initLicense("YOUR-LICENSE-KEY");
BarcodeReader barcodeReader = BarcodeReader.getInstance();
// Add your code here to call decoding method, process barcode results and so on
// ...
// Recycle the barcodeReader instance to make it idle for other concurrent tasks
barcodeReader.recycle();
```

## Recycle

Recycles a Dynamsoft Barcode Reader instance running on concurrent instance mode.

```java
void com.dynamsoft.dbr.BarcodeReader.recycle()
```

**Code Snippet**  

```java
BarcodeReader.initLicense("YOUR-LICENSE-KEY");
BarcodeReader barcodeReader = BarcodeReader.getInstance();
// Add your code here to call decoding method, process barcode results and so on
// ...
// Recycle the barcodeReader instance to make it idle for other concurrent tasks
barcodeReader.recycle();
```
