---
layout: default-layout
title: BarcodeReader Initialization and Destroy - Dynamsoft Barcode Reader SDK Java Edition API Reference
description: This page shows BarcodeReader Initialization and Destroy of Dynamsoft Barcode Reader SDK Java Edition API Reference.
keywords: BarcodeReader, destroy, initialization and destroy, api reference, java
needAutoGenerateSidebar: true
permalink: /programming/java/api-reference/BarcodeReader/initialize-and-destroy.html
---

# Initialization and Destroy

  | Method               | Description |
  |----------------------|-------------|
  | [`BarcodeReader`](#barcodereader) | Initialization of `BarcodeReader` object.|
  | [`destroy`](#destroy) | Destroys an instance of `BarcodeReader` object.|
  | [`getInstance`](#getinstance) | Creates an instance of Dynamsoft Barcode Reader. |
  | [`recycle`](#recycle) | Destroys an instance of Dynamsoft Barcode Reader. |






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

Creates an instance of Dynamsoft Barcode Reader.

```java
static BarcodeReader com.dynamsoft.dbr.BarcodeReader.getInstance()
```

**Return Value**  
Returns an instance of Dynamsoft Barcode Reader. If failed, returns `null`.

**Code Snippet**  

```java
//Make sure initLicense have been called somewhere before getInstance
BarcodeReader reader = BarcodeReader.getInstance();
if(reader != null)
{
    // Add your code here to call decoding method, process barcode results and so on
    // ...
    // Recycle the instance
    reader.recycle();
}
```

## Recycle

Destroys an instance of Dynamsoft Barcode Reader.

```java
void com.dynamsoft.dbr.BarcodeReader.recycle()
```

**Code Snippet**  

```java
//Make sure initLicense have been called somewhere before getInstance
BarcodeReader reader = BarcodeReader.getInstance();
if(reader != null)
{
    // Add your code here to call decoding method, process barcode results and so on
    // ...
    // Recycle the instance
    reader.recycle();
}
```
