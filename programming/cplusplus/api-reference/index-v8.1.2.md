---
layout: default-layout
title: Main Page - Dynamsoft Barcode Reader SDK C++ Edition API Reference
description: This is the main page of Dynamsoft Barcode Reader SDK C++ Edition API Reference.
keywords: api reference, c++
needAutoGenerateSidebar: false
breadcrumbText: API Reference
permalink: /programming/cplusplus/api-reference/index-v8.1.2.html
---

# Dynamsoft Barcode Reader SDK - C++ API Reference

- [`CBarcodeReader` Methods](#cbarcodereader-methods) 
- [`CBarcodeReader` Attributes](#cbarcodereader-protected-attribute) 
- [Function Pointer](#function-pointer)
- [Error Code](#error-code)
- [Structs](#structs)  
- [Enumerations](#enumerations)

     
 


## CBarcodeReader Methods

### Constructor and Destructor
   
  | Method               | Description |
  |----------------------|-------------|
  | [`CBarcodeReader`](cbarcodereader-methods/constructor-and-destructor.md#cbarcodereader) | Default constructor of `CBarcodeReader` object.|
  | [`~CBarcodeReader`](cbarcodereader-methods/constructor-and-destructor.md#~cbarcodereader) | Destructor of `CBarcodeReader` object.|
   
   
 
   
   
### Decode
   
  | Method               | Description |
  |----------------------|-------------|
  | [`DecodeFile`](cbarcodereader-methods/decode.md#decodefile) | Decode barcodes from a specified image file. |
  | [`DecodeFileInMemory`](cbarcodereader-methods/decode.md#decodefileinmemory) | Decode barcodes from an image file in memory. |
  | [`DecodeBuffer`](cbarcodereader-methods/decode.md#decodebuffer) | Decode barcodes from raw buffer. |
  | [`DecodeBase64String`](cbarcodereader-methods/decode.md#decodebase64string) | Decode barcodes from a base64 encoded string. |
  | [`DecodeDIB`](cbarcodereader-methods/decode.md#decodedib) | Decode barcode from a handle of device-independent bitmap (DIB). |
  | [`InitIntermediateResult`](cbarcodereader-methods/decode.md#initintermediateresult) | Inits an intermediateResult struct with default values. |
  | [`DecodeIntermediateResults`](cbarcodereader-methods/decode.md#decodeintermediateresults) | Decodes barcode from intermediate results. |
   
   
 
   
   
   
### Parameter and Runtime Settings

#### Basic
   
  | Method               | Description |
  |----------------------|-------------|
  | [`SetModeArgument`](cbarcodereader-methods/parameter-and-runtime-settings-basic.md#setmodeargument) | Set argument value for the specified mode parameter. |
  | [`GetModeArgument`](cbarcodereader-methods/parameter-and-runtime-settings-basic.md#getmodeargument) | Get argument value for the specified mode parameter. |
  | [`GetRuntimeSettings`](cbarcodereader-methods/parameter-and-runtime-settings-basic.md#getruntimesettings) | Get current runtime settings. |
  | [`UpdateRuntimeSettings`](cbarcodereader-methods/parameter-and-runtime-settings-basic.md#updateruntimesettings) | Modify and update the current runtime settings. |
  | [`ResetRuntimeSettings`](cbarcodereader-methods/parameter-and-runtime-settings-basic.md#resetruntimesettings) | Reset runtime settings to default. |

#### Advanced
  
  | Method               | Description |
  |----------------------|-------------|
  | [`InitRuntimeSettingsWithFile`](cbarcodereader-methods/parameter-and-runtime-settings-advanced.md#initruntimesettingswithfile)  | Initialize runtime settings with the settings in a given JSON file. |
  | [`InitRuntimeSettingsWithString`](cbarcodereader-methods/parameter-and-runtime-settings-advanced.md#initruntimesettingswithstring) | Initialize runtime settings with the settings in a given JSON string. |
  | [`AppendTplFileToRuntimeSettings`](cbarcodereader-methods/parameter-and-runtime-settings-advanced.md#appendtplfiletoruntimesettings) | Append a new template file to the current runtime settings. |
  | [`AppendTplStringToRuntimeSettings`](cbarcodereader-methods/parameter-and-runtime-settings-advanced.md#appendtplstringtoruntimesettings) | Append a new template string to the current runtime settings. |
  | [`GetParameterTemplateCount`](cbarcodereader-methods/parameter-and-runtime-settings-advanced.md#getparametertemplatecount) | Get the count of the parameter templates. |
  | [`GetParameterTemplateName`](cbarcodereader-methods/parameter-and-runtime-settings-advanced.md#getparametertemplatename) | Get the parameter template name by index. |
  | [`OutputSettingsToFile`](cbarcodereader-methods/parameter-and-runtime-settings-advanced.md#outputsettingstofile) | Output runtime settings to a settings file (JSON file). |
  | [`OutputSettingsToString`](cbarcodereader-methods/parameter-and-runtime-settings-advanced.md#outputsettingstostring) | Output runtime settings to a string. |
  | [`OutputSettingsToStringPtr`](cbarcodereader-methods/parameter-and-runtime-settings-advanced.md#outputsettingstostringptr) | Output runtime settings to a string. |
  | [`FreeSettingsString`](cbarcodereader-methods/parameter-and-runtime-settings-advanced.md#freesettingsstring) | Free memory allocated for runtime settings string. |
   
      
 

   
### License
  
  | Method               | Description |
  |----------------------|-------------|
  | [`InitLicense`](cbarcodereader-methods/license.md#initlicense) | Read product key and activate the SDK. |
  | [`InitLicenseFromServer`](cbarcodereader-methods/license.md#initlicensefromserver) | Initialize license and connect to the specified server for online verification. |
  | [`InitLicenseFromLicenseContent`](cbarcodereader-methods/license.md#initlicensefromlicensecontent) | Initialize license from the license content on client machine for offline verification. |
  | [`OutputLicenseToString`](cbarcodereader-methods/license.md#outputlicensetostring) | Output the license content to a string from the license server. |
  | [`OutputLicenseToStringPtr`](cbarcodereader-methods/license.md#outputlicensetostringptr) | Output the license content to a string from the license server. |
  | [`FreeLicenseString`](cbarcodereader-methods/license.md#freelicensestring) | Free memory allocated for the license string. |
  | [`InitLTSConnectionParameters`](cbarcodereader-methods/license.md#initltsconnectionparameters) | Initializes a DM_LTSConnectionParameters struct with default values. |
  | [`InitLicenseFromLTS`](cbarcodereader-methods/license.md#initlicensefromlts) | Initializes the barcode reader license and connects to the specified server for online verification. |
   
   
 
   
   
### Result
   
  | Method               | Description |
  |----------------------|-------------|
  | [`GetAllTextResults`](cbarcodereader-methods/result.md#getalltextresults) | Get all recognized barcode results. |
  | [`FreeTextResults`](cbarcodereader-methods/result.md#freetextresults) | Free memory allocated for text results. |
  | [`GetIntermediateResults`](cbarcodereader-methods/result.md#getintermediateresults) | Get intermediate results. |
  | [`FreeIntermediateResults`](cbarcodereader-methods/result.md#freeintermediateresults) | Free memory allocated for the intermediate results. |
   
      
 

   
### General
   
  | Method               | Description |
  |----------------------|-------------|
  | [`GetErrorString`](cbarcodereader-methods/general.md#geterrorstring) | Get error message by error code.|
  | [`GetVersion`](cbarcodereader-methods/general.md#getversion) | Get version information of SDK.|
   
      
 

   
### Video

#### Decode
    
   | Method               | Description |
   |----------------------|-------------|
   | [`StartFrameDecoding`](cbarcodereader-methods/video.md#startframedecoding) | Decode barcodes from inner frame queue. |
   | [`StartFrameDecodingEx`](cbarcodereader-methods/video.md#startframedecodingex) | Decode barcodes from inner frame queue. |
   | [`AppendFrame`](cbarcodereader-methods/video.md#appendframe) | Append a frame image buffer to the inner frame queue. |
   | [`StopFrameDecoding`](cbarcodereader-methods/video.md#stopframedecoding) | Stop thread used for frame decoding. |

#### Parameter
   
   | Method               | Description |
   |----------------------|-------------|
   | [`InitFrameDecodingParameters`](cbarcodereader-methods/video.md#initframedecodingparameters) | Initialize frame decoding parameter. |

#### Callback
   
   | Method               | Description |
   |----------------------|-------------|
   | [`SetErrorCallback`](cbarcodereader-methods/video.md#seterrorcallback) | Set callback function to process errors which is triggered when the library finishes decoding a frame. |
   | [`SetTextResultCallback`](cbarcodereader-methods/video.md#settextresultcallback) | Set callback function to process text results which is triggered when the library finishes decoding a frame. |
   | [`SetIntermediateResultCallback`](cbarcodereader-methods/video.md#setintermediateresultcallback) | Set callback function to process intermediate results which is triggered when the library finishes decoding a frame. |

#### Status retrieval
   
   | Method               | Description |
   |----------------------|-------------|
   | [`GetLengthOfFrameQueue`](cbarcodereader-methods/video.md#getlengthofframequeue) | Get length of current inner frame queue. |
 
   
 


## `CBarcodeReader` Protected Attribute
  
  | Attribute            | Description |
  |----------------------|-------------|
  | [`m_pBarcodeReader`]()  | |
  
   
 

## Function Pointer

  | Function | Description |
  |----------|-------------|
  | [`CB_Error`](function-pointer.md#cb_error) | Represents the method that will handle the error code returned by the SDK. |
  | [`CB_IntermediateResult`](function-pointer.md#cb_intermediateresult) | Represents the method that will handle the intermediate result array returned by the SDK. |
  | [`CB_TextResult`](function-pointer.md#cb_textresult) | Represents the method that will handle the text result array returned by the SDK. | 




## [Error Code]({{ site.dbr_c_cpp_enumerations }}error-code.html?src=cpp)
		



## [Structs]({{ site.dbr_structs }}?src=cpp)
- [`AztecDetails`]({{ site.dbr_structs }}AztecDetails.html?src=cpp)
- [`Contour`]({{ site.dbr_structs }}Contour.html?src=cpp)
- [`DBRPoint`]({{ site.dbr_structs }}DBRPoint.html?src=cpp)
- [`DataMatrixDetails`]({{ site.dbr_structs }}DataMatrixDetails.html?src=cpp)	
- [`DM_LTSConnectionParameters`]({{ site.dbr_structs }}DMLTSConnectionParameters.html?src=cpp)	
- [`ExtendedResult`]({{ site.dbr_structs }}ExtendedResult.html?src=cpp)	
- [`FrameDecodingParameters`]({{ site.dbr_structs }}FrameDecodingParameters.html?src=cpp)
- [`FurtherModes`]({{ site.dbr_structs }}FurtherModes.html?src=cpp)	
- [`ImageData`]({{ site.dbr_structs }}ImageData.html?src=cpp)	
- [`IntermediateResult`]({{ site.dbr_structs }}IntermediateResult.html?src=cpp)	
- [`IntermediateResultArray`]({{ site.dbr_structs }}IntermediateResultArray.html?src=cpp)	
- [`LineSegment`]({{ site.dbr_structs }}LineSegment.html?src=cpp)	
- [`LocalizationResult`]({{ site.dbr_structs }}LocalizationResult.html?src=cpp)	
- [`OneDCodeDetails`]({{ site.dbr_structs }}OneDCodeDetails.html?src=cpp)	
- [`PDF417Details`]({{ site.dbr_structs }}PDF417Details.html?src=cpp)	
- [`PublicRuntimeSettings`]({{ site.dbr_structs }}PublicRuntimeSettings.html?src=cpp)	
- [`QRCodeDetails`]({{ site.dbr_structs }}QRCodeDetails.html?src=cpp)
- [`Quadrilateral`]({{ site.dbr_structs }}Quadrilateral.html?src=cpp)
- [`RegionDefinition`]({{ site.dbr_structs }}RegionDefinition.html?src=cpp)	
- [`RegionOfInterest`]({{ site.dbr_structs }}RegionOfInterest.html?src=cpp)	
- [`SamplingImageData`]({{ site.dbr_structs }}SamplingImageData.html?src=cpp)	
- [`TextResult`]({{ site.dbr_structs }}TextResult.html?src=cpp)	
- [`TextResultArray`]({{ site.dbr_structs }}TextResultArray.html?src=cpp)


 


## [Enumerations]({{ site.dbr_c_cpp_enumerations }}?src=cpp)
- [`AccompanyingTextRecognitionMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html?src=cpp#accompanyingtextrecognitionmode)	
- [`BarcodeColourMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html?src=cpp#barcodecolourmode)	
- [`BarcodeComplementMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html?src=cpp#barcodecomplementmode)	
- [`BarcodeFormat`]({{ site.dbr_c_cpp_enumerations }}format-enums.html?src=cpp#barcodeformat)	
- [`BarcodeFormat_2`]({{ site.dbr_c_cpp_enumerations }}format-enums.html?src=cpp#barcodeformat_2)	
- [`BinarizationMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html?src=cpp#binarizationmode)
- [`ClarityCalculationMethod`]({{ site.dbr_c_cpp_enumerations }}frame-decoding-enums.html?src=cpp#claritycalculationmethod) 
- [`ClarityFilterMode`]({{ site.dbr_c_cpp_enumerations }}frame-decoding-enums.html?src=cpp#clarityfiltermode) 
- [`ColourClusteringMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html?src=cpp#colourclusteringmode)	
- [`ColourConversionMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html?src=cpp#colourconversionmode)	
- [`ConflictMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html?src=cpp#conflictmode)	
- [`DeblurMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html?src=cpp#deblurmode)	
- [`DeformationResistingMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html?src=cpp#deformationresistingmode)	
- [`DM_ChargeWay`]({{ site.dbr_c_cpp_enumerations }}other-enums.html?src=cpp#dm_chargeway)	
- [`DM_DeploymentType`]({{ site.dbr_c_cpp_enumerations }}other-enums.html?src=cpp#dm_deploymenttype)	
- [`DM_LicenseModule`]({{ site.dbr_c_cpp_enumerations }}other-enums.html?src=cpp#dm_licensemodule)	
- [`DM_UUIDGenerationMethod`]({{ site.dbr_c_cpp_enumerations }}other-enums.html?src=cpp#dm_uuidgenerationmethod)	
- [`DPMCodeReadingMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html?src=cpp#dpmcodereadingmode)	
- [`GrayscaleTransformationMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html?src=cpp#grayscaletransformationmode)	
- [`ImagePixelFormat`]({{ site.dbr_c_cpp_enumerations }}other-enums.html?src=cpp#imagepixelformat)	
- [`ImagePreprocessingMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html?src=cpp#imagepreprocessingmode)	
- [`IMResultDataType`]({{ site.dbr_c_cpp_enumerations }}result-enums.html?src=cpp#imresultdatatype)	
- [`IntermediateResultSavingMode`]({{ site.dbr_c_cpp_enumerations }}result-enums.html?src=cpp#intermediateresultsavingmode)	
- [`IntermediateResultType`]({{ site.dbr_c_cpp_enumerations }}result-enums.html?src=cpp#intermediateresulttype)	
- [`LocalizationMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html?src=cpp#localizationmode)
- [`PDFReadingMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html?src=cpp#pdfreadingmode)   
- [`QRCodeErrorCorrectionLevel`]({{ site.dbr_c_cpp_enumerations }}other-enums.html?src=cpp#qrcodeerrorcorrectionlevel)	
- [`RegionPredetectionMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html?src=cpp#regionpredetectionmode)	
- [`ResultCoordinateType`]({{ site.dbr_c_cpp_enumerations }}result-enums.html?src=cpp#resultcoordinatetype)	
- [`ResultType`]({{ site.dbr_c_cpp_enumerations }}result-enums.html?src=cpp#resulttype)	
- [`ScaleUpMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html?src=cpp#scaleupmode)	
- [`TerminatePhase`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html?src=cpp#terminatephase)	
- [`TextAssistedCorrectionMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html?src=cpp#textassistedcorrectionmode)	
- [`TextFilterMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html?src=cpp#textfiltermode)	
- [`TextResultOrderMode`]({{ site.dbr_c_cpp_enumerations }}result-enums.html?src=cpp#textresultordermode)	
- [`TextureDetectionMode`]({{ site.dbr_c_cpp_enumerations }}parameter-mode-enums.html?src=cpp#texturedetectionmode)
