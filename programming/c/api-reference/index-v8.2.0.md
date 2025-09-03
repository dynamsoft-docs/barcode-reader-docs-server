---
layout: default-layout
title: Main Page - Dynamsoft Barcode Reader SDK C Edition API Reference
description: This is the main page of Dynamsoft Barcode Reader SDK C Edition API Reference.
keywords: api reference, c
needAutoGenerateSidebar: false
breadcrumbText: API Reference
permalink: /programming/c/api-reference/index-v8.2.0.html
---

# Dynamsoft Barcode Reader SDK - C API Reference

- [Methods](#methods)
- [Function Pointer](#function-pointer)
- [Error Code](#error-code)
- [Structs](#structs)
- [Enumerations](#enumerations)  

 


## Methods

### Initialize and Destroy
  
  | Method               | Description |
  |----------------------|-------------|
  | [`DBR_CreateInstance`](methods/initialize-and-destroy.md#dbr_createinstance) | Create an instance of Dynamsoft Barcode Reader. |
  | [`DBR_DestroyInstance`](methods/initialize-and-destroy.md#dbr_destroyinstance) | Destroy the instance of Dynamsoft Barcode Reader. |


 


### Decode

  | Method               | Description |
  |----------------------|-------------|
  | [`DBR_DecodeFile`](methods/decode.md#dbr_decodefile) | Decode barcodes from a specified image file. |
  | [`DBR_DecodeFileInMemory`](methods/decode.md#dbr_decodefileinmemory) | Decode barcodes from an image file in memory. |
  | [`DBR_DecodeBuffer`](methods/decode.md#dbr_decodebuffer) | Decode barcodes from raw buffer. |
  | [`DBR_DecodeBase64String`](methods/decode.md#dbr_decodebase64string) | Decode barcodes from a base64 encoded string. |
  | [`DBR_DecodeDIB`](methods/decode.md#dbr_decodedib) | Decode barcode from a handle of device-independent bitmap (DIB). | 
  | [`DBR_InitIntermediateResult`](methods/decode.md#dbr_initintermediateresult) | Inits an intermediateResult struct with default values. |
  | [`DBR_DecodeIntermediateResults`](methods/decode.md#dbr_decodeintermediateresults) | Decodes barcode from intermediate results. |


 


### Parameter and Runtime Settings

#### Basic
  
  | Method               | Description |
  |----------------------|-------------|
  | [`DBR_SetModeArgument`](methods/parameter-and-runtime-settings-basic.md#dbr_setmodeargument) | Set argument value for the specified mode parameter. |
  | [`DBR_GetModeArgument`](methods/parameter-and-runtime-settings-basic.md#dbr_getmodeargument) | Get argument value for the specified mode parameter. |
  | [`DBR_GetRuntimeSettings`](methods/parameter-and-runtime-settings-basic.md#dbr_getruntimesettings) | Get current runtime settings. |
  | [`DBR_UpdateRuntimeSettings`](methods/parameter-and-runtime-settings-basic.md#dbr_updateruntimesettings) | Modify and update the current runtime settings. |
  | [`DBR_ResetRuntimeSettings`](methods/parameter-and-runtime-settings-basic.md#dbr_resetruntimesettings) | Reset runtime settings to default. |

#### Advanced
  
  | Method               | Description |
  |----------------------|-------------|
  | [`DBR_InitRuntimeSettingsWithFile`](methods/parameter-and-runtime-settings-advanced.md#dbr_initruntimesettingswithfile) | Initialize runtime settings with the settings in a given JSON file. |
  | [`DBR_InitRuntimeSettingsWithString`](methods/parameter-and-runtime-settings-advanced.md#dbr_initruntimesettingswithstring) | Initialize runtime settings with the settings in a given JSON string. |
  | [`DBR_AppendTplFileToRuntimeSettings`](methods/parameter-and-runtime-settings-advanced.md#dbr_appendtplfiletoruntimesettings) | Append a new template file to the current runtime settings. |
  | [`DBR_AppendTplStringToRuntimeSettings`](methods/parameter-and-runtime-settings-advanced.md#dbr_appendtplstringtoruntimesettings) | Append a new template string to the current runtime settings. |
  | [`DBR_GetParameterTemplateCount`](methods/parameter-and-runtime-settings-advanced.md#dbr_getparametertemplatecount) | Get the count of the parameter templates. |
  | [`DBR_GetParameterTemplateName`](methods/parameter-and-runtime-settings-advanced.md#dbr_getparametertemplatename) | Get the parameter template name by index. |
  | [`DBR_OutputSettingsToFile`](methods/parameter-and-runtime-settings-advanced.md#dbr_outputsettingstofile) | Output runtime settings to a settings file (JSON file). |
  | [`DBR_OutputSettingsToString`](methods/parameter-and-runtime-settings-advanced.md#dbr_outputsettingstostring) | Output runtime settings to a string. |
  | [`DBR_OutputSettingsToStringPtr`](methods/parameter-and-runtime-settings-advanced.md#dbr_outputsettingstostringptr) | Output runtime settings to a string. |
  | [`DBR_FreeSettingsString`](methods/parameter-and-runtime-settings-advanced.md#dbr_freesettingsstring) | Free memory allocated for runtime settings string. |


 


### License
   
  | Method               | Description |
  |----------------------|-------------|
  | [`DBR_InitLicense`](methods/license.md#dbr_initlicense) | Read product key and activate the SDK. |
  | [`DBR_InitLicenseFromServer`](methods/license.md#dbr_initlicensefromserver) | Initialize license and connect to the specified server for online verification. |
  | [`DBR_InitLicenseFromLicenseContent`](methods/license.md#dbr_initlicensefromlicensecontent) | Initialize license from the license content on client machine for offline verification. |
  | [`DBR_OutputLicenseToString`](methods/license.md#dbr_outputlicensetostring) | Output the license content to a string from the license server. |
  | [`DBR_OutputLicenseToStringPtr`](methods/license.md#dbr_outputlicensetostringptr) | Output the license content to a string from the license server. |
  | [`DBR_FreeLicenseString`](methods/license.md#dbr_freelicensestring) | Free memory allocated for the license string. |
  | [`DBR_InitLTSConnectionParameters`](methods/license.md#dbr_initltsconnectionparameters) | Initializes a DM_LTSConnectionParameters struct with default values. |
  | [`DBR_InitLicenseFromLTS`](methods/license.md#dbr_initlicensefromlts) | Initializes the barcode reader license and connects to the specified server for online verification. |

 


### Result
   
  | Method               | Description |
  |----------------------|-------------|
  | [`DBR_GetAllTextResults`](methods/result.md#dbr_getalltextresults) | Get all recognized barcode results.  |
  | [`DBR_FreeTextResults`](methods/result.md#dbr_freetextresults) | Free memory allocated for text results. |
  | [`DBR_GetIntermediateResults`](methods/result.md#dbr_getintermediateresults) | Get intermediate results. |
  | [`DBR_FreeIntermediateResults`](methods/result.md#dbr_freeintermediateresults) | Free memory allocated for the intermediate results. |


 


### General
  
  | Method               | Description |
  |----------------------|-------------|
  | [`DBR_GetErrorString`](methods/general.md#dbr_geterrorstring) | Get error message by error code. |
  | [`DBR_GetVersion`](methods/general.md#dbr_getversion) | Get version information of SDK. |


 


### Video
#### Decode
   
  | Method               | Description |
  |----------------------|-------------|
  | [`DBR_StartFrameDecoding`](methods/video.md#dbr_startframedecoding) | Decode barcodes from inner frame queue. |
  | [`DBR_StartFrameDecodingEx`](methods/video.md#dbr_startframedecodingex) | Decode barcodes from inner frame queue. |
  | [`DBR_AppendFrame`](methods/video.md#dbr_appendframe) | Append a frame image buffer to the inner frame queue. |
  | [`DBR_StopFrameDecoding`](methods/video.md#dbr_stopframedecoding) | Stop thread used for frame decoding. |

#### Parameter
   
  | Method               | Description |
  |----------------------|-------------|
  | [`DBR_InitFrameDecodingParameters`](methods/video.md#dbr_initframedecodingparameters) | Initialize frame decoding parameter. |

#### Callback
   
  | Method               | Description |
  |----------------------|-------------|
  | [`DBR_SetErrorCallback`](methods/video.md#dbr_seterrorcallback) | Set callback function to process errors which is triggered when the library finishes decoding a frame. |
  | [`DBR_SetTextResultCallback`](methods/video.md#dbr_settextresultcallback) | Set callback function to process text results which is triggered when the library finishes decoding a frame. |
  | [`DBR_SetIntermediateResultCallback`](methods/video.md#dbr_setintermediateresultcallback) | Set callback function to process intermediate results which is triggered when the library finishes decoding a frame. |

#### Status retrieval
   
  | Method               | Description |
  |----------------------|-------------|
  | [`DBR_GetLengthOfFrameQueue`](methods/video.md#dbr_getlengthofframequeue) | Get length of current inner frame queue. |
  

 

## Function Pointer

  | Function | Description |
  |----------|-------------|
  | [`CB_Error`](function-pointer.md#cb_error) | Represents the method that will handle the error code returned by the SDK. |
  | [`CB_IntermediateResult`](function-pointer.md#cb_intermediateresult) | Represents the method that will handle the intermediate result array returned by the SDK. |
  | [`CB_TextResult`](function-pointer.md#cb_textresult) | Represents the method that will handle the text result array returned by the SDK. | 



## [Error Code]({{ site.dbr_c_cpp_enumerations }}error-code.html)
		



## [Structs]({{ site.dbr_structs }})
- [`AztecDetails`]({{ site.dbr_structs }}AztecDetails.html)	
- [`Contour`]({{ site.dbr_structs }}Contour.html)	
- [`DBRPoint`]({{ site.dbr_structs }}DBRPoint.html)	
- [`DataMatrixDetails`]({{ site.dbr_structs }}DataMatrixDetails.html)		
- [`DM_LTSConnectionParameters`]({{ site.dbr_structs }}DMLTSConnectionParameters.html)		
- [`ExtendedResult`]({{ site.dbr_structs }}ExtendedResult.html)		
- [`FrameDecodingParameters`]({{ site.dbr_structs }}FrameDecodingParameters.html)	
- [`FurtherModes`]({{ site.dbr_structs }}FurtherModes.html)		
- [`ImageData`]({{ site.dbr_structs }}ImageData.html)	
- [`IntermediateResult`]({{ site.dbr_structs }}IntermediateResult.html)		
- [`IntermediateResultArray`]({{ site.dbr_structs }}IntermediateResultArray.html)		
- [`LineSegment`]({{ site.dbr_structs }}LineSegment.html)		
- [`LocalizationResult`]({{ site.dbr_structs }}LocalizationResult.html)		
- [`OneDCodeDetails`]({{ site.dbr_structs }}OneDCodeDetails.html)		
- [`PDF417Details`]({{ site.dbr_structs }}PDF417Details.html)		
- [`PublicRuntimeSettings`]({{ site.dbr_structs }}PublicRuntimeSettings.html)		
- [`QRCodeDetails`]({{ site.dbr_structs }}QRCodeDetails.html)
- [`Quadrilateral`]({{ site.dbr_structs }}Quadrilateral.html)
- [`RegionDefinition`]({{ site.dbr_structs }}RegionDefinition.html)		
- [`RegionOfInterest`]({{ site.dbr_structs }}RegionOfInterest.html)		
- [`SamplingImageData`]({{ site.dbr_structs }}SamplingImageData.html)		
- [`TextResult`]({{ site.dbr_structs }}TextResult.html)		
- [`TextResultArray`]({{ site.dbr_structs }}TextResultArray.html)	


 


## [Enumerations]({{ site.dbr_c_cpp_enumerations }})
- [`BarcodeColourMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html?src=c#barcodecolourmode)	
- [`BarcodeComplementMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html?src=c#barcodecomplementmode)	
- [`BarcodeFormat`]({{ site.dbr_c_cpp_enumerations }}format-enums.html?src=c#barcodeformat)	
- [`BarcodeFormat_2`]({{ site.dbr_c_cpp_enumerations }}format-enums.html?src=c#barcodeformat_2)	
- [`BinarizationMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html?src=c#binarizationmode)
- [`ClarityCalculationMethod`]({{ site.dbr_c_cpp_enumerations }}frame-decoding-enums.html?src=c#claritycalculationmethod) 
- [`ClarityFilterMode`]({{ site.dbr_c_cpp_enumerations }}frame-decoding-enums.html?src=c#clarityfiltermode) 
- [`ColourClusteringMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html?src=c#colourclusteringmode)	
- [`ColourConversionMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html?src=c#colourconversionmode)	
- [`ConflictMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html?src=c#conflictmode)	
- [`DeblurMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html?src=c#deblurmode)	
- [`DeformationResistingMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html?src=c#deformationresistingmode)	
- [`DM_ChargeWay`]({{ site.dbr_c_cpp_enumerations }}other-enums.html?src=c#dm_chargeway)	
- [`DM_DeploymentType`]({{ site.dbr_c_cpp_enumerations }}other-enums.html?src=c#dm_deploymenttype)	
- [`DM_LicenseModule`]({{ site.dbr_c_cpp_enumerations }}other-enums.html?src=c#dm_licensemodule)	
- [`DM_UUIDGenerationMethod`]({{ site.dbr_c_cpp_enumerations }}other-enums.html?src=c#dm_uuidgenerationmethod)	
- [`DPMCodeReadingMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html?src=c#dpmcodereadingmode)	
- [`GrayscaleTransformationMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html?src=c#grayscaletransformationmode)	
- [`ImagePixelFormat`]({{ site.dbr_c_cpp_enumerations }}other-enums.html?src=c#imagepixelformat)	
- [`ImagePreprocessingMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html?src=c#imagepreprocessingmode)	
- [`IMResultDataType`]({{ site.dbr_c_cpp_enumerations }}result-enums.html?src=c#imresultdatatype)	
- [`IntermediateResultSavingMode`]({{ site.dbr_c_cpp_enumerations }}result-enums.html?src=c#intermediateresultsavingmode)	
- [`IntermediateResultType`]({{ site.dbr_c_cpp_enumerations }}result-enums.html?src=c#intermediateresulttype)	
- [`LocalizationMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html?src=c#localizationmode)
- [`PDFReadingMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html?src=c#pdfreadingmode)   
- [`QRCodeErrorCorrectionLevel`]({{ site.dbr_c_cpp_enumerations }}other-enums.html?src=c#qrcodeerrorcorrectionlevel)	
- [`RegionPredetectionMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html?src=c#regionpredetectionmode)	
- [`ResultCoordinateType`]({{ site.dbr_c_cpp_enumerations }}result-enums.html?src=c#resultcoordinatetype)	
- [`ResultType`]({{ site.dbr_c_cpp_enumerations }}result-enums.html?src=c#resulttype)	
- [`ScaleUpMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html?src=c#scaleupmode)	
- [`TerminatePhase`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html?src=c#terminatephase)	
- [`TextFilterMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html?src=c#textfiltermode)	
- [`TextResultOrderMode`]({{ site.dbr_c_cpp_enumerations }}result-enums.html?src=c#textresultordermode)	
- [`TextureDetectionMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html?src=c#texturedetectionmode)
