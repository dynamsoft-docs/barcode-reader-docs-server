---
layout: default-layout
title: BarcodeReaderException Class - Dynamsoft Barcode Reader SDK .NET Edition API Reference
description: This page shows the BarcodeReaderException Class of Dynamsoft Barcode Reader SDK .NET Edition.
keywords: BarcodeReaderException, class, api reference, .Net
needAutoGenerateSidebar: false
permalink: /programming/dotnet/api-reference/class/BarcodeReaderException.html
---


# BarcodeReaderException
The exception class of Dynamsoft.BarcodeReader.

```csharp
public class BarcodeReaderException : Exception
```  


## Attributes
  
| Attribute | Type |
|---------- | ----------- | 
| [`Code`](#code) | *EnumErrorCode* |
| [`Message`](#message) | *string* | 
| [`StackTrace`](#stacktrace) | *string* |
  
  
### Code
Gets or sets the error code. 

```csharp
EnumErrorCode Dynamsoft.DBR.BarcodeReaderException.Code
```  
**See Also**  
- [EnumErrorCode]({{site.dotnet_enumerations}}error-code.html)

### Message
Gets the message that describes the current exception. 

```csharp
override string Dynamsoft.DBR.BarcodeReaderException.Message
```  

### StackTrace
Gets the string representation of the frames on the call stack at the time the current exception was thrown. 

```csharp
override string Dynamsoft.DBR.BarcodeReaderException.StackTrace
```  

