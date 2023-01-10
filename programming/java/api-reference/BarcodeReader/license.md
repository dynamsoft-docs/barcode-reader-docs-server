---
layout: default-layout
title: BarcodeReader License Methods - Dynamsoft Barcode Reader SDK Java Edition API Reference
description: This page shows BarcodeReader license methods of Dynamsoft Barcode Reader SDK Java Edition API Reference.
keywords: initLicense, initLicenseFromServer, initLicenseFromLicenseContent, outputLicenseToString, license methods, BarcodeReader, api reference, java
needAutoGenerateSidebar: true
---


# License Methods

  | Method               | Description |
  |----------------------|-------------|
  | [`initLicense`](#initlicense) | Initializes license key and activate the SDK. |
  | [`getDeviceUUID`](#getdeviceuuid) | Gets the device uuid used for license activating. |
  | [`getIdleInstancesCount`](#getidleinstancescount) | Gets available instances count when charging by concurrent instances count. |
  | [`isInstanceValid`](#isinstancevalid) | Gets whether the instance is valid when charging by concurrent instances count. |
  | [`setDeviceFriendlyName`](#setdevicefriendlyname) | Sets a human-readable name that identifies the device. |
  | [`setLicenseCachePath`](#setlicensecachepath) | Sets a directory path for saving the license cache. |
  | [`setMaxConcurrentInstanceCount`](#setmaxconcurrentinstancecount) | Sets the max concurrent instance count used for current device and process. |
  | [`initLicenseFromServer`](#initlicensefromserver) | `Deprecated` |
  | [`initLicenseFromLicenseContent`](#initlicensefromlicensecontent) | `Deprecated` |
  | [`outputLicenseToString`](#outputlicensetostring) | `Deprecated` |
  | [`initDLSConnectionParameters`](#initdlsconnectionparameters) | `Deprecated` |
  | [`initLicenseFromDLS`](#initlicensefromdls) | `Deprecated` |
  | [`initLTSConnectionParameters`](#initltsconnectionparameters) | `Deprecated` |
  | [`initLicenseFromLTS`](#initlicensefromlts) | `Deprecated` |


## initLicense

Initializes license key and activates the SDK.

```java
static void com.dynamsoft.dbr.BarcodeReader.initLicense(String license) throws BarcodeReaderException
```   
   
**Parameters**  

`license` The product keys.

**Exception**  

[`BarcodeReaderException`](../class/BarcodeReaderException.md)

**Code Snippet**  

```java
BarcodeReader.initLicense("YOUR-LICENSE-KEY");
BarcodeReader reader = new BarcodeReader();
// add further process
```

## getDeviceUUID

Gets the device uuid used for license activating.

```java
static String com.dynamsoft.dbr.BarcodeReader.getDeviceUUID(int uuidGenerationMethod) throws BarcodeReaderException
```

**Parameters**  

`uuidGenerationMethod` The method used to generate the UUID.

- 1: Generates UUID with random values.
- 2: Generates UUID based on hardware info.

**Exception**  

[`BarcodeReaderException`](../class/BarcodeReaderException.md)

## getIdleInstancesCount

Gets the count of available instances when charging by concurrent instances count.

```java
static int com.dynamsoft.dbr.BarcodeReader.getIdleInstancesCount()
```   

**Return Value**  

Returns available instances count.

- 0: There is no space for new instance
- -1: The available count needs to be updated from server by calling initLicense.
- N ( N > 0 ): N more instances can be created.

**Code Snippet**  

```java
//...
int count = BarcodeReader.getIdleInstancesCount();
if(count > 0)
{
  //create instance and process further
}
if(count < 0)
{
  //call InitLicense
  //create instance and process further
}
if(count = 0)
{
  //waiting for available instances 
}
```


## isInstanceValid

Gets whether the instance is valid when charging by concurrent instances count.

```java
int com.dynamsoft.dbr.BarcodeReader.isInstanceValid()
```

**Return Value**

Returns an int value indicating whether the instance is valid for running on concurrent instance mode.

- 0: The instance is not valid for running on concurrent instance mode.
- 1: The instance is valid for running on concurrent instance mode.

**Remarks**

This method is meaningful only when using a license charged by concurrent instances count.

## setDeviceFriendlyName

Sets a human-readable name that identifies the device.

```java
static void com.dynamsoft.dbr.BarcodeReader.setDeviceFriendlyName(String name) throws BarcodeReaderException
```   
   
**Parameters**  

`name` The device alias.

**Exception**  

[`BarcodeReaderException`](../class/BarcodeReaderException.md)

**Code Snippet**  

```java
BarcodeReader.setDeviceFriendlyName("My-PC");
BarcodeReader.initLicense("YOUR-LICENSE-KEY");
BarcodeReader reader = new BarcodeReader();
// add further process
```

## setLicenseCachePath

Sets a directory path for saving the license cache.

```java
static void com.dynamsoft.dbr.BarcodeReader.setLicenseCachePath(String directoryPath) throws BarcodeReaderException
```

**Parameters**

`directoryPath` The directory path where to save the license cache.

**Exception**

[`BarcodeReaderException`](../class/BarcodeReaderException.md)

**Code Snippet**

```java
BarcodeReader.setLicenseCachePath("DIRECTORY-PATH-FOR-LICENSE-CACHE");
BarcodeReader.initLicense("YOUR-LICENSE-KEY");
BarcodeReader reader = new BarcodeReader();
// add further process
```

## setMaxConcurrentInstanceCount

Sets the max concurrent instance count used for current device and process.

```java
static void com.dynamsoft.dbr.BarcodeReader.setMaxConcurrentInstanceCount(int countForThisDevice, int countForThisProcess)
```

**Parameters**

`[in] countForThisDevice` The maximum number of concurrent instances that the current device can run.

`[in] countForThisProcess` The maximum number of concurrent instances that the current process can run.

**Code Snippet**

```java
int countForThisDevice = 10;
int countForThisProcess = 10;
BarcodeReader.setMaxConcurrentInstanceCount(countForThisDevice, countForThisProcess);
BarcodeReader.initLicense("YOUR-LICENSE-KEY");
BarcodeReader barcodeReader = BarcodeReader.getInstance();
// Add your code here to call decoding method, process barcode results and so on
// ...
// Recycle the barcodeReader instance to make it idle for other concurrent tasks
barcodeReader.recycle();
```

## initLicenseFromServer

`Deprecated`. It still works in this version but could be removed in the near future.

```java
void com.dynamsoft.dbr.BarcodeReader.initLicenseFromServer(String licenseServer, String licenseKey)	throws BarcodeReaderException
```   
   

## initLicenseFromLicenseContent

`Deprecated`. It still works in this version but could be removed in the near future.

```java
void com.dynamsoft.dbr.BarcodeReader.initLicenseFromLicenseContent(String licenseKey, String licenseContent) throws BarcodeReaderException
```   


## outputLicenseToString

`Deprecated`. It still works in this version but could be removed in the near future.

```java
String com.dynamsoft.dbr.BarcodeReader.outputLicenseToString() throws BarcodeReaderException
```   


## initDLSConnectionParameters

`Deprecated`. It still works in this version but could be removed in the near future.

```java
static DMDLSConnectionParameters com.dynamsoft.dbr.BarcodeReader.initDLSConnectionParameters() throws BarcodeReaderException
```

## initLicenseFromDLS

`Deprecated`. It still works in this version but could be removed in the near future.

```java
static void com.dynamsoft.dbr.BarcodeReader.initLicenseFromDLS(DMDLSConnectionParameters dlsInfo) throws BarcodeReaderException
```


## initLTSConnectionParameters
`Deprecated`. It still works in this version but could be removed in the near future.
## initLicenseFromLTS
`Deprecated`. It still works in this version but could be removed in the near future.
