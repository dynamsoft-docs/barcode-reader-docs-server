---
layout: default-layout
title: CBarcodeReader License Methods - Dynamsoft Barcode Reader SDK C++ Edition API Reference
description: This page shows CBarcodeReader license methods of Dynamsoft Barcode Reader SDK C++ Edition.
keywords: InitLicense, license methods, CBarcodeReader, api reference, c++
needAutoGenerateSidebar: true
permalink: /programming/cplusplus/api-reference/cbarcodereader-methods/license-v9.6.0.html
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
  | [`OutputLicenseToStringPtr`](#outputlicensetostringptr) | `Deprecated` |
  | [`FreeLicenseString`](#freelicensestring) | `Deprecated` |
  | [`InitDLSConnectionParameters`](#initdlsconnectionparameters) | `Deprecated` |
  | [`InitLicenseFromDLS`](#initlicensefromdls) | `Deprecated` |
  | [`InitLTSConnectionParameters`](#initltsconnectionparameters) | `Deprecated` |
  | [`InitLicenseFromLTS`](#initlicensefromlts) | `Deprecated` |


## InitLicense
Initializes license key and activate the SDK.

```cpp
static int dynamsoft::dbr::CBarcodeReader::InitLicense (const char* pLicense, char errorMsgBuffer[] = NULL, const int errorMsgBufferLen = 0)	
```   
   
**Parameters**  
`[in]	pLicense` The product keys.  
`[in, out] errorMsgBuffer` The buffer is allocated by caller and the recommended length is 512. The error message will be copied to the buffer.  
`[in]	errorMsgBufferLen` The length of allocated buffer.  


**Return Value**  
Returns error code (returns 0 if the function operates successfully).    
*You can call [`GetErrorString`](general.md#geterrorstring) to get detailed error message.*


**Code Snippet**  
```cpp
char errorBuf[512];
dynamsoft::dbr::CBarcodeReader::InitLicense("YOUR-LICENSE-KEY", errorBuf, 512);
CBarcodeReader* reader = new CBarcodeReader();
// add further process
```

## IsInstanceValid

Gets whether the instance is valid when charging by concurrent instances count.

```cpp
int dynamsoft::dbr::CBarcodeReader::IsInstanceValid()
```

**Return Value**

Returns an int value indicating whether the instance is valid for running on concurrent instance mode.

- 0: The instance is not valid for running on concurrent instance mode.
- 1: The instance is valid for running on concurrent instance mode.

**Remarks**

This method is meaningful only when using a license charged by concurrent instances count.

## SetDeviceFriendlyName

Sets a human-readable name that identifies the device.

```cpp
static int dynamsoft::dbr::CBarcodeReader::SetDeviceFriendlyName(const char* name)
```

**Parameters**

`[in] name` The device alias.

**Return Value**

Returns error code (returns 0 if the function operates successfully).

*You can call [`GetErrorString`](general.md#geterrorstring) to get detailed error message.*

**Code Snippet**

```cpp
char errorBuf[512];
dynamsoft::dbr::CBarcodeReader::SetDeviceFriendlyName("My-PC");
dynamsoft::dbr::CBarcodeReader::InitLicense("YOUR-LICENSE-KEY", errorBuf, 512);
CBarcodeReader* reader = new CBarcodeReader();
// add further process
```

## SetMaxConcurrentInstanceCount

Sets the max concurrent instance count used for current device and process.

```cpp
static void dynamsoft::dbr::CBarcodeReader::SetMaxConcurrentInstanceCount(int countForThisDevice, int countForThisProcess = 0)
```

**Parameters**

`[in] countForThisDevice` The maximum number of concurrent instances that the current device can run.

`[in] countForThisProcess` <sub>Optional</sub> The maximum number of concurrent instances that the current process can run.

**Code Snippet**

```cpp
char errorBuf[512];
int countForThisDevice = 1; // The count value should be set based on your purchased license count
int countForThisProcess = 1; // The count value should be set based on your purchased license count
dynamsoft::dbr::CBarcodeReader::SetMaxConcurrentInstanceCount(countForThisDevice, countForThisProcess);
dynamsoft::dbr::CBarcodeReader::InitLicense("YOUR-LICENSE-KEY", errorBuf, 512);
CBarcodeReader* dbr = dynamsoft::dbr::CBarcodeReader::GetInstance();
// If no instance is available right away, the application will wait until one becomes available
if(dbr != NULL)
{
    // Add your code here to call decoding method, process barcode results and so on
    // ...
    // Recycle the instance to make it idle for other concurrent tasks
    dbr->Recycle();
}
```

## GetIdleInstancesCount

`Deprecated`. It still works in this version but could be removed in the near future.

```cpp
static int dynamsoft::dbr::CBarcodeReader::GetIdleInstancesCount()
```

## InitLicenseFromServer
`Deprecated`. It still works in this version but could be removed in the near future.

```cpp
int dynamsoft::dbr::CBarcodeReader::InitLicenseFromServer (const char* pLicenseServer, const char* pLicenseKey)
```   
   

## InitLicenseFromLicenseContent
`Deprecated`. It still works in this version but could be removed in the near future.

```cpp
int dynamsoft::dbr::CBarcodeReader::InitLicenseFromLicenseContent (const char* pLicenseKey, const char* pLicenseContent)	
```   


## OutputLicenseToString
`Deprecated`. It still works in this version but could be removed in the near future.

```cpp
int dynamsoft::dbr::CBarcodeReader::OutputLicenseToString (char content[], const int contentLen)
```   
   

## OutputLicenseToStringPtr
`Deprecated`. It still works in this version but could be removed in the near future.

```cpp
int dynamsoft::dbr::CBarcodeReader::OutputLicenseToStringPtr (char** content)
```   


## FreeLicenseString
`Deprecated`. It still works in this version but could be removed in the near future.

```cpp
void dynamsoft::dbr::CBarcodeReader::FreeLicenseString (char** content)
```   


## InitDLSConnectionParameters
`Deprecated`. It still works in this version but could be removed in the near future.

```cpp
static int dynamsoft::dbr::CBarcodeReader::InitDLSConnectionParameters(DM_DLSConnectionParameters *pDLSConnectionParameters)
```   
   


## InitLicenseFromDLS
`Deprecated`. It still works in this version but could be removed in the near future.

```cpp
static int dynamsoft::dbr::CBarcodeReader::InitLicenseFromDLS(DM_DLSConnectionParameters *pDLSConnectionParameters, char errorMsgBuffer[] = NULL, const int errorMsgBufferLen = 0)
```   
   

## InitLTSConnectionParameters
`Deprecated`. It still works in this version but could be removed in the near future.

## InitLicenseFromLTS
`Deprecated`. It still works in this version but could be removed in the near future.

