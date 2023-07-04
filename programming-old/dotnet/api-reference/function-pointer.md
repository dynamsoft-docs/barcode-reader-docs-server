---
layout: default-layout
title: Delegates - Dynamsoft Barcode Reader SDK .NET Edition API Reference
description: This page shows Delegates of Dynamsoft Barcode Reader SDK .NET Edition.
keywords: CB_Error, CB_IntermediateResult, CB_TextResult, delegates, api reference, .Net
needAutoGenerateSidebar: false
permalink: /programming/dotnet/api-reference/function-pointer.html
---


# Delegates

  | Delegate | Description |
  |----------|-------------|
  | [`CB_Error`](#cb_error) | Represents the method that will handle the error code returned by the SDK. |
  | [`CB_IntermediateResult`](#cb_intermediateresult) | Represents the method that will handle the intermediate result array returned by the SDK. |
  | [`CB_TextResult`](#cb_textresult) | Represents the method that will handle the text result array returned by the SDK. | 
   


## CB_Error
Represents the method that will handle the error code returned by the SDK. 

```csharp
delegate void Dynamsoft.DBR.CB_Error(int frameId, int errorCode, IntPtr pUser)
```   
   
**Parameters**  
`[in, out] frameId` The id of the frame.  
`[in, out] errorCode` Error Code generated when decoding the frame.  
`[in, out] pUser` Arguments pass to your function.  





## CB_IntermediateResult
Represents the method that will handle the intermediate result array returned by the SDK. 

```csharp
delegate void Dynamsoft.DBR.CB_IntermediateResult(int frameId, IntermediateResult[] intermediateResults, IntPtr pUser)
```   
   
**Parameters**  
`[in, out] frameId` The id of the frame.  
`[in, out] intermediateResults` The intermediate results of the frame. 
`[in, out] pUser` Arguments pass to your function.  





## CB_TextResult
Represents the method that will handle the text result array returned by the SDK. 

```csharp
delegate void Dynamsoft.DBR.CB_TextResult(int frameId, TextResult[]  textResults, IntPtr pUser) 
```   
   
**Parameters**  
`[in, out] frameId` The id of the frame.  
`[in, out] textResults` Recognized barcode results of the frame. 
`[in, out] pUser` Arguments pass to your function. 

