---
layout: default-layout
title: Main Page - Dynamsoft Barcode Reader SDK Python Edition API Reference
description: This is the main page of Dynamsoft Barcode Reader SDK Python Edition API Reference.
keywords: api reference, python
needAutoGenerateSidebar: false
breadcrumbText: API Reference
permalink: /programming/python/api-reference/index-v8.2.0.html
---

# Dynamsoft Barcode Reader SDK - Python API Reference

- [`BarcodeReader` Methods](#barcodereader-methods) 
- [`BarcodeReader` Attributes](#barcodereader-attributes) 
- [Error Code](#error-code)
- [Classes](#classes)
- [Enumerations](#enumerations)

     
 


## BarcodeReader Methods

### Constructor and Destructor
   
  | Method               | Description |
  |----------------------|-------------|
  | [`BarcodeReader`](BarcodeReader/constructor-and-destructor.md#barcodereader) | Constructor of `BarcodeReader` object.|

   
 
   
   
### Decode
   
  | Method               | Description |
  |----------------------|-------------|
  | [`decode_file`](BarcodeReader/decode.md#decode_file) | Decodes barcodes from a specified image file. |
  | [`decode_buffer`](BarcodeReader/decode.md#decode_buffer) | Decodes barcodes from the memory buffer containing image pixels in defined format.  |
  | [`decode_file_stream`](BarcodeReader/decode.md#decode_file_stream) | Decodes barcodes from an image file in memory. |
  | [`decode_buffer_manually`](BarcodeReader/decode.md#decode_buffer_manually) | Decodes barcodes from the memory buffer containing image pixels in defined format. |
  | [`init_intermediate_result`](BarcodeReader/decode.md#init_intermediateresult) | Inits an intermediateResult struct with default values. |
  | [`decode_intermediate_results`](BarcodeReader/decode.md#decode_intermediateresults) | Decodes barcode from intermediate results. |
   
   
 
   
   
   
### Parameter and Runtime Settings

#### Basic
   
  | Method               | Description |
  |----------------------|-------------|
  | [`set_mode_argument`](BarcodeReader/parameter-and-runtime-settings-basic.md#set_mode_argument) | Sets the optional argument for a specified mode in Modes parameters. |
  | [`get_mode_argument`](BarcodeReader/parameter-and-runtime-settings-basic.md#get_mode_argument) | Gets the optional argument for a specified mode in Modes parameters.  |
  | [`get_runtime_settings`](BarcodeReader/parameter-and-runtime-settings-basic.md#get_runtime_settings) | Gets current runtime settings. |
  | [`update_runtime_settings`](BarcodeReader/parameter-and-runtime-settings-basic.md#update_runtime_settings) | Update runtime settings with a given struct. |
  | [`reset_runtime_settings`](BarcodeReader/parameter-and-runtime-settings-basic.md#reset_runtime_settings) | Resets all parameters to default values. |

#### Advanced
  
  | Method               | Description |
  |----------------------|-------------|
  | [`init_runtime_settings_with_file`](BarcodeReader/parameter-and-runtime-settings-advanced.md#init_runtime_settings_with_file)  | Initializes runtime settings with the settings in a given JSON file. |
  | [`init_runtime_settings_with_string`](BarcodeReader/parameter-and-runtime-settings-advanced.md#init_runtime_settings_with_string) | Initializes runtime settings with the settings in a given JSON string. |
  | [`append_template_file_to_runtime_settings`](BarcodeReader/parameter-and-runtime-settings-advanced.md#append_template_file_to_runtime_settings) | Appends a new template file to the current runtime settings. |
  | [`append_template_string_to_runtime_settings`](BarcodeReader/parameter-and-runtime-settings-advanced.md#append_template_string_to_runtime_settings) | Appends a new template string to the current runtime settings. |
  | [`get_all_template_names`](BarcodeReader/parameter-and-runtime-settings-advanced.md#get_all_template_names) | Gets the parameter templates name array. |
  | [`output_settings_to_json_file`](BarcodeReader/parameter-and-runtime-settings-advanced.md#output_settings_to_json_file) | Outputs runtime settings to a settings file (JSON file). |
  | [`output_settings_to_json_string`](BarcodeReader/parameter-and-runtime-settings-advanced.md#output_settings_to_json_string) | Outputs runtime settings to a string. |
   
      
 

   
### License
  
  | Method               | Description |
  |----------------------|-------------|
  | [`init_license`](BarcodeReader/license.md#init_license) | Reads product key and activates the SDK.  |
  | [`init_license_from_server`](BarcodeReader/license.md#init_license_from_server) | Initializes license and connect to the specified server for online verification. |
  | [`init_license_from_license_content`](BarcodeReader/license.md#init_license_from_license_content) | Initializes license from the license content on client machine for offline verification. |
  | [`output_license_to_string`](BarcodeReader/license.md#output_license_to_string) | Outputs the license content as an encrypted string from the license server to be used for offline license verification.|
  | [`init_lts_connection_parameters`](BarcodeReader/license.md#init_lts_connection_parameters) | Initializes a DMLTSConnectionParameters struct with default values. |
  | [`init_license_from_lts`](BarcodeReader/license.md#init_license_from_lts) | Initializes the barcode reader license and connects to the specified server for online verification. |
   
   
 
   
   
### Video

#### Decode
    
   | Method               | Description |
   |----------------------|-------------|
   | [`start_video_mode`](BarcodeReader/video.md#start_video_mode) | Starts a new thread to decode barcodes from the inner frame queue. |
   | [`append_video_frame`](BarcodeReader/video.md#append_video_frame) | Appends a frame image buffer to the inner frame queue. |
   | [`stop_video_mode`](BarcodeReader/video.md#stop_video_mode) | Stops the frame decoding thread created by start_video_mode(). |

#### Parameter
   
   | Method               | Description |
   |----------------------|-------------|
   | [`init_frame_decoding_parameters`](BarcodeReader/video.md#init_frame_decoding_parameters) | Initializes frame decoding parameters. |


#### Status retrieval
   
   | Method               | Description |
   |----------------------|-------------|
   | [`get_length_of_frame_queue`](BarcodeReader/video.md#get_length_of_frame_queue) | Gets length of current inner frame queue. |
 
   
 


## `BarcodeReader` Attributes
  
  | Attribute            | Description |
  |----------------------|-------------|
  | `version`  | dbr-python version |
  | `dbr_version`  | Dynamsoft Barcode Reader version |
  
   
 


## [Error Code]({{ site.python_enumerations }}error-code.html)
		




## Classes
- [`AztecDetailedResult`](class/AztecDetailedResult.md)	 
- [`BarcodeReaderError`](class/BarcodeReaderError.md)	
- [`Contour`](class/Contour.md)	 
- [`DataMatrixDetailedResult`](class/DataMatrixDetailedResult.md)	 
- [`ExtendedResult`](class/ExtendedResult.md)	
- [`FrameDecodingParameters`](class/FrameDecodingParameters.md)	
- [`ImageData`](class/ImageData.md)	 
- [`IntermediateResult`](class/IntermediateResult.md)	
- [`LineSegment`](class/LineSegment.md)	 
- [`LocalizationResult`](class/LocalizationResult.md)	
- [`OnedDetailedResult`](class/OnedDetailedResult.md)	
- [`PDFDetailedResult`](class/PDFDetailedResult.md)	
- [`Point`](class/Point.md)		
- [`PublicRuntimeSettings`](class/PublicRuntimeSettings.md)		
- [`QRCodeDetailedResult`](class/QRCodeDetailedResult.md)	
- [`Quadrilateral`](class/Quadrilateral.md)	 
- [`RegionOfInterest`](class/RegionOfInterest.md)	 
- [`SamplingImageData`](class/SamplingImageData.md)	 
- [`TextResult`](class/TextResult.md)	
- [`DMLTSConnectionParameters`](class/DMLTSConnectionParameters.md)
- [`IntermediateResultCallBack`](class/IntermediateResultCallBack.md)
- [`TextResultCallBack`](class/TextResultCallBack.md)
- [`ErrorCallBack`](class/ErrorCallBack.md)
		




## Enumerations
- [`AccompanyingTextRecognitionMode`]({{ site.python_enumerations }}parameter-mode-enums.html#accompanyingtextrecognitionmode)	
- [`BarcodeColourMode`]({{ site.python_enumerations }}parameter-mode-enums.html#barcodecolourmode)	
- [`BarcodeComplementMode`]({{ site.python_enumerations }}parameter-mode-enums.html#barcodecomplementmode)	
- [`BarcodeFormat`]({{ site.python_enumerations }}format-enums.html#barcodeformat)	
- [`BarcodeFormat_2`]({{ site.python_enumerations }}format-enums.html#barcodeformat_2)	
- [`BinarizationMode`]({{ site.python_enumerations }}parameter-mode-enums.html#binarizationmode)
- [`ClarityCalculationMethod`]({{ site.python_enumerations }}frame-decoding-enums.html#claritycalculationmethod) 
- [`ClarityFilterMode`]({{ site.python_enumerations }}frame-decoding-enums.html#clarityfiltermode) 
- [`ColourClusteringMode`]({{ site.python_enumerations }}parameter-mode-enums.html#colourclusteringmode)	
- [`ColourConversionMode`]({{ site.python_enumerations }}parameter-mode-enums.html#colourconversionmode)	
- [`ConflictMode`]({{ site.python_enumerations }}parameter-mode-enums.html#conflictmode)	
- [`DeblurMode`]({{ site.python_enumerations }}parameter-mode-enums.html#deblurmode)
- [`DeformationResistingMode`]({{ site.python_enumerations }}parameter-mode-enums.html#deformationresistingmode)
- [`DMChargeWay`]({{ site.python_enumerations }}other-enums.html#dm_chargeway)
- [`DMDeploymentType`]({{ site.python_enumerations }}other-enums.html#dm_deploymenttype)
- [`DMLicenseModule`]({{ site.python_enumerations }}other-enums.html#dm_licensemodule)
- [`DMUUIDGenerationMethod`]({{ site.python_enumerations }}other-enums.html#dm_uuidgenerationmethod)
- [`DPMCodeReadingMode`]({{ site.python_enumerations }}parameter-mode-enums.html#dpmcodereadingmode)	
- [`GrayscaleTransformationMode`]({{ site.python_enumerations }}parameter-mode-enums.html#grayscaletransformationmode)	
- [`ImagePixelFormat`]({{ site.python_enumerations }}other-enums.html#imagepixelformat)	
- [`ImagePreprocessingMode`]({{ site.python_enumerations }}parameter-mode-enums.html#imagepreprocessingmode)	
- [`IMResultDataType`]({{ site.python_enumerations }}result-enums.html#imresultdatatype)	
- [`IntermediateResultSavingMode`]({{ site.python_enumerations }}result-enums.html#intermediateresultsavingmode)	
- [`IntermediateResultType`]({{ site.python_enumerations }}result-enums.html#intermediateresulttype)	
- [`LocalizationMode`]({{ site.python_enumerations }}parameter-mode-enums.html#localizationmode)
- [`PDFReadingMode`]({{ site.python_enumerations }}parameter-mode-enums.html#pdfreadingmode)   
- [`QRCodeErrorCorrectionLevel`]({{ site.python_enumerations }}other-enums.html#qrcodeerrorcorrectionlevel)	
- [`RegionPredetectionMode`]({{ site.python_enumerations }}parameter-mode-enums.html#regionpredetectionmode)	
- [`ResultCoordinateType`]({{ site.python_enumerations }}result-enums.html#resultcoordinatetype)	
- [`ResultType`]({{ site.python_enumerations }}result-enums.html#resulttype)	
- [`ScaleUpMode`]({{ site.python_enumerations }}parameter-mode-enums.html#scaleupmode)	
- [`TerminatePhase`]({{ site.python_enumerations }}parameter-mode-enums.html#terminatephase)	
- [`TextFilterMode`]({{ site.python_enumerations }}parameter-mode-enums.html#textfiltermode)	
- [`TextResultOrderMode`]({{ site.python_enumerations }}result-enums.html#textresultordermode)	
- [`TextureDetectionMode`]({{ site.python_enumerations }}parameter-mode-enums.html#texturedetectionmode)
