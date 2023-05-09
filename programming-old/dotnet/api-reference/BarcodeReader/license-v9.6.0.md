---
layout: default-layout
title: BarcodeReader License Methods - Dynamsoft Barcode Reader SDK .NET Edition API Reference
description: This page shows BarcodeReader license methods of Dynamsoft Barcode Reader SDK .NET Edition.
keywords: InitLicenseFromServer, InitLicenseFromLicenseContent, OutputLicenseToString, license methods, BarcodeReader, api reference, .Net
needAutoGenerateSidebar: true
permalink: /programming/dotnet/api-reference/BarcodeReader/license-v9.6.0.html
---


# License Methods

  | Method               | Description |
  |----------------------|-------------|
  | [`InitLicense`](#initlicense) | Initializes license key and activate the SDK. |
  | [`IsInstanceValid`](#isinstancevalid) | Gets whether the instance is valid when charging by concurrent instances count. |
  | [`SetDeviceFriendlyName`](#setdevicefriendlyname) | Sets a human-readable name that identifies the device. |
  | [`SetMaxConcurrentInstanceCount`](#setmaxconcurrentinstancecount) | Sets the max concurrent instance count used for current device and process. |
  | [`GetIdleInstancesCount`](#getidleinstancescount) | `Deprecated` |
  | [`InitLicenseFromServer`](#initlicensefromserver) | `Deprecated` |
  | [`InitLicenseFromLicenseContent`](#initlicensefromlicensecontent) | `Deprecated` |
  | [`OutputLicenseToString`](#outputlicensetostring) | `Deprecated` |
  | [`InitDLSConnectionParameters`](#initdlsconnectionparameters) | `Deprecated` |
  | [`InitLicenseFromDLS`](#initlicensefromdls) | `Deprecated` |
  | [`InitLTSConnectionParameters`](#initltsconnectionparameters) | `Deprecated` |
  | [`InitLicenseFromLTS`](#initlicensefromlts) | `Deprecated` |
  


## InitLicense
Initializes license key and activate the SDK.

```csharp
static EnumErrorCode Dynamsoft.DBR.BarcodeReader.InitLicense (string license, out string errorMsg)
```   
   
**Parameters**  
`[in]	licenseKey`	<*string*> : The license key of Barcode Reader.   
`[out]	errorMsg` <*string*> : The detailed error message.

**Return Value**  
Returns error code (returns DBR_SUCCESS if the function operates successfully).    
*You can check `errorMsg` to get detailed error message.*

**Code Snippet**  
```csharp
string errorMsg;
BarcodeReader.InitLicense("YOUR-LICENSE-KEY", out errorMsg);
BarcodeReader reader = new BarcodeReader();
// add further process
```

## IsInstanceValid

Gets whether the instance is valid when charging by concurrent instances count.

```csharp
int Dynamsoft.DBR.BarcodeReader.IsInstanceValid()
```

**Return Value**

Returns an int value indicating whether the instance is valid for running on concurrent instance mode.

- 0: The instance is not valid for running on concurrent instance mode.
- 1: The instance is valid for running on concurrent instance mode.

**Remarks**

This method is meaningful only when using a license charged by concurrent instances count.

## SetDeviceFriendlyName

Sets a human-readable name that identifies the device.

```csharp
static EnumErrorCode Dynamsoft.DBR.BarcodeReader.SetDeviceFriendlyName(string name)
```

**Parameters**

`[in] name` The device alias.

**Return Value**

Returns error code (returns DBR_SUCCESS if the function operates successfully).

**Code Snippet**

```csharp
string errorMsg;
BarcodeReader.SetDeviceFriendlyName("My-PC");
BarcodeReader.InitLicense("YOUR-LICENSE-KEY", out errorMsg);
BarcodeReader reader = new BarcodeReader();
// add further process
```

## SetMaxConcurrentInstanceCount

Sets the max concurrent instance count used for current device and process.

```csharp
static void Dynamsoft.DBR.BarcodeReader.SetMaxConcurrentInstanceCount(int countForThisDevice, int countForThisProcess = 0)
```

**Parameters**

`[in] countForThisDevice` The maximum number of concurrent instances that the current device can run.

`[in] countForThisProcess` <sub>Optional</sub> The maximum number of concurrent instances that the current process can run.

**Code Snippet**

```csharp
string errorMsg;
int countForThisDevice = 1; // The count value should be set based on your purchased license count
int countForThisProcess = 1; // The count value should be set based on your purchased license count
BarcodeReader.SetMaxConcurrentInstanceCount(countForThisDevice, countForThisProcess);
BarcodeReader.InitLicense("YOUR-LICENSE-KEY", out errorMsg);
BarcodeReader reader = BarcodeReader.GetInstance();
// If no instance is available right away, the application will wait until one becomes available
if (reader != null)
{
    // Add your code here to call decoding method, process barcode results and so on
    // ...
    // Recycle the instance to make it idle for other concurrent tasks
    reader.Recycle();
}
```

## GetIdleInstancesCount

`Deprecated`. It still works in this version but could be removed in the near future.

```csharp
static int Dynamsoft.DBR.BarcodeReader.GetIdleInstancesCount()
```

## InitLicenseFromServer
`Deprecated`. It still works in this version but could be removed in the near future.

```csharp
int Dynamsoft.DBR.BarcodeReader.InitLicenseFromServer(string licenseServer, string licenseKey)
```   
   
## InitLicenseFromLicenseContent
`Deprecated`. It still works in this version but could be removed in the near future.

```csharp
int Dynamsoft.DBR.BarcodeReader.InitLicenseFromLicenseContent(string licenseKey, string strLicenseContent)
```

## OutputLicenseToString
`Deprecated`. It still works in this version but could be removed in the near future.

```csharp
string Dynamsoft.DBR.BarcodeReader.OutputLicenseToString()
```
   

## InitDLSConnectionParameters
`Deprecated`. It still works in this version but could be removed in the near future.

```csharp
static DMDLSConnectionParameters Dynamsoft.DBR.BarcodeReader.InitDLSConnectionParameters()
```   

## InitLicenseFromDLS
`Deprecated`. It still works in this version but could be removed in the near future.

```csharp
static EnumErrorCode Dynamsoft.DBR.BarcodeReader.InitLicenseFromDLS(DMDLSConnectionParameters dlsConnectionParameters, out string errorMsg)
```   


## InitLTSConnectionParameters
`Deprecated`. It still works in this version but could be removed in the near future.
## InitLicenseFromLTS
`Deprecated`. It still works in this version but could be removed in the near future.

