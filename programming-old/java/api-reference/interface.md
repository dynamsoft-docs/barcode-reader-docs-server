---
layout: default-layout
title: Interface - Dynamsoft Barcode Reader SDK Java Edition API Reference
description: This page shows the interfaces of Dynamsoft Barcode Reader SDK Java Edition API Reference.
keywords: ErrorCallback, IntermediateResultCallback, TextResultCallback, interface, api reference, java
needAutoGenerateSidebar: false
permalink: /programming/java/api-reference/interface.html
---


# Interfaces

  | Interface | Description |
  |----------|-------------|
  | [`ErrorCallback`](#errorcallback) | Represents the method that will handle the error code returned by the SDK. |
  | [`IntermediateResultCallback`](#intermediateresultcallback) | Represents the method that will handle the intermediate result array returned by the SDK. |
  | [`TextResultCallback`](#textresultcallback) | Represents the method that will handle the text result array returned by the SDK. |

## ErrorCallback

Represents the method that will handle the error code returned by the SDK.

```java
void com.dynamsoft.dbr.ErrorCallback.errorCallback(int frameId, int errorCode, Object userData)	
```   
   
**Parameters**  
`frameId` 	The ID of the frame.    
`errorCode` Error Code generated when decoding the frame.
`userData` Arguments passed to your function.







## IntermediateResultCallback
Represents the method that will handle the intermediate result array returned by the SDK.

```java
void com.dynamsoft.dbr.IntermediateResultCallback.intermediateResultCallback(int frameId, IntermediateResult[] results, Object userData)	
```   
   
**Parameters**  
`frameId` 	The ID of the frame.  
`results` The intermediate results of the frame.   
`userData` Arguments passed to your function.   

**See Also**  
[IntermediateResult](class/IntermediateResult.md)







## TextResultCallback

Interface to handle callbacks when the text result array returned by the SDK.

```java
public interface TextResultCallback {
    void textResultCallback(int id, TextResult[] results, Object userData);
    void uniqueBarcodeCallback(int id, TextResult[] results, Object userData);
}
```

### textResultCallback

The method will be triggered when the library finishes decoding a frame.

```java
void textResultCallback(int id, TextResult[] results, Object userData);
```

**Parameters**  
`id` The ID of the frame.  
`results` Recognized barcode results of the frame.
`userData` Arguments passed to your function.

**See Also**  
[TextResult](class/TextResult.md)

### uniqueBarcodeCallback

The method will be triggered when the library finishes decoding a frame and finds unique barcodes.

```java
void uniqueBarcodeCallback(int id, TextResult[] results, Object userData);
```

**Parameters**  
`id` The ID of the frame.  
`results` Recognized unique barcode results of the frame.
`userData` Arguments passed to your function.

**See Also**  
[TextResult](class/TextResult.md)  
[FrameDecodingParameters.duplicateForgetTime](class/FrameDecodingParameters.md#duplicateforgettime)
