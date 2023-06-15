---
layout: default-layout
title: Main Page - Dynamsoft Barcode Reader SDK C++ Edition API Reference
description: This is the main page of Dynamsoft Barcode Reader SDK C++ Edition API Reference.
keywords: api reference, c++
needAutoGenerateSidebar: false
breadcrumbText: API Reference
permalink: /programming/cplusplus/api-reference/index-v7.6.0.html
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




## [Error Code]({{ site.c_cpp_enumerations }}error-code.html)
		



## [Structs]({{ site.structs }})
- [`AztecDetails`]({{ site.structs }}AztecDetails.html)	
- [`Contour`]({{ site.structs }}Contour.html)	
- [`DBRPoint`]({{ site.structs }}DBRPoint.html)	
- [`DataMatrixDetails`]({{ site.structs }}DataMatrixDetails.html)		
- [`ExtendedResult`]({{ site.structs }}ExtendedResult.html)		
- [`FrameDecodingParameters`]({{ site.structs }}FrameDecodingParameters.html)	
- [`FurtherModes`]({{ site.structs }}FurtherModes.html)		
- [`ImageData`]({{ site.structs }}ImageData.html)		
- [`IntermediateResult`]({{ site.structs }}IntermediateResult.html)		
- [`IntermediateResultArray`]({{ site.structs }}IntermediateResultArray.html)		
- [`LineSegment`]({{ site.structs }}LineSegment.html)		
- [`LocalizationResult`]({{ site.structs }}LocalizationResult.html)		
- [`OneDCodeDetails`]({{ site.structs }}OneDCodeDetails.html)		
- [`PDF417Details`]({{ site.structs }}PDF417Details.html)		
- [`PublicRuntimeSettings`]({{ site.structs }}PublicRuntimeSettings.html)		
- [`QRCodeDetails`]({{ site.structs }}QRCodeDetails.html)
- [`Quadrilateral`]({{ site.structs }}Quadrilateral.html)
- [`RegionDefinition`]({{ site.structs }}RegionDefinition.html)		
- [`RegionOfInterest`]({{ site.structs }}RegionOfInterest.html)		
- [`SamplingImageData`]({{ site.structs }}SamplingImageData.html)		
- [`TextResult`]({{ site.structs }}TextResult.html)		
- [`TextResultArray`]({{ site.structs }}TextResultArray.html)	


 


## [Enumerations]({{ site.c_cpp_enumerations }})
- [`AccompanyingTextRecognitionMode`]({{ site.c_cpp_enumerations }}parameter-mode-enums.html?src=cpp#accompanyingtextrecognitionmode)	
- [`BarcodeColourMode`]({{ site.c_cpp_enumerations }}parameter-mode-enums.html?src=cpp#barcodecolourmode)	
- [`BarcodeComplementMode`]({{ site.c_cpp_enumerations }}parameter-mode-enums.html?src=cpp#barcodecomplementmode)	
- [`BarcodeFormat`]({{ site.c_cpp_enumerations }}format-enums.html?src=cpp#barcodeformat)	
- [`BarcodeFormat_2`]({{ site.c_cpp_enumerations }}format-enums.html?src=cpp#barcodeformat_2)	
- [`BinarizationMode`]({{ site.c_cpp_enumerations }}parameter-mode-enums.html?src=cpp#binarizationmode)
- [`ClarityCalculationMethod`]({{ site.c_cpp_enumerations }}frame-decoding-enums.html?src=cpp#claritycalculationmethod) 
- [`ClarityFilterMode`]({{ site.c_cpp_enumerations }}frame-decoding-enums.html?src=cpp#clarityfiltermode) 
- [`ColourClusteringMode`]({{ site.c_cpp_enumerations }}parameter-mode-enums.html?src=cpp#colourclusteringmode)	
- [`ColourConversionMode`]({{ site.c_cpp_enumerations }}parameter-mode-enums.html?src=cpp#colourconversionmode)	
- [`ConflictMode`]({{ site.c_cpp_enumerations }}parameter-mode-enums.html?src=cpp#conflictmode)	
- [`DeformationResistingMode`]({{ site.c_cpp_enumerations }}parameter-mode-enums.html?src=cpp#deformationresistingmode)	
- [`DPMCodeReadingMode`]({{ site.c_cpp_enumerations }}parameter-mode-enums.html?src=cpp#dpmcodereadingmode)	
- [`GrayscaleTransformationMode`]({{ site.c_cpp_enumerations }}parameter-mode-enums.html?src=cpp#grayscaletransformationmode)	
- [`ImagePixelFormat`]({{ site.c_cpp_enumerations }}other-enums.html?src=cpp#imagepixelformat)	
- [`ImagePreprocessingMode`]({{ site.c_cpp_enumerations }}parameter-mode-enums.html?src=cpp#imagepreprocessingmode)	
- [`IMResultDataType`]({{ site.c_cpp_enumerations }}result-enums.html?src=cpp#imresultdatatype)	
- [`IntermediateResultSavingMode`]({{ site.c_cpp_enumerations }}result-enums.html?src=cpp#intermediateresultsavingmode)	
- [`IntermediateResultType`]({{ site.c_cpp_enumerations }}result-enums.html?src=cpp#intermediateresulttype)	
- [`LocalizationMode`]({{ site.c_cpp_enumerations }}parameter-mode-enums.html?src=cpp#localizationmode)
- [`PDFReadingMode`]({{ site.c_cpp_enumerations }}parameter-mode-enums.html?src=cpp#pdfreadingmode)   
- [`QRCodeErrorCorrectionLevel`]({{ site.c_cpp_enumerations }}other-enums.html?src=cpp#qrcodeerrorcorrectionlevel)	
- [`RegionPredetectionMode`]({{ site.c_cpp_enumerations }}parameter-mode-enums.html?src=cpp#regionpredetectionmode)	
- [`ResultCoordinateType`]({{ site.c_cpp_enumerations }}result-enums.html?src=cpp#resultcoordinatetype)	
- [`ResultType`]({{ site.c_cpp_enumerations }}result-enums.html?src=cpp#resulttype)	
- [`ScaleUpMode`]({{ site.c_cpp_enumerations }}parameter-mode-enums.html?src=cpp#scaleupmode)	
- [`TerminatePhase`]({{ site.c_cpp_enumerations }}parameter-mode-enums.html?src=cpp#terminatephase)	
- [`TextAssistedCorrectionMode`]({{ site.c_cpp_enumerations }}parameter-mode-enums.html?src=cpp#textassistedcorrectionmode)	
- [`TextFilterMode`]({{ site.c_cpp_enumerations }}parameter-mode-enums.html?src=cpp#textfiltermode)	
- [`TextResultOrderMode`]({{ site.c_cpp_enumerations }}result-enums.html?src=cpp#textresultordermode)	
- [`TextureDetectionMode`]({{ site.c_cpp_enumerations }}parameter-mode-enums.html?src=cpp#texturedetectionmode)
