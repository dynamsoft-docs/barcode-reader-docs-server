---
layout: default-layout
title: Initialize and Destroy Functions - Dynamsoft Barcode Reader SDK C Edition API Reference
description: This page shows Initialize and Destroy functions of Dynamsoft Barcode Reader SDK C Edition.
keywords: DBR_CreateInstance, DBR_DestroyInstance, initialize and destroy functions, api reference, c
needAutoGenerateSidebar: true
permalink: /programming/c/api-reference/methods/initialize-and-destroy.html
---


# Initialize and Destroy Functions

  | Function               | Description |
  |----------------------|-------------|
  | [`DBR_CreateInstance`](#dbr_createinstance) | Creates an instance of Dynamsoft Barcode Reader. |
  | [`DBR_DestroyInstance`](#dbr_destroyinstance) | Destroys the instance of Dynamsoft Barcode Reader. |
  | [`DBR_GetInstance`](#dbr_getinstance) | Gets an idle Dynamsoft Barcode Reader instance running on concurrent instance mode. |
  | [`DBR_RecycleInstance`](#dbr_recycleinstance) | Recycles a Dynamsoft Barcode Reader instance running on concurrent instance mode. |
  
  
## DBR_CreateInstance

Creates an instance of Dynamsoft Barcode Reader.

```c
DBR_API void* DBR_CreateInstance ()	
```   

**Return Value**  

Returns an instance of Dynamsoft Barcode Reader. If failed, returns `NULL`.


**Code Snippet**  

```c
char errorBuf[512];
DBR_InitLicense("YOUR-LICENSE-KEY", errorBuf, 512);
void* barcodeReader = DBR_CreateInstance();
DBR_DestroyInstance(barcodeReader);
```

## DBR_DestroyInstance

Destroys an instance of Dynamsoft Barcode Reader.

```c
DBR_API void DBR_DestroyInstance (void* barcodeReader)	
```   
   
**Parameters**  

`[in]	barcodeReader` Handle of the barcode reader instance.

**Code Snippet**  

```c
char errorBuf[512];
DBR_InitLicense("YOUR-LICENSE-KEY", errorBuf, 512);
void* barcodeReader = DBR_CreateInstance();
DBR_DestroyInstance(barcodeReader);
```

## DBR_GetInstance

Gets an idle Dynamsoft Barcode Reader instance running on concurrent instance mode.

```c
DBR_API void* DBR_GetInstance()
```

**Return Value**  
Returns an idle Dynamsoft Barcode Reader instance running on concurrent instance mode. If failed, returns `NULL`.

**Code Snippet**  

```c
//Make sure DBR_InitLicense have been called somewhere before DBR_GetInstance
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

## DBR_RecycleInstance

Recycles a Dynamsoft Barcode Reader instance running on concurrent instance mode.

```c
DBR_API void DBR_RecycleInstance (void* barcodeReader)
```

**Parameters**  

`[in] barcodeReader` Handle of a Dynamsoft Barcode Reader instance running on concurrent instance mode.

**Code Snippet**  

```c
//Make sure DBR_InitLicense have been called somewhere before DBR_GetInstance
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
