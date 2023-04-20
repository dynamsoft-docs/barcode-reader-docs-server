---
layout: default-layout
title: BarcodeReader Methods - Dynamsoft Barcode Reader SDK Java Edition API Reference
description: This page shows all BarcodeReader methods of Dynamsoft Barcode Reader SDK Java Edition API Reference.
keywords: methods, BarcodeReader, api reference, java
needAutoGenerateSidebar: true
---


# Class com.dynamsoft.dbr.BarcodeReader

## Initialize and Destroy
   
  | Method               | Description |
  |----------------------|-------------|
  | [`BarcodeReader`](initialize-and-destroy.md#barcodereader) | Initialization of `BarcodeReader` object.|
  | [`destroy`](initialize-and-destroy.md#destroy) | Destroys an instance of `BarcodeReader` object.|
  | [`getInstance`](initialize-and-destroy.md#getinstance) | Gets an idle Dynamsoft Barcode Reader instance running on concurrent instance mode. |
  | [`recycle`](initialize-and-destroy.md#recycle) | Recycles a Dynamsoft Barcode Reader instance running on concurrent instance mode. |
   
   

   

## License
  
  | Method               | Description |
  |----------------------|-------------|
  | [`initLicense`](license.md#initlicense) | Initializes license key and activate the SDK. |
  | [`isInstanceValid`](license.md#isinstancevalid) | Gets whether the instance is valid when charging by concurrent instances count. |
  | [`setDeviceFriendlyName`](license.md#setdevicefriendlyname) | Sets a human-readable name that identifies the device. |
  | [`setMaxConcurrentInstanceCount`](license.md#setmaxconcurrentinstancecount) | Sets the max concurrent instance count used for current device and process. |
  | [`getIdleInstancesCount`](license.md#getidleinstancescount) | `Deprecated` |
  | [`initLicenseFromServer`](license.md#initlicensefromserver) | `Deprecated` |
  | [`initLicenseFromLicenseContent`](license.md#initlicensefromlicensecontent) | `Deprecated` |
  | [`outputLicenseToString`](license.md#outputlicensetostring) | `Deprecated` |
  | [`initDLSConnectionParameters`](license.md#initdlsconnectionparameters) | `Deprecated` |
  | [`initLicenseFromDLS`](license.md#initlicensefromdls) | `Deprecated` |
  | [`initLTSConnectionParameters`](license.md#initltsconnectionparameters) | `Deprecated` |
  | [`initLicenseFromLTS`](license.md#initlicensefromlts) | `Deprecated` |


## Decode
   
  | Method               | Description |
  |----------------------|-------------|
  | [`decodeFile`](decode.md#decodefile) | Decode barcodes from a specified image file. |
  | [`decodeFileInMemory`](decode.md#decodefileinmemory) | Decode barcodes from an image file in memory. |
  | [`decodeBuffer`](decode.md#decodebuffer) | Decode barcodes from raw buffer. |
  | [`decodeBase64String`](decode.md#decodebase64string) | Decode barcodes from a base64 encoded string. |
  | [`decodeBufferedImage`](decode.md#decodebufferedimage) | Decodes barcode from a buffered imag (bitmap). |
  | [`initIntermediateResult`](decode.md#initintermediateresult) | Inits an intermediateResult struct with default values. |
  | [`decodeIntermediateResults`](decode.md#decodeintermediateresults) | Decodes barcode from intermediate results. |
   
   
   
## Basic Settings Functions
   
  | Method               | Description |
  |----------------------|-------------|
  | [`setModeArgument`](parameter-and-runtime-settings-basic.md#setmodeargument) | Set argument value for the specified mode parameter. |
  | [`getModeArgument`](parameter-and-runtime-settings-basic.md#getmodeargument) | Get argument value for the specified mode parameter. |
  | [`getRuntimeSettings`](parameter-and-runtime-settings-basic.md#getruntimesettings) | Get current runtime settings. |
  | [`updateRuntimeSettings`](parameter-and-runtime-settings-basic.md#updateruntimesettings) | Modify and update the current runtime settings. |
  | [`resetRuntimeSettings`](parameter-and-runtime-settings-basic.md#resetruntimesettings) | Reset runtime settings to default. |

## Advanced Settings Functions
  
  | Method               | Description |
  |----------------------|-------------|
  | [`initRuntimeSettingsWithFile`](parameter-and-runtime-settings-advanced.md#initruntimesettingswithfile)  | Initialize runtime settings with the settings in a given JSON file. |
  | [`initRuntimeSettingsWithString`](parameter-and-runtime-settings-advanced.md#initruntimesettingswithstring) | Initialize runtime settings with the settings in a given JSON string. |
  | [`appendTplFileToRuntimeSettings`](parameter-and-runtime-settings-advanced.md#appendtplfiletoruntimesettings) | Append a new template file to the current runtime settings. |
  | [`appendTplStringToRuntimeSettings`](parameter-and-runtime-settings-advanced.md#appendtplstringtoruntimesettings) | Append a new template string to the current runtime settings. |
  | [`getAllParameterTemplateNames`](parameter-and-runtime-settings-advanced.md#getallparametertemplatenames) | Gets the parameter templates name array. |
  | [`outputSettingsToFile`](parameter-and-runtime-settings-advanced.md#outputsettingstofile) | Output runtime settings to a settings file (JSON file). |
  | [`outputSettingsToString`](parameter-and-runtime-settings-advanced.md#outputsettingstostring) | Output runtime settings to a string. |
   
      
   
   
## Result
   
  | Method               | Description |
  |----------------------|-------------|
  | [`getIntermediateResults`](result.md#getintermediateresults) | Get intermediate results. |
   
      


   
## General
   
  | Method               | Description |
  |----------------------|-------------|
  | [`getVersion`](general.md#getversion) | Get version information of SDK.|
  | [`transformCoordinates`](general.md#transformcoordinates) | Transform the coordinates of a point based on the given transformation matrix. |
   
      


   
## Video

### Decode
    
   | Method               | Description |
   |----------------------|-------------|
   | [`startFrameDecoding`](video.md#startframedecoding) | Decode barcodes from inner frame queue. |
   | [`startFrameDecodingEx`](video.md#startframedecodingex) | Decode barcodes from inner frame queue. |
   | [`appendFrame`](video.md#appendframe) | Append a frame image buffer to the inner frame queue. |
   | [`stopFrameDecoding`](video.md#stopframedecoding) | Stop thread used for frame decoding. |

### Parameter
   
   | Method               | Description |
   |----------------------|-------------|
   | [`initFrameDecodingParameters`](video.md#initframedecodingparameters) | Initialize frame decoding parameter. |

### Callback
   
   | Method               | Description |
   |----------------------|-------------|
   | [`setErrorCallback`](video.md#seterrorcallback) | Set callback interface to process errors which is triggered when the library finishes decoding a frame. |
   | [`setTextResultCallback`](video.md#settextresultcallback) | Set callback interface to process text results which is triggered when the library finishes decoding a frame. |
   | [`setIntermediateResultCallback`](video.md#setintermediateresultcallback) | Set callback interface to process intermediate results which is triggered when the library finishes decoding a frame. |

### Status retrieval
   
   | Method               | Description |
   |----------------------|-------------|
   | [`getLengthOfFrameQueue`](video.md#getlengthofframequeue) | Get length of current inner frame queue. |
 
   