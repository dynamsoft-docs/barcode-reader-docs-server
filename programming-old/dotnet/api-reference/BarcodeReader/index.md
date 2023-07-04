---
layout: default-layout
title: BarcodeReader Methods - Dynamsoft Barcode Reader SDK .NET Edition API Reference
description: This page shows BarcodeReader methods of Dynamsoft Barcode Reader SDK .NET Edition.
keywords: methods, BarcodeReader, api reference, .Net
needAutoGenerateSidebar: true
permalink: /programming/dotnet/api-reference/BarcodeReader/index.html
---

# Class Dynamsoft.DBR.BarcodeReader

## Constructor and Destructor
   
  | Method               | Description |
  |----------------------|-------------|
  | [`BarcodeReader`](constructor-and-destructor.md#barcodereader) | Constructor of `BarcodeReader` object.|
  | [`Dispose`](constructor-and-destructor.md#dispose) | Destroys an instance of Dynamsoft Barcode Reader. |
  | [`GetInstance`](constructor-and-destructor.md#getinstance) | Gets an idle Dynamsoft Barcode Reader instance running on concurrent instance mode. |
  | [`Recycle`](constructor-and-destructor.md#recycle) | Recycles a Dynamsoft Barcode Reader instance running on concurrent instance mode. |
 
## License
  
  | Method               | Description |
  |----------------------|-------------|
  | [`InitLicense`](license.md#initlicense) | Initializes license key and activate the SDK. |
  | [`GetDeviceUUID`](license.md#getdeviceuuid) | Gets the device uuid used for license activating. |
  | [`IsInstanceValid`](license.md#isinstancevalid) | Gets whether the instance is valid when charging by concurrent instances count. |
  | [`SetDeviceFriendlyName`](license.md#setdevicefriendlyname) | Sets a human-readable name that identifies the device. |
  | [`SetLicenseCachePath`](license.md#setlicensecachepath) | Sets a directory path for saving the license cache. |
  | [`SetMaxConcurrentInstanceCount`](license.md#setmaxconcurrentinstancecount) | Sets the max concurrent instance count used for current device and process. |
  | [`GetIdleInstancesCount`](license.md#getidleinstancescount) | `Deprecated` |
  | [`InitLicenseFromServer`](license.md#initlicensefromserver) | `Deprecated` |
  | [`InitLicenseFromLicenseContent`](license.md#initlicensefromlicensecontent) | `Deprecated` |
  | [`OutputLicenseToString`](license.md#outputlicensetostring) | `Deprecated` |
  | [`InitDLSConnectionParameters`](license.md#initdlsconnectionparameters) | `Deprecated` |
  | [`InitLicenseFromDLS`](license.md#initlicensefromdls) | `Deprecated` |
  | [`InitLTSConnectionParameters`](license.md#initltsconnectionparameters) | `Deprecated` |
  | [`InitLicenseFromLTS`](license.md#initlicensefromlts) | `Deprecated` |
   
   
   
## Decode
   
  | Method               | Description |
  |----------------------|-------------|
  | [`DecodeFile`](decode.md#decodefile) | Decodes barcodes from a specified image file. |
  | [`DecodeFileInMemory`](decode.md#decodefileinmemory) | Decode barcodes from an image file in memory. |
  | [`DecodeBuffer`](decode.md#decodebuffer) | Decodes barcodes from the memory buffer containing image pixels in defined format. |
  | [`DecodeBase64String`](decode.md#decodebase64string) | Decodes barcodes from a base64 encoded string. |
  | [`DecodeBitmap`](decode.md#decodebitmap) | Decodes barcode from a bitmap. |
  | [`InitIntermediateResult`](decode.md#initintermediateresult) | Inits an intermediateResult struct with default values. |
  | [`DecodeIntermediateResults`](decode.md#decodeintermediateresults) | Decodes barcode from intermediate results. |
  
   

## Basic Settings Functions
   
  | Method               | Description |
  |----------------------|-------------|
  | [`SetModeArgument`](parameter-and-runtime-settings-basic.md#setmodeargument) | Sets the optional argument for a specified mode in Modes parameters. |
  | [`GetModeArgument`](parameter-and-runtime-settings-basic.md#getmodeargument) | Gets the optional argument for a specified mode in Modes parameters.  |
  | [`GetRuntimeSettings`](parameter-and-runtime-settings-basic.md#getruntimesettings) | Gets current runtime settings. |
  | [`UpdateRuntimeSettings`](parameter-and-runtime-settings-basic.md#updateruntimesettings) | Update runtime settings with a given struct. |
  | [`ResetRuntimeSettings`](parameter-and-runtime-settings-basic.md#resetruntimesettings) | Resets all parameters to default values. |

## Advanced Settings Functions
  
  | Method               | Description |
  |----------------------|-------------|
  | [`InitRuntimeSettingsWithFile`](parameter-and-runtime-settings-advanced.md#initruntimesettingswithfile)  | Initializes runtime settings with the settings in a given JSON file. |
  | [`InitRuntimeSettingsWithString`](parameter-and-runtime-settings-advanced.md#initruntimesettingswithstring) | Initializes runtime settings with the settings in a given JSON string. |
  | [`AppendTplFileToRuntimeSettings`](parameter-and-runtime-settings-advanced.md#appendtplfiletoruntimesettings) | Appends a new template file to the current runtime settings. |
  | [`AppendTplStringToRuntimeSettings`](parameter-and-runtime-settings-advanced.md#appendtplstringtoruntimesettings) | Appends a new template string to the current runtime settings. |
  | [`GetAllParameterTemplateNames`](parameter-and-runtime-settings-advanced.md#getallparametertemplatenames) | Gets the parameter templates name array. |
  | [`OutputSettingsToFile`](parameter-and-runtime-settings-advanced.md#outputsettingstofile) | Outputs runtime settings to a settings file (JSON file). |
  | [`OutputSettingsToString`](parameter-and-runtime-settings-advanced.md#outputsettingstostring) | Outputs runtime settings to a string. |
   
   
## General
   
  | Method               | Description |
  |----------------------|-------------|
  | [`GetVersion`](general.md#getversion) | Gets version information of SDK. |
  | [`TransformCoordinates`](general.md#transformcoordinates) | Transform the coordinates of a point based on the given transformation matrix. |
   
      
 

   
## Video

### Decode
    
   | Method               | Description |
   |----------------------|-------------|
   | [`StartFrameDecoding`](video.md#startframedecoding) | Starts a new thread to decode barcodes from the inner frame queue. |
   | [`StartFrameDecodingEx`](video.md#startframedecodingex) | Starts a new thread to decode barcodes from the inner frame queue. |
   | [`AppendFrame`](video.md#appendframe) | Appends a frame image buffer to the inner frame queue. |
   | [`StopFrameDecoding`](video.md#stopframedecoding) | Stops the frame decoding thread created by StartFrameDecoding. |

### Parameter
   
   | Method               | Description |
   |----------------------|-------------|
   | [`InitFrameDecodingParameters`](video.md#initframedecodingparameters) | Initializes frame decoding parameters. |


### Callback

   | Method               | Description |
   |----------------------|-------------|
   | [`SetErrorCallback`](video.md#seterrorcallback) | Set callback function to process errors which is triggered when the library finishes decoding a frame. |
   | [`SetTextResultCallback`](video.md#settextresultcallback) | Set callback function to process text results which is triggered when the library finishes decoding a frame. |
  | [`SetUniqueBarcodeCallback`](video.md#setuniquebarcodecallback) | Set callback function to process text results which is triggered when the library finishes decoding a frame and finds unique barcodes. |
   | [`SetIntermediateResultCallback`](video.md#setintermediateresultcallback) | Set callback function to process intermediate results which is triggered when the library finishes decoding a frame. |

### Status retrieval
   
   | Method               | Description |
   |----------------------|-------------|
   | [`GetLengthOfFrameQueue`](video.md#getlengthofframequeue) | Gets length of current inner frame queue. |
 
   
 


## Result

   | Method               | Description |
   |----------------------|-------------|
   | [`GetIntermediateResults`](result.md#getintermediateresults) | Returns intermediate results containing the original image, the colour clustered image, the binarized Image, contours, Lines, TextBlocks, etc.  |


 


## `BarcodeReader` Attributes
  
  | Attribute            | Description |
  |----------------------|-------------|
  | `ProductKeys`  | `Deprecated`. It still works in this version but could be removed in the near future. |
  
   
 
