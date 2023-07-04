---
layout: default-layout
title: BarcodeReader Decode Methods - Dynamsoft Barcode Reader SDK Java Edition API Reference
description: This page shows BarcodeReader Decode methods of Dynamsoft Barcode Reader SDK Java Edition API Reference.
keywords: decodeFile, decodeFileInMemory, decodeBuffer, decodeBase64String, decodeBufferedImage, decode methods, BarcodeReader, api reference, java
needAutoGenerateSidebar: true
permalink: /programming/java/api-reference/BarcodeReader/decode-v7.6.0.html
---


# Java API Reference - BarcodeReader Decode Methods

  | Method               | Description |
  |----------------------|-------------|
  | [`decodeFile`](#decodefile) | Decode barcodes from a specified image file. |
  | [`decodeFileInMemory`](#decodefileinmemory) | Decode barcodes from an image file in memory. |
  | [`decodeBuffer`](#decodebuffer) | Decode barcodes from raw buffer. |
  | [`decodeBase64String`](#decodebase64string) | Decode barcodes from a base64 encoded string. |
  | [`decodeBufferedImage `](#decodebufferedimage) | Decodes barcode from a buffered imag (bitmap). |
  ---




## DecodeFile

Decode barcodes from a specified image file.

```java
TextResult[] com.dynamsoft.barcode.BarcodeReader.decodeFile(String fileFullPath, String templateName)	throws BarcodeReaderException	
```   
   
#### Parameters
`fileFullPath`	A string defining the file path.   
`templateName`  The template name.

#### Return value
All barcode text results decoded successfully.

#### Exceptions
[`BarcodeReaderException`](../class/BarcodeReaderException.md)

#### Code Snippet
```java
BarcodeReader reader = new BarcodeReader("t0260NwAAAHV***************");
TextResult[] result = reader.decodeFile("your file path", "");
reader.destroy();
```







## DecodeFileInMemory

Decode barcodes from an image file in memory.   

```java
TextResult[] com.dynamsoft.barcode.BarcodeReader.decodeFileInMemory(byte[] fileBytes, String templateName) throws BarcodeReaderException
```   
   
#### Parameters
`fileBytes` The image file bytes in memory.  
`templateName` The template name.

#### Return value
All barcode text results decoded successfully.

#### Exceptions
[`BarcodeReaderException`](../class/BarcodeReaderException.md)

#### Code Snippet
```java
BarcodeReader reader = new BarcodeReader("t0260NwAAAHV***************");
byte[] bufferBytes = null;
GetBufferFromFile("your file path", bufferBytes);
TextResult[] result = reader.decodeFileInMemory(bufferBytes, "");
reader.destroy();
```



```java
TextResult[] com.dynamsoft.barcode.BarcodeReader.decodeFileInMemory(InputStream fileStream, String templateName) throws BarcodeReaderException, IOException
```   
   
#### Parameters
`fileStream` The image file bytes in memory.  
`templateName` The template name.

#### Return value
All barcode text results decoded successfully.

#### Exceptions
[`BarcodeReaderException`](../class/BarcodeReaderException.md), IOException

#### Code Snippet
```java
BarcodeReader reader = new BarcodeReader("t0260NwAAAHV***************");
FileInputStream fis = new FileInputStream("your file path");
TextResult[] result = reader.decodeFileInMemory(fis, "");
reader.destroy();
```







## DecodeBuffer

Decode barcodes from the memory buffer containing image pixels in defined format.

```java
TextResult[] com.dynamsoft.barcode.BarcodeReader.decodeBuffer(byte[] buffer, int width, int height, int stride, int enumImagePixelFormat, String templateName)	throws BarcodeReaderException	
```   
   
#### Parameters
`buffer` The array of bytes which contain the image data.  
`width` The width of the image in pixels.  
`height` The height of the image in pixels.  
`stride` The stride (or scan width) of the image.  
`enumImagePixelFormat` The image pixel format used in the image byte array.  
`templateName` The template name.

#### Return value
All barcode text results decoded successfully.  

#### Exceptions
[`BarcodeReaderException`](../class/BarcodeReaderException.md)

#### Code Snippet
```java
BarcodeReader reader = new BarcodeReader("t0260NwAAAHV***************");
byte[] bufferBytes;
int iWidth = 0;
int iHeight = 0;
int iStride = 0;
int format;
GetBufferFromFile("your file path", bufferBytes, iWidth, iHeight, iStride, format);
TextResult[] result = reader.decodeBuffer(bufferBytes, iWidth,  iHeight, iStride, format, "");
reader.destroy();
```







## DecodeBase64String

Decode barcode from an image file encoded as a base64 string.

```java
TextResult[] com.dynamsoft.barcode.BarcodeReader.decodeBase64String(String base64, String templateName)	throws BarcodeReaderException
```   
   
#### Parameters
`base64`	A base64 encoded string that represents an image.   
`templateName` The template name.

#### Return value
All barcode text results decoded successfully.

#### Exceptions
[`BarcodeReaderException`](../class/BarcodeReaderException.md)

#### Code Snippet
```java
BarcodeReader reader = new BarcodeReader("t0260NwAAAHV***************");
TextResult[] result = reader.decodeBase64String("file in base64 string", "");
reader.destroy();
```







## DecodeBufferedImage

Decodes barcode from a buffered imag (bitmap).

```java
TextResult[] com.dynamsoft.barcode.BarcodeReader.decodeBufferedImage(BufferedImage image, String templateName)	throws IOException, BarcodeReaderException
```   
   
#### Parameters
`image` The image to be decoded.  
`templateName` The template name.

#### Return value
All barcode text results decoded successfully.  

#### Exceptions
[`BarcodeReaderException`](../class/BarcodeReaderException.md), IOException

#### Code Snippet
```java
BarcodeReader reader = new BarcodeReader("t0260NwAAAHV***************");
BufferedImage input = ImageIO.read("your file path");
TextResult[] result = reader.decodeBufferedImage(bitmap, "");
reader.destroy();
```



