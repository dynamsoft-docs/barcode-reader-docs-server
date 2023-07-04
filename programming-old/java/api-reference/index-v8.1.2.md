---
layout: default-layout
title: Main Page - Dynamsoft Barcode Reader SDK Java Edition API Reference
description: This is the main page of Dynamsoft Barcode Reader SDK Java Edition API Reference.
keywords: api reference, java
needAutoGenerateSidebar: false
breadcrumbText: API Reference
permalink: /programming/java/api-reference/index-v8.1.2.html
---


# Dynamsoft Barcode Reader SDK - Java API Reference

- [`BarcodeReader` Methods](#barcodereader-methods) 
- [Interface](#interface)
- [Error Code](#error-code)
- [Classes](#classes)  
- [Enumerations](#enumerations)

     
 


## BarcodeReader Methods

### Initialize and Destroy
   
  | Method               | Description |
  |----------------------|-------------|
  | [`BarcodeReader`](BarcodeReader/initialize-and-destroy.md#barcodereader) | Initialization of `BarcodeReader` object.|
  | [`destroy`](BarcodeReader/initialize-and-destroy.md#destroy) | Destroys an instance of `BarcodeReader` object.|
   
   
 
   
   
### Decode
   
  | Method               | Description |
  |----------------------|-------------|
  | [`decodeFile`](BarcodeReader/decode.md#decodefile) | Decode barcodes from a specified image file. |
  | [`decodeFileInMemory`](BarcodeReader/decode.md#decodefileinmemory) | Decode barcodes from an image file in memory. |
  | [`decodeBuffer`](BarcodeReader/decode.md#decodebuffer) | Decode barcodes from raw buffer. |
  | [`decodeBase64String`](BarcodeReader/decode.md#decodebase64string) | Decode barcodes from a base64 encoded string. |
  | [`decodeBufferedImage`](BarcodeReader/decode.md#decodebufferedimage) | Decodes barcode from a buffered image (bitmap). |
  | [`initIntermediateResult`](BarcodeReader/decode.md#initintermediateresult) | Inits an intermediateResult struct with default values. |
  | [`decodeIntermediateResults`](BarcodeReader/decode.md#decodeintermediateresults) | Decodes barcode from intermediate results. |
   
   
 
   
   
   
### Parameter and Runtime Settings

#### Basic
   
  | Method               | Description |
  |----------------------|-------------|
  | [`setModeArgument`](BarcodeReader/parameter-and-runtime-settings-basic.md#setmodeargument) | Set argument value for the specified mode parameter. |
  | [`getModeArgument`](BarcodeReader/parameter-and-runtime-settings-basic.md#getmodeargument) | Get argument value for the specified mode parameter. |
  | [`getRuntimeSettings`](BarcodeReader/parameter-and-runtime-settings-basic.md#getruntimesettings) | Get current runtime settings. |
  | [`updateRuntimeSettings`](BarcodeReader/parameter-and-runtime-settings-basic.md#updateruntimesettings) | Modify and update the current runtime settings. |
  | [`resetRuntimeSettings`](BarcodeReader/parameter-and-runtime-settings-basic.md#resetruntimesettings) | Reset runtime settings to default. |

#### Advanced
  
  | Method               | Description |
  |----------------------|-------------|
  | [`initRuntimeSettingsWithFile`](BarcodeReader/parameter-and-runtime-settings-advanced.md#initruntimesettingswithfile)  | Initialize runtime settings with the settings in a given JSON file. |
  | [`initRuntimeSettingsWithString`](BarcodeReader/parameter-and-runtime-settings-advanced.md#initruntimesettingswithstring) | Initialize runtime settings with the settings in a given JSON string. |
  | [`appendTplFileToRuntimeSettings`](BarcodeReader/parameter-and-runtime-settings-advanced.md#appendtplfiletoruntimesettings) | Append a new template file to the current runtime settings. |
  | [`appendTplStringToRuntimeSettings`](BarcodeReader/parameter-and-runtime-settings-advanced.md#appendtplstringtoruntimesettings) | Append a new template string to the current runtime settings. |
  | [`getAllParameterTemplateNames`](BarcodeReader/parameter-and-runtime-settings-advanced.md#getallparametertemplatenames) | Gets the parameter templates name array. |
  | [`outputSettingsToFile`](BarcodeReader/parameter-and-runtime-settings-advanced.md#outputsettingstofile) | Output runtime settings to a settings file (JSON file). |
  | [`outputSettingsToString`](BarcodeReader/parameter-and-runtime-settings-advanced.md#outputsettingstostring) | Output runtime settings to a string. |
   
      
 

   
### License
  
  | Method               | Description |
  |----------------------|-------------|
  | [`initLicense`](BarcodeReader/license.md#initlicense) | Read product key and activate the SDK. |
  | [`initLicenseFromServer`](BarcodeReader/license.md#initlicensefromserver) | Initialize license and connect to the specified server for online verification. |
  | [`initLicenseFromLicenseContent`](BarcodeReader/license.md#initlicensefromlicensecontent) | Initialize license from the license content on client machine for offline verification. |
  | [`outputLicenseToString`](BarcodeReader/license.md#outputlicensetostring) | Output the license content to a string from the license server. |
  | [`initLTSConnectionParameters`](BarcodeReader/license.md#initltsconnectionparameters) | Initializes a DMLTSConnectionParameters struct with default values. |
  | [`initLicenseFromLTS`](BarcodeReader/license.md#initlicensefromlts) | Initializes the barcode reader license and connects to the specified server for online verification. |
   
   
 
   
   
### Result
   
  | Method               | Description |
  |----------------------|-------------|
  | [`getIntermediateResults`](BarcodeReader/result.md#getintermediateresults) | Get intermediate results. |
   
      
 

   
### General
   
  | Method               | Description |
  |----------------------|-------------|
  | [`getVersion`](BarcodeReader/general.md#getversion) | Get version information of SDK.|
   
      
 

   
### Video

#### Decode
    
   | Method               | Description |
   |----------------------|-------------|
   | [`startFrameDecoding`](BarcodeReader/video.md#startframedecoding) | Decode barcodes from inner frame queue. |
   | [`startFrameDecodingEx`](BarcodeReader/video.md#startframedecodingex) | Decode barcodes from inner frame queue. |
   | [`appendFrame`](BarcodeReader/video.md#appendframe) | Append a frame image buffer to the inner frame queue. |
   | [`stopFrameDecoding`](BarcodeReader/video.md#stopframedecoding) | Stop thread used for frame decoding. |

#### Parameter
   
   | Method               | Description |
   |----------------------|-------------|
   | [`initFrameDecodingParameters`](BarcodeReader/video.md#initframedecodingparameters) | Initialize frame decoding parameter. |

#### Callback
   
   | Method               | Description |
   |----------------------|-------------|
   | [`setErrorCallback`](BarcodeReader/video.md#seterrorcallback) | Set callback interface to process errors which is triggered when the library finishes decoding a frame. |
   | [`setTextResultCallback`](BarcodeReader/video.md#settextresultcallback) | Set callback interface to process text results which is triggered when the library finishes decoding a frame. |
   | [`setIntermediateResultCallback`](BarcodeReader/video.md#setintermediateresultcallback) | Set callback interface to process intermediate results which is triggered when the library finishes decoding a frame. |

#### Status retrieval
   
   | Method               | Description |
   |----------------------|-------------|
   | [`getLengthOfFrameQueue`](BarcodeReader/video.md#getlengthofframequeue) | Get length of current inner frame queue. |
 
   
  
   
 

## Interface

  | Function | Description |
  |----------|-------------|
  | [`ErrorCallback`](interface.md#errorcallback) | Represents the method that will handle the error code returned by the SDK. |
  | [`IntermediateResultCallback`](interface.md#intermediateresultcallback) | Represents the method that will handle the intermediate result array returned by the SDK. |
  | [`TextResultCallback`](interface.md#cb_textresult) | Represents the method that will handle the text result array returned by the SDK. | 




## [Error Code]({{ site.java_enumerations }}error-code.html)
		



## Classes
- [`AztecDetails`](class/AztecDetails.md)	 
- [`BarcodeReaderException`](class/BarcodeReaderException.md)	
- [`Contour`](class/Contour.md)	 
- [`DMLTSConnectionParameters`](class/DMLTSConnectionParameters.md)		
- [`DataMatrixDetails`](class/DataMatrixDetails.md)	 
- [`ExtendedResult`](class/ExtendedResult.md)	
- [`FrameDecodingParameters`](class/FrameDecodingParameters.md)
- [`FurtherModes`](class/FurtherModes.md)
- [`ImageData`](class/ImageData.md)	 
- [`IntermediateResult`](class/IntermediateResult.md)	
- [`LineSegment`](class/LineSegment.md)	 
- [`LocalizationResult`](class/LocalizationResult.md)	
- [`OneDCodeDetails`](class/OneDCodeDetails.md)	
- [`PDF417Details`](class/PDF417Details.md)	
- [`PublicRuntimeSettings`](class/PublicRuntimeSettings.md)	
- [`QRCodeDetails`](class/QRCodeDetails.md)	
- [`Quadrilateral`](class/Quadrilateral.md)	 
- [`RegionDefinition`](class/RegionDefinition.md)	
- [`RegionOfInterest`](class/RegionOfInterest.md)	 
- [`SamplingImageData`](class/SamplingImageData.md)	 
- [`TextResult`](class/TextResult.md)		


 


## Enumerations
- [`EnumAccompanyingTextRecognitionMode`]({{ site.java_enumerations }}parameter-mode-enums.html#accompanyingtextrecognitionmode)	
- [`EnumBarcodeColourMode`]({{ site.java_enumerations }}parameter-mode-enums.html#barcodecolourmode)	
- [`EnumBarcodeComplementMode`]({{ site.java_enumerations }}parameter-mode-enums.html#barcodecomplementmode)	
- [`EnumBarcodeFormat`]({{ site.java_enumerations }}format-enums.html#barcodeformat)	
- [`EnumBarcodeFormat_2`]({{ site.java_enumerations }}format-enums.html#barcodeformat_2)	
- [`EnumBinarizationMode`]({{ site.java_enumerations }}parameter-mode-enums.html#binarizationmode)
- [`EnumClarityCalculationMethod`]({{ site.java_enumerations }}frame-decoding-enums.html#claritycalculationmethod) 
- [`EnumClarityFilterMode`]({{ site.java_enumerations }}frame-decoding-enums.html#clarityfiltermode) 
- [`EnumColourClusteringMode`]({{ site.java_enumerations }}parameter-mode-enums.html#colourclusteringmode)	
- [`EnumColourConversionMode`]({{ site.java_enumerations }}parameter-mode-enums.html#colourconversionmode)	
- [`EnumConflictMode`]({{ site.java_enumerations }}parameter-mode-enums.html#conflictmode)	
- [`EnumDeblurMode`]({{ site.java_enumerations }}parameter-mode-enums.html#deblurmode)	
- [`EnumDeformationResistingMode`]({{ site.java_enumerations }}parameter-mode-enums.html#deformationresistingmode)	
- [`EnumDMChargeWay`]({{ site.java_enumerations }}other-enums.html#dm_chargeway)	
- [`EnumDMDeploymentType`]({{ site.java_enumerations }}other-enums.html#dm_deploymenttype)	
- [`EnumDMLicenseModule`]({{ site.java_enumerations }}other-enums.html#dm_licensemodule)	
- [`EnumDMUUIDGenerationMethod`]({{ site.java_enumerations }}other-enums.html#dm_uuidgenerationmethod)	
- [`EnumDPMCodeReadingMode`]({{ site.java_enumerations }}parameter-mode-enums.html#dpmcodereadingmode)	
- [`EnumGrayscaleTransformationMode`]({{ site.java_enumerations }}parameter-mode-enums.html#grayscaletransformationmode)	
- [`EnumImagePixelFormat`]({{ site.java_enumerations }}other-enums.html#imagepixelformat)	
- [`EnumImagePreprocessingMode`]({{ site.java_enumerations }}parameter-mode-enums.html#imagepreprocessingmode)	
- [`EnumIMResultDataType`]({{ site.java_enumerations }}result-enums.html#imresultdatatype)	
- [`EnumIntermediateResultSavingMode`]({{ site.java_enumerations }}result-enums.html#intermediateresultsavingmode)	
- [`EnumIntermediateResultType`]({{ site.java_enumerations }}result-enums.html#intermediateresulttype)	
- [`EnumLocalizationMode`]({{ site.java_enumerations }}parameter-mode-enums.html#localizationmode)
- [`EnumPDFReadingMode`]({{ site.java_enumerations }}parameter-mode-enums.html#pdfreadingmode)   
- [`EnumQRCodeErrorCorrectionLevel`]({{ site.java_enumerations }}other-enums.html#qrcodeerrorcorrectionlevel)	
- [`EnumRegionPredetectionMode`]({{ site.java_enumerations }}parameter-mode-enums.html#regionpredetectionmode)	
- [`EnumResultCoordinateType`]({{ site.java_enumerations }}result-enums.html#resultcoordinatetype)	
- [`EnumResultType`]({{ site.java_enumerations }}result-enums.html#resulttype)	
- [`EnumScaleUpMode`]({{ site.java_enumerations }}parameter-mode-enums.html#scaleupmode)	
- [`EnumTerminatePhase`]({{ site.java_enumerations }}parameter-mode-enums.html#terminatephase)	
- [`EnumTextAssistedCorrectionMode`]({{ site.java_enumerations }}parameter-mode-enums.html#textassistedcorrectionmode)	
- [`EnumTextFilterMode`]({{ site.java_enumerations }}parameter-mode-enums.html#textfiltermode)	
- [`EnumTextResultOrderMode`]({{ site.java_enumerations }}result-enums.html#textresultordermode)	
- [`EnumTextureDetectionMode`]({{ site.java_enumerations }}parameter-mode-enums.html#texturedetectionmode)
