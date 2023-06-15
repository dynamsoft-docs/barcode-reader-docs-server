---
layout: default-layout
title: Callbacks - Dynamsoft Barcode Reader SDK C Edition API Reference
description: This is the callbacks of Dynamsoft Barcode Reader SDK C Edition.
keywords: CB_Error, CB_IntermediateResult, CB_TextResult, Callbacks, api reference, c
needAutoGenerateSidebar: true
permalink: /programming/c/api-reference/function-pointer.html
---

# Callbacks

  | Function | Description |
  |----------|-------------|
  | [`CB_Error`](#cb_error) | Represents the function that will handle the error code returned by the SDK. |
  | [`CB_IntermediateResult`](#cb_intermediateresult) | Represents the function that will handle the intermediate result array returned by the SDK. |
  | [`CB_TextResult`](#cb_textresult) | Represents the function that will handle the text result array returned by the SDK. | 
  
---
 




## CB_Error
Represents the function that will handle the error code returned by the SDK.

```c
typedef void(* CB_Error) (int frameId, int errorCode, void* pUser)
```   
   
**Parameters**  
`frameId` 	The ID of the frame.  
`errorCode` Error Code generated when decoding the frame.   
`pUser` Customized arguments passed to your function.

**See Also**  
[Error Code]({{ site.c_cpp_enumerations }}error-code.html)







## CB_IntermediateResult
Represents the function that will handle the intermediate result array returned by the SDK.

```c
typedef void(* CB_IntermediateResult) (int frameId, IntermediateResultArray* pResults, void* pUser)
```   
   
**Parameters**  
`frameId` 	The ID of the frame.  
`pResults` The intermediate results of the frame.   
`pUser` Arguments passed to your function.

**See Also**  
[IntermediateResultArray]({{ site.structs }}IntermediateResultArray.html)







## CB_TextResult
Represents the function that will handle the text result array returned by the SDK.

```c
typedef void(* CB_TextResult) (int frameId, TextResultArray *pResults, void *pUser)
```   
   
**Parameters**  
`frameId` 	The ID of the frame.  
`pResults` Recognized barcode results of the frame.   
`pUser` Arguments passed to your function.

**See Also**  
[TextResultArray]({{ site.structs }}TextResultArray.html)




