---
layout: default-layout
title: BarcodeReader License Methods - Dynamsoft Barcode Reader SDK Java Edition API Reference
description: This page shows BarcodeReader license methods of Dynamsoft Barcode Reader SDK Java Edition API Reference.
keywords: initLicense, initLicenseFromServer, initLicenseFromLicenseContent, outputLicenseToString, license methods, BarcodeReader, api reference, java
needAutoGenerateSidebar: true
permalink: /programming/java/api-reference/BarcodeReader/license.html
---


# License Methods

  | Method               | Description |
  |----------------------|-------------|
  | [`initLicense`](#initlicense) | Initializes license key and activate the SDK. |
  | [`getDeviceUUID`](#getdeviceuuid) | Gets the device uuid used for license activating. |
  | [`isInstanceValid`](#isinstancevalid) | Gets whether the instance is valid when charging by concurrent instances count. |
  | [`setDeviceFriendlyName`](#setdevicefriendlyname) | Sets a human-readable name that identifies the device. |
  | [`setLicenseCachePath`](#setlicensecachepath) | Sets a directory path for saving the license cache. |
  | [`setMaxConcurrentInstanceCount`](#setmaxconcurrentinstancecount) | Sets the max concurrent instance count used for current device and process. |
  | [`getInstancePoolStatus`](#getinstancepoolstatus) | Gets a class to represent the status of an instance pool. |
  | [`getIdleInstancesCount`](#getidleinstancescount) | `Deprecated` |
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
BarcodeReader reader = BarcodeReader.getInstance();
if(reader != null)
{
    // add further process
    reader.recycle();
}
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
BarcodeReader reader = BarcodeReader.getInstance();
if(reader != null)
{
    // add further process
    reader.recycle();
}
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
BarcodeReader reader = BarcodeReader.getInstance();
if(reader != null)
{
    // add further process
    reader.recycle();
}
```

## setMaxConcurrentInstanceCount

Sets the max concurrent instance count used for current device and process.

```java
static void com.dynamsoft.dbr.BarcodeReader.setMaxConcurrentInstanceCount(int countForThisDevice, int countForThisProcess)
static void com.dynamsoft.dbr.BarcodeReader.setMaxConcurrentInstanceCount(int countForThisDevice, int countForThisProcess, int timeout)
```

**Parameters**

`[in] countForThisDevice` The maximum number of concurrent instances that the current device can run.

`[in] countForThisProcess` The maximum number of concurrent instances that the current process can run.

`[in] timeout` The maximum time (in milliseconds) to wait for an available authorization or instance when calling initLicense, getInstance, or decode functions.

**Code Snippet**

```java
int countForThisDevice = 1; // The count value should be set based on your purchased license count
int countForThisProcess = 1; // The count value should be set based on your purchased license count
BarcodeReader.setMaxConcurrentInstanceCount(countForThisDevice, countForThisProcess);
BarcodeReader.initLicense("YOUR-LICENSE-KEY");
BarcodeReader reader = BarcodeReader.getInstance();
// If no instance is available right away, the application will wait until one becomes available
if(reader != null)
{
    // Add your code here to call decoding method, process barcode results and so on
    // ...
    // Recycle the instance to make it idle for other concurrent tasks
    reader.recycle();
}
```

## getInstancePoolStatus

Gets a class to represent the status of an instance pool.

```cpp
static InstancePoolStatus com.dynamsoft.dbr.BarcodeReader.getInstancePoolStatus() throws BarcodeReaderException
```

**Return Value**

Returns the [`InstancePoolStatus`]({{ site.java_class }}InstancePoolStatus.html) class representing the status of an instance pool.

**Exception**

[`BarcodeReaderException`](../class/BarcodeReaderException.md)

## getIdleInstancesCount

`Deprecated`. It still works in this version but could be removed in the near future.

```java
static int com.dynamsoft.dbr.BarcodeReader.getIdleInstancesCount()
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
