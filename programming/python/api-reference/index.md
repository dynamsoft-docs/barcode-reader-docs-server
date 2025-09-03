---
layout: default-layout
title: Main Page - Dynamsoft Barcode Reader SDK Python Edition API Reference
description: This is the main page of Dynamsoft Barcode Reader SDK Python Edition API Reference.
keywords: api reference, python
needAutoGenerateSidebar: true
needGenerateH3Content: true
permalink: /programming/python/api-reference/index.html
---

# Python API Reference
 
## BarcodeReader Class

### `BarcodeReader` Attributes
  
  | Attribute            | Description |
  |----------------------|-------------|
  | `version`  | dbr-python version |
  | `dbr_version`  | Dynamsoft Barcode Reader version |
  
   

### Constructor and Destructor

  | Method               | Description |
  |----------------------|-------------|
  | [`BarcodeReader`](BarcodeReader/constructor-and-destructor.md#barcodereader) | Constructor of `BarcodeReader` object.|
  | [`get_instance`](BarcodeReader/constructor-and-destructor.md#get_instance) | Creates an instance of Dynamsoft Barcode Reader. |
  | [`recycle_instance`](BarcodeReader/constructor-and-destructor.md#recycle_instance) | Destroys an instance of Dynamsoft Barcode Reader. |

   
 
   

### License Methods
  
  | Method               | Description |
  |----------------------|-------------|
  | [`init_license`](BarcodeReader/license.md#init_license) | Reads product key and activates the SDK.  |
  | [`get_device_uuid`](BarcodeReader/license.md#get_device_uuid) | Gets the device uuid used for license activating. |
  | [`is_instance_valid`](BarcodeReader/license.md#is_instance_valid) | Gets whether the instance is valid when charging by concurrent instances count. |
  | [`set_device_friendly_name`](BarcodeReader/license.md#set_device_friendly_name) | Sets a human-readable name that identifies the device. |
  | [`set_license_cache_path`](BarcodeReader/license.md#set_license_cache_path) | Sets a directory path for saving the license cache. |
  | [`set_max_concurrent_instance_count`](BarcodeReader/license.md#set_max_concurrent_instance_count) | Sets the max concurrent instance count used for current device and process. |
  | [`get_instance_pool_status`](BarcodeReader/license.md#get_instance_pool_status) | Gets a class to represent the status of an instance pool. |
  | [`get_idle_instances_count`](BarcodeReader/license.md#get_idle_instances_count) | `Deprecated` |
  | [`init_license_from_server`](BarcodeReader/license.md#init_license_from_server) | `Deprecated` |
  | [`init_license_from_license_content`](BarcodeReader/license.md#init_license_from_license_content) | `Deprecated` |
  | [`output_license_to_string`](BarcodeReader/license.md#output_license_to_string) | `Deprecated` |
  | [`init_dls_connection_parameters`](BarcodeReader/license.md#init_dls_connection_parameters) | `Deprecated` |
  | [`init_license_from_dls`](BarcodeReader/license.md#init_license_from_dls) | `Deprecated` |
  | [`init_lts_connection_parameters`](BarcodeReader/license.md#init_lts_connection_parameters) | `Deprecated`. |
  | [`init_license_from_lts`](BarcodeReader/license.md#init_license_from_lts) | `Deprecated`. |
      

### Decode Methods
   
  | Method               | Description |
  |----------------------|-------------|
  | [`decode_file`](BarcodeReader/decode.md#decode_file) | Decodes barcodes from a specified image file. |
  | [`decode_buffer`](BarcodeReader/decode.md#decode_buffer) | Decodes barcodes from the memory buffer containing image pixels in defined format.  |
  | [`decode_file_stream`](BarcodeReader/decode.md#decode_file_stream) | Decodes barcodes from an image file in memory. |
  | [`decode_buffer_manually`](BarcodeReader/decode.md#decode_buffer_manually) | Decodes barcodes from the memory buffer containing image pixels in defined format. |
  | [`decode_base64_string`](BarcodeReader/decode.md#decode_base64_string) | Decodes barcodes from the base64 encoded string. |
  | [`init_intermediate_result`](BarcodeReader/decode.md#init_intermediateresult) | Inits an intermediateResult struct with default values. |
  | [`decode_intermediate_results`](BarcodeReader/decode.md#decode_intermediateresults) | Decodes barcode from intermediate results. |
   
   
 

### Basic Settings Methods
   
  | Method               | Description |
  |----------------------|-------------|
  | [`set_mode_argument`](BarcodeReader/parameter-and-runtime-settings-basic.md#set_mode_argument) | Sets the optional argument for a specified mode in Modes parameters. |
  | [`get_mode_argument`](BarcodeReader/parameter-and-runtime-settings-basic.md#get_mode_argument) | Gets the optional argument for a specified mode in Modes parameters.  |
  | [`get_runtime_settings`](BarcodeReader/parameter-and-runtime-settings-basic.md#get_runtime_settings) | Gets current runtime settings. |
  | [`update_runtime_settings`](BarcodeReader/parameter-and-runtime-settings-basic.md#update_runtime_settings) | Updates runtime settings with a given struct. |
  | [`reset_runtime_settings`](BarcodeReader/parameter-and-runtime-settings-basic.md#reset_runtime_settings) | Resets all parameters to default values. |

### Advanced Settings Methods
  
  | Method               | Description |
  |----------------------|-------------|
  | [`init_runtime_settings_with_file`](BarcodeReader/parameter-and-runtime-settings-advanced.md#init_runtime_settings_with_file)  | Initializes runtime settings with the settings in a given JSON file. |
  | [`init_runtime_settings_with_string`](BarcodeReader/parameter-and-runtime-settings-advanced.md#init_runtime_settings_with_string) | Initializes runtime settings with the settings in a given JSON string. |
  | [`append_template_file_to_runtime_settings`](BarcodeReader/parameter-and-runtime-settings-advanced.md#append_template_file_to_runtime_settings) | Appends a new template file to the current runtime settings. |
  | [`append_template_string_to_runtime_settings`](BarcodeReader/parameter-and-runtime-settings-advanced.md#append_template_string_to_runtime_settings) | Appends a new template string to the current runtime settings. |
  | [`get_all_template_names`](BarcodeReader/parameter-and-runtime-settings-advanced.md#get_all_template_names) | Gets the parameter templates name array. |
  | [`output_settings_to_json_file`](BarcodeReader/parameter-and-runtime-settings-advanced.md#output_settings_to_json_file) | Outputs runtime settings to a settings file (JSON file). |
  | [`output_settings_to_json_string`](BarcodeReader/parameter-and-runtime-settings-advanced.md#output_settings_to_json_string) | Outputs runtime settings to a string. |
   
      
 
## General Methods

  | Method               | Description |
  |----------------------|-------------|
  | [`transform_coordinates`](BarcodeReader/general.md#transform_coordinates) | Transform the coordinates of a point based on the given transformation matrix. |
   

   
### Video Methods

#### Decode
    
   | Method               | Description |
   |----------------------|-------------|
   | [`start_video_mode`](BarcodeReader/video.md#start_video_mode) | Starts a new thread to decode barcodes from the inner frame queue. |
   | [`append_video_frame`](BarcodeReader/video.md#append_video_frame) | Appends a frame image buffer to the inner frame queue. |
   | [`stop_video_mode`](BarcodeReader/video.md#stop_video_mode) | Stops the frame decoding thread created by `start_video_mode()`. |

#### Parameter
   
   | Method               | Description |
   |----------------------|-------------|
   | [`init_frame_decoding_parameters`](BarcodeReader/video.md#init_frame_decoding_parameters) | Initializes frame decoding parameters. |


#### Status retrieval
   
   | Method               | Description |
   |----------------------|-------------|
   | [`get_length_of_frame_queue`](BarcodeReader/video.md#get_length_of_frame_queue) | Gets length of current inner frame queue. |
 
   


## Auxiliary Classes

- [`AztecDetailedResult`](class/AztecDetailedResult.md)	 
- [`BarcodeReaderError`](class/BarcodeReaderError.md)	
- [`Contour`](class/Contour.md)	 
- [`DataMatrixDetailedResult`](class/DataMatrixDetailedResult.md)	 
- [`ExtendedResult`](class/ExtendedResult.md)	
- [`FrameDecodingParameters`](class/FrameDecodingParameters.md)	
- [`ImageData`](class/ImageData.md)	 
- [`InstancePoolStatus`](class/InstancePoolStatus.md)
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
- [`AccompanyingTextRecognitionMode`]({{ site.dbr_python_enumerations }}parameter-mode-enums.html#accompanyingtextrecognitionmode)	
- [`BarcodeColourMode`]({{ site.dbr_python_enumerations }}parameter-mode-enums.html#barcodecolourmode)	
- [`BarcodeComplementMode`]({{ site.dbr_python_enumerations }}parameter-mode-enums.html#barcodecomplementmode)	
- [`BarcodeFormat`]({{ site.dbr_python_enumerations }}format-enums.html#barcodeformat)	
- [`BarcodeFormat_2`]({{ site.dbr_python_enumerations }}format-enums.html#barcodeformat_2)	
- [`BinarizationMode`]({{ site.dbr_python_enumerations }}parameter-mode-enums.html#binarizationmode)
- [`ClarityCalculationMethod`]({{ site.dbr_python_enumerations }}frame-decoding-enums.html#claritycalculationmethod) 
- [`ClarityFilterMode`]({{ site.dbr_python_enumerations }}frame-decoding-enums.html#clarityfiltermode) 
- [`ColourClusteringMode`]({{ site.dbr_python_enumerations }}parameter-mode-enums.html#colourclusteringmode)	
- [`ColourConversionMode`]({{ site.dbr_python_enumerations }}parameter-mode-enums.html#colourconversionmode)	
- [`ConflictMode`]({{ site.dbr_python_enumerations }}parameter-mode-enums.html#conflictmode)	
- [`DeblurMode`]({{ site.dbr_python_enumerations }}parameter-mode-enums.html#deblurmode)
- [`DeformationResistingMode`]({{ site.dbr_python_enumerations }}parameter-mode-enums.html#deformationresistingmode)
- [`DMChargeWay`]({{ site.dbr_python_enumerations }}other-enums.html#dm_chargeway)
- [`DMDeploymentType`]({{ site.dbr_python_enumerations }}other-enums.html#dm_deploymenttype)
- [`DMLicenseModule`]({{ site.dbr_python_enumerations }}other-enums.html#dm_licensemodule)
- [`DMUUIDGenerationMethod`]({{ site.dbr_python_enumerations }}other-enums.html#dm_uuidgenerationmethod)
- [`DPMCodeReadingMode`]({{ site.dbr_python_enumerations }}parameter-mode-enums.html#dpmcodereadingmode)	
- [`GrayscaleTransformationMode`]({{ site.dbr_python_enumerations }}parameter-mode-enums.html#grayscaletransformationmode)	
- [`ImagePixelFormat`]({{ site.dbr_python_enumerations }}other-enums.html#imagepixelformat)	
- [`ImagePreprocessingMode`]({{ site.dbr_python_enumerations }}parameter-mode-enums.html#imagepreprocessingmode)	
- [`IMResultDataType`]({{ site.dbr_python_enumerations }}result-enums.html#imresultdatatype)	
- [`IntermediateResultSavingMode`]({{ site.dbr_python_enumerations }}result-enums.html#intermediateresultsavingmode)	
- [`IntermediateResultType`]({{ site.dbr_python_enumerations }}result-enums.html#intermediateresulttype)	
- [`LocalizationMode`]({{ site.dbr_python_enumerations }}parameter-mode-enums.html#localizationmode)
- [`PDFReadingMode`]({{ site.dbr_python_enumerations }}parameter-mode-enums.html#pdfreadingmode)   
- [`Product`]({{ site.dbr_python_enumerations }}other-enums.html#product)   
- [`QRCodeErrorCorrectionLevel`]({{ site.dbr_python_enumerations }}other-enums.html#qrcodeerrorcorrectionlevel)	
- [`RegionPredetectionMode`]({{ site.dbr_python_enumerations }}parameter-mode-enums.html#regionpredetectionmode)	
- [`ResultCoordinateType`]({{ site.dbr_python_enumerations }}result-enums.html#resultcoordinatetype)	
- [`ResultType`]({{ site.dbr_python_enumerations }}result-enums.html#resulttype)	
- [`ScaleUpMode`]({{ site.dbr_python_enumerations }}parameter-mode-enums.html#scaleupmode)	
- [`TerminatePhase`]({{ site.dbr_python_enumerations }}parameter-mode-enums.html#terminatephase)	
- [`TextFilterMode`]({{ site.dbr_python_enumerations }}parameter-mode-enums.html#textfiltermode)	
- [`TextResultOrderMode`]({{ site.dbr_python_enumerations }}result-enums.html#textresultordermode)	
- [`TextureDetectionMode`]({{ site.dbr_python_enumerations }}parameter-mode-enums.html#texturedetectionmode)

## [Error Code]({{ site.dbr_python_enumerations }}error-code.html)
