---
layout: default-layout
title: License Functions - Dynamsoft Barcode Reader SDK C Edition API Reference
description: This page shows the license functions of Dynamsoft Barcode Reader SDK C Edition.
keywords: DBR_InitLicense, license functions, api reference, c
needAutoGenerateSidebar: true
permalink: /programming/c/api-reference/methods/license-v9.6.0.html
---

# License Functions

  | Function               | Description |
  |----------------------|-------------|
  | [`DBR_InitLicense`](#dbr_initlicense) | Initializes license key and activate the SDK. |
  | [`DBR_IsInstanceValid`](#dbr_isinstancevalid) | Gets whether the instance is valid when charging by concurrent instances count. |
  | [`DBR_SetDeviceFriendlyName`](#dbr_setdevicefriendlyname) | Sets a human-readable name that identifies the device. |
  | [`DBR_SetMaxConcurrentInstanceCount`](#dbr_setmaxconcurrentinstancecount) | Sets the max concurrent instance count used for current device and process. |
  | [`DBR_GetIdleInstancesCount`](#dbr_getidleinstancescount) | `Deprecated` |
  | [`DBR_InitLicenseFromServer`](#dbr_initlicensefromserver) | `Deprecated` |
  | [`DBR_InitLicenseFromLicenseContent`](#dbr_initlicensefromlicensecontent) | `Deprecated` |
  | [`DBR_OutputLicenseToString`](#dbr_outputlicensetostring) | `Deprecated` |
  | [`DBR_OutputLicenseToStringPtr`](#dbr_outputlicensetostringptr) | `Deprecated` |
  | [`DBR_FreeLicenseString`](#dbr_freelicensestring) | `Deprecated` |
  | [`DBR_InitDLSConnectionParameters`](#dbr_initdlsconnectionparameters) | `Deprecated` |
  | [`DBR_InitLicenseFromDLS`](#dbr_initlicensefromdls) | `Deprecated` |
  | [`DBR_InitLTSConnectionParameters`](#dbr_initltsconnectionparameters) | `Deprecated` |
  | [`DBR_InitLicenseFromLTS`](#dbr_initlicensefromlts) | `Deprecated` |

## DBR_InitLicense

Initializes license key and activate the SDK.

```c
DBR_API int DBR_InitLicense (const char* pLicense, char errorMsgBuffer[], const int errorMsgBufferLen)
```

**Parameters**

`[in] pLicense` The license string.

`[in, out] errorMsgBuffer` The buffer is allocated by caller and the recommended length is 512. The error message will be copied to the buffer.

`[in] errorMsgBufferLen` The length of allocated buffer.

**Return Value**

Returns error code (returns 0 if the function operates successfully).

*You can call [`DBR_GetErrorString`](general.md#dbr_geterrorstring) to get detailed error message.*

**Code Snippet**

```c
char errorBuf[512];
DBR_InitLicense("YOUR-LICENSE-KEY", errorBuf, 512);
void* barcodeReader = DBR_CreateInstance();
// add further process
```

## DBR_IsInstanceValid

Gets whether the instance is valid when charging by concurrent instances count.

```c
DBR_API int DBR_IsInstanceValid (void* barcodeReader)
```

**Parameters**

`[in] barcodeReader` Handle of a Dynamsoft Barcode Reader instance.

**Return Value**

Returns an int value indicating whether the instance is valid for running on concurrent instance mode.

- 0: The instance is not valid for running on concurrent instance mode.
- 1: The instance is valid for running on concurrent instance mode.

**Remarks**

This method is meaningful only when using a license charged by concurrent instances count.

## DBR_SetDeviceFriendlyName

Sets a human-readable name that identifies the device.

```c
DBR_API int DBR_SetDeviceFriendlyName(const char* name)
```

**Parameters**

`[in] name` The device alias.

**Return Value**

Returns error code (returns 0 if the function operates successfully).

*You can call [`DBR_GetErrorString`](general.md#dbr_geterrorstring) to get detailed error message.*

**Code Snippet**

```c
char errorBuf[512];
DBR_SetDeviceFriendlyName("My-PC");
DBR_InitLicense("YOUR-LICENSE-KEY", errorBuf, 512);
void* barcodeReader = DBR_CreateInstance();
// add further process
```

## DBR_SetMaxConcurrentInstanceCount

Sets the max concurrent instance count used for current device and process.

```c
DBR_API void DBR_SetMaxConcurrentInstanceCount(int countForThisDevice, int countForThisProcess)
```

**Parameters**

`[in] countForThisDevice` The maximum number of concurrent instances that the current device can run.

`[in] countForThisProcess` The maximum number of concurrent instances that the current process can run.

**Code Snippet**

```c
char errorBuf[512];
int countForThisDevice = 1; // The count value should be set based on your purchased license count
int countForThisProcess = 1; // The count value should be set based on your purchased license count
DBR_SetMaxConcurrentInstanceCount(countForThisDevice, countForThisProcess);
DBR_InitLicense("YOUR-LICENSE-KEY", errorBuf, 512);
void* dbr = DBR_GetInstance();
// If no instance is available right away, the application will wait until one becomes available
if(dbr != NULL)
{
    // Add your code here to call decoding method, process barcode results and so on
    // ...
    // Recycle the instance to make it idle for other concurrent tasks
    DBR_RecycleInstance(dbr);
}
```

## DBR_InitLicenseFromServer

`Deprecated`. It still works in this version but could be removed in the near future.

```c
DBR_API int DBR_InitLicenseFromServer (void* barcodeReader, const char* pLicenseServer, const char* pLicenseKey)
```   

## DBR_GetIdleInstancesCount

`Deprecated`. It still works in this version but could be removed in the near future.

```c
DBR_API int DBR_GetIdleInstancesCount()
```

## DBR_InitLicenseFromLicenseContent
`Deprecated`. It still works in this version but could be removed in the near future.

```c
DBR_API int DBR_InitLicenseFromLicenseContent (void* barcodeReader, const char* pLicenseKey, const char* pLicenseContent)	
```   


## DBR_OutputLicenseToString
`Deprecated`. It still works in this version but could be removed in the near future.

```c
DBR_API int DBR_OutputLicenseToString (void* barcodeReader, char content[], int contentLen)
```   
   

## DBR_OutputLicenseToStringPtr
`Deprecated`. It still works in this version but could be removed in the near future.

```c
DBR_API int DBR_OutputLicenseToStringPtr (void* barcodeReader, char** content)
```   

   

## DBR_FreeLicenseString
`Deprecated`. It still works in this version but could be removed in the near future.

```c
DBR_API void DBR_FreeLicenseString (char** content)
```   


## DBR_InitDLSConnectionParameters
`Deprecated`. It still works in this version but could be removed in the near future.

```c
DBR_API int DBR_InitDLSConnectionParameters (DM_DLSConnectionParameters *pDLSConnectionParameters)
```   


## DBR_InitLicenseFromDLS
`Deprecated`. It still works in this version but could be removed in the near future.

```c
DBR_API int DBR_InitLicenseFromDLS(DM_DLSConnectionParameters *pDLSConnectionParameters, char errorMsgBuffer[], const int errorMsgBufferLen)
```   

## DBR_InitLTSConnectionParameters
`Deprecated`. It still works in this version but could be removed in the near future.

## DBR_InitLicenseFromLTS
`Deprecated`. It still works in this version but could be removed in the near future.
