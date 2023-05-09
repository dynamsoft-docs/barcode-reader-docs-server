---
layout: default-layout
title: Initialize and Destroy Functions - Dynamsoft Barcode Reader SDK C Edition API Reference
description: This page shows Initialize and Destroy functions of Dynamsoft Barcode Reader SDK C Edition.
keywords: DBR_CreateInstance, DBR_DestroyInstance, initialize and destroy functions, api reference, c
needAutoGenerateSidebar: true
permalink: /programming/c/api-reference/methods/initialize-and-destroy-v9.4.0.html
---


# Initialize and Destroy Functions

  | Function               | Description |
  |----------------------|-------------|
  | [`DBR_CreateInstance`](#dbr_createinstance) | Creates an instance of Dynamsoft Barcode Reader. |
  | [`DBR_DestroyInstance`](#dbr_destroyinstance) | Destroys the instance of Dynamsoft Barcode Reader. |
  
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
