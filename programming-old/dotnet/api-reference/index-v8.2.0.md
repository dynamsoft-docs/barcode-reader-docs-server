---
layout: default-layout
title: Main Page - Dynamsoft Barcode Reader SDK .NET Edition API Reference
description: This is the main page of Dynamsoft Barcode Reader SDK .NET Edition API Reference.
keywords: api reference, .Net
needAutoGenerateSidebar: false
breadcrumbText: API Reference
---

# Dynamsoft Barcode Reader SDK - .Net API Reference

- [`BarcodeReader` Methods](#barcodereader-methods) 
- [`BarcodeReader` Attributes](#barcodereader-attributes) 
- [Function Pointers](#function-pointers)
- [Error Code](#error-code)
- [Structs](#structs)  
- [Classes](#classes)
- [Enumerations](#enumerations)

     
 


## BarcodeReader Methods

### Constructor and Destructor
   
  | Method               | Description |
  |----------------------|-------------|
  | [`BarcodeReader`](BarcodeReader/constructor-and-destructor.md#barcodereader) | Constructor of `BarcodeReader` object.|
  | [`Dispose`](BarcodeReader/constructor-and-destructor.md#dispose) | Destroys an instance of Dynamsoft Barcode Reader. |
   
 
   
   
### Decode
   
  | Method               | Description |
  |----------------------|-------------|
  | [`DecodeFile`](BarcodeReader/decode.md#decodefile) | Decodes barcodes from a specified image file. |
  | [`DecodeFileInMemory`](BarcodeReader/decode.md#decodefileinmemory) | Decode barcodes from an image file in memory. |
  | [`DecodeBuffer`](BarcodeReader/decode.md#decodebuffer) | Decodes barcodes from the memory buffer containing image pixels in defined format. |
  | [`DecodeBase64String`](BarcodeReader/decode.md#decodebase64string) | Decodes barcodes from a base64 encoded string. |
  | [`DecodeBitmap`](BarcodeReader/decode.md#decodebitmap) | Decodes barcode from a bitmap. |
  | [`InitIntermediateResult`](BarcodeReader/decode.md#initintermediateresult) | Inits an intermediateResult struct with default values. |
  | [`DecodeIntermediateResults`](BarcodeReader/decode.md#decodeintermediateresults) | Decodes barcode from intermediate results. |
   
   
 
   
   
   
### Parameter and Runtime Settings

#### Basic
   
  | Method               | Description |
  |----------------------|-------------|
  | [`SetModeArgument`](BarcodeReader/parameter-and-runtime-settings-basic.md#setmodeargument) | Sets the optional argument for a specified mode in Modes parameters. |
  | [`GetModeArgument`](BarcodeReader/parameter-and-runtime-settings-basic.md#getmodeargument) | Gets the optional argument for a specified mode in Modes parameters.  |
  | [`GetRuntimeSettings`](BarcodeReader/parameter-and-runtime-settings-basic.md#getruntimesettings) | Gets current runtime settings. |
  | [`UpdateRuntimeSettings`](BarcodeReader/parameter-and-runtime-settings-basic.md#updateruntimesettings) | Update runtime settings with a given struct. |
  | [`ResetRuntimeSettings`](BarcodeReader/parameter-and-runtime-settings-basic.md#resetruntimesettings) | Resets all parameters to default values. |

#### Advanced
  
  | Method               | Description |
  |----------------------|-------------|
  | [`InitRuntimeSettingsWithFile`](BarcodeReader/parameter-and-runtime-settings-advanced.md#initruntimesettingswithfile)  | Initializes runtime settings with the settings in a given JSON file. |
  | [`InitRuntimeSettingsWithString`](BarcodeReader/parameter-and-runtime-settings-advanced.md#initruntimesettingswithstring) | Initializes runtime settings with the settings in a given JSON string. |
  | [`AppendTplFileToRuntimeSettings`](BarcodeReader/parameter-and-runtime-settings-advanced.md#appendtplfiletoruntimesettings) | Appends a new template file to the current runtime settings. |
  | [`AppendTplStringToRuntimeSettings`](BarcodeReader/parameter-and-runtime-settings-advanced.md#appendtplstringtoruntimesettings) | Appends a new template string to the current runtime settings. |
  | [`GetAllParameterTemplateNames`](BarcodeReader/parameter-and-runtime-settings-advanced.md#getallparametertemplatenames) | Gets the parameter templates name array. |
  | [`OutputSettingsToFile`](BarcodeReader/parameter-and-runtime-settings-advanced.md#outputsettingstofile) | Outputs runtime settings to a settings file (JSON file). |
  | [`OutputSettingsToString`](BarcodeReader/parameter-and-runtime-settings-advanced.md#outputsettingstostring) | Outputs runtime settings to a string. |
   
      
 

   
### License
  
  | Method               | Description |
  |----------------------|-------------|
  | [`InitLicenseFromServer`](BarcodeReader/license.md#initlicensefromserver) | Initializes license and connect to the specified server for online verification. |
  | [`InitLicenseFromLicenseContent`](BarcodeReader/license.md#initlicensefromlicensecontent) | Initializes license from the license content on client machine for offline verification. |
  | [`OutputLicenseToString`](BarcodeReader/license.md#outputlicensetostring) | Outputs the license content as an encrypted string from the license server to be used for offline license verification.|
  | [`InitLTSConnectionParameters`](BarcodeReader/license.md#initltsconnectionparameters) | Initializes a DMLTSConnectionParameters struct with default values. |
  | [`InitLicenseFromLTS`](BarcodeReader/license.md#initlicensefromlts) | Initializes the barcode reader license and connects to the specified server for online verification. |
   
   
 
   
   
### General
   
  | Method               | Description |
  |----------------------|-------------|
  | [`GetVersion`](BarcodeReader/general.md#getversion) | Gets version information of SDK. |
   
      
 

   
### Video

#### Decode
    
   | Method               | Description |
   |----------------------|-------------|
   | [`StartFrameDecoding`](BarcodeReader/video.md#startframedecoding) | Starts a new thread to decode barcodes from the inner frame queue. |
   | [`StartFrameDecodingEx`](BarcodeReader/video.md#startframedecodingex) | Starts a new thread to decode barcodes from the inner frame queue. |
   | [`AppendFrame`](BarcodeReader/video.md#appendframe) | Appends a frame image buffer to the inner frame queue. |
   | [`StopFrameDecoding`](BarcodeReader/video.md#stopframedecoding) | Stops the frame decoding thread created by StartFrameDecoding. |

#### Parameter
   
   | Method               | Description |
   |----------------------|-------------|
   | [`InitFrameDecodingParameters`](BarcodeReader/video.md#initframedecodingparameters) | Initializes frame decoding parameters. |


#### Callback

   | Method               | Description |
   |----------------------|-------------|
   | [`SetErrorCallback`](BarcodeReader/video.md#seterrorcallback) | Set callback function to process errors which is triggered when the library finishes decoding a frame. |
   | [`SetTextResultCallback`](BarcodeReader/video.md#settextresultcallback) | Set callback function to process text results which is triggered when the library finishes decoding a frame. |
   | [`SetIntermediateResultCallback`](BarcodeReader/video.md#setintermediateresultcallback) | Set callback function to process intermediate results which is triggered when the library finishes decoding a frame. |

#### Status retrieval
   
   | Method               | Description |
   |----------------------|-------------|
   | [`GetLengthOfFrameQueue`](BarcodeReader/video.md#getlengthofframequeue) | Gets length of current inner frame queue. |
 
   
 


### Result

   | Method               | Description |
   |----------------------|-------------|
   | [`GetIntermediateResults`](BarcodeReader/result.md#getintermediateresults) | Returns intermediate results containing the original image, the colour clustered image, the binarized Image, contours, Lines, TextBlocks, etc.  |


 


## `BarcodeReader` Attributes
  
  | Attribute            | Description |
  |----------------------|-------------|
  | `ProductKeys`  | Product keys used for Dynamsoft Barcode Reader. |
  
   
 


## Function Pointers

  | Function | Description |
  |----------|-------------|
  | [`CB_Error`](function-pointer.md#cb_error) | Represents the method that will handle the error code returned by the SDK. |
  | [`CB_IntermediateResult`](function-pointer.md#cb_intermediateresult) | Represents the method that will handle the intermediate result array returned by the SDK. |
  | [`CB_TextResult`](function-pointer.md#cb_textresult) | Represents the method that will handle the text result array returned by the SDK. | 





## [Error Code]({{ site.dotnet_enumerations }}error-code.html)
		




## Structs

- [`FurtherModes`](struct/FurtherModes.md)		
- [`PublicRuntimeSettings`](struct/PublicRuntimeSettings.md)		
- [`RegionDefinition`](struct/RegionDefinition.md)		


 


## Classes
- [`AztecDetails`](class/AztecDetails.md)	 
- [`BarcodeReaderException`](class/BarcodeReaderException.md)	
- [`Contour`](class/Contour.md)	 
- [`DMLTSConnectionParameters`](class/DMLTSConnectionParameters.md)		
- [`DataMatrixDetails`](class/DataMatrixDetails.md)	 
- [`ExtendedResult`](class/ExtendedResult.md)	
- [`FrameDecodingParameters`](class/FrameDecodingParameters.md)	
- [`ImageData`](class/ImageData.md)	 
- [`IntermediateResult`](class/IntermediateResult.md)	
- [`LineSegment`](class/LineSegment.md)	 
- [`LocalizationResult`](class/LocalizationResult.md)	
- [`OneDCodeDetails`](class/OneDCodeDetails.md)	
- [`PDF417Details`](class/PDF417Details.md)	
- [`QRCodeDetails`](class/QRCodeDetails.md)	
- [`Quadrilateral`](class/Quadrilateral.md)	 
- [`RegionOfInterest`](class/RegionOfInterest.md)	 
- [`SamplingImageData`](class/SamplingImageData.md)	 
- [`TextResult`](class/TextResult.md)	



## Enumerations
- [`AccompanyingTextRecognitionMode`]({{ site.dotnet_enumerations }}parameter-mode-enums.html#accompanyingtextrecognitionmode)	
- [`BarcodeColourMode`]({{ site.dotnet_enumerations }}parameter-mode-enums.html#barcodecolourmode)	
- [`BarcodeComplementMode`]({{ site.dotnet_enumerations }}parameter-mode-enums.html#barcodecomplementmode)	
- [`BarcodeFormat`]({{ site.dotnet_enumerations }}format-enums.html#barcodeformat)	
- [`BarcodeFormat_2`]({{ site.dotnet_enumerations }}format-enums.html#barcodeformat_2)	
- [`BinarizationMode`]({{ site.dotnet_enumerations }}parameter-mode-enums.html#binarizationmode)
- [`ClarityCalculationMethod`]({{ site.dotnet_enumerations }}frame-decoding-enums.html#claritycalculationmethod) 
- [`ClarityFilterMode`]({{ site.dotnet_enumerations }}frame-decoding-enums.html#clarityfiltermode) 
- [`ColourClusteringMode`]({{ site.dotnet_enumerations }}parameter-mode-enums.html#colourclusteringmode)	
- [`ColourConversionMode`]({{ site.dotnet_enumerations }}parameter-mode-enums.html#colourconversionmode)	
- [`ConflictMode`]({{ site.dotnet_enumerations }}parameter-mode-enums.html#conflictmode)	
- [`DeblurMode`]({{ site.dotnet_enumerations }}parameter-mode-enums.html#deblurmode)
- [`DeformationResistingMode`]({{ site.dotnet_enumerations }}parameter-mode-enums.html#deformationresistingmode)
- [`DM_ChargeWay`]({{ site.dotnet_enumerations }}other-enums.html#dm_chargeway)
- [`DM_DeploymentType`]({{ site.dotnet_enumerations }}other-enums.html#dm_deploymenttype)
- [`DM_LicenseModule`]({{ site.dotnet_enumerations }}other-enums.html#dm_licensemodule)
- [`DM_UUIDGenerationMethod`]({{ site.dotnet_enumerations }}other-enums.html#dm_uuidgenerationmethod)
- [`DPMCodeReadingMode`]({{ site.dotnet_enumerations }}parameter-mode-enums.html#dpmcodereadingmode)
- [`GrayscaleTransformationMode`]({{ site.dotnet_enumerations }}parameter-mode-enums.html#grayscaletransformationmode)	
- [`ImagePixelFormat`]({{ site.dotnet_enumerations }}other-enums.html#imagepixelformat)	
- [`ImagePreprocessingMode`]({{ site.dotnet_enumerations }}parameter-mode-enums.html#imagepreprocessingmode)	
- [`IMResultDataType`]({{ site.dotnet_enumerations }}result-enums.html#imresultdatatype)	
- [`IntermediateResultSavingMode`]({{ site.dotnet_enumerations }}result-enums.html#intermediateresultsavingmode)	
- [`IntermediateResultType`]({{ site.dotnet_enumerations }}result-enums.html#intermediateresulttype)	
- [`LocalizationMode`]({{ site.dotnet_enumerations }}parameter-mode-enums.html#localizationmode)
- [`PDFReadingMode`]({{ site.dotnet_enumerations }}parameter-mode-enums.html#pdfreadingmode)   
- [`QRCodeErrorCorrectionLevel`]({{ site.dotnet_enumerations }}other-enums.html#qrcodeerrorcorrectionlevel)	
- [`RegionPredetectionMode`]({{ site.dotnet_enumerations }}parameter-mode-enums.html#regionpredetectionmode)	
- [`ResultCoordinateType`]({{ site.dotnet_enumerations }}result-enums.html#resultcoordinatetype)	
- [`ResultType`]({{ site.dotnet_enumerations }}result-enums.html#resulttype)	
- [`ScaleUpMode`]({{ site.dotnet_enumerations }}parameter-mode-enums.html#scaleupmode)	
- [`TerminatePhase`]({{ site.dotnet_enumerations }}parameter-mode-enums.html#terminatephase)	
- [`TextFilterMode`]({{ site.dotnet_enumerations }}parameter-mode-enums.html#textfiltermode)	
- [`TextResultOrderMode`]({{ site.dotnet_enumerations }}result-enums.html#textresultordermode)	
- [`TextureDetectionMode`]({{ site.dotnet_enumerations }}parameter-mode-enums.html#texturedetectionmode)
