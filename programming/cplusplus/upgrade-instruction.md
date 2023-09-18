---
title: Upgrade Instructions - Dynamsoft Barcode Reader C++ Edition
keywords: c++, cplusplus, upgrade
description: This page introduces how to upgrade Dynamsoft Barcode Reader
needAutoGenerateSidebar: false
permalink: /programming/cplusplus/upgrade-instruction.html
---

# How to Upgrade

## From version 9.x or earlier to version 10.x

`DynamsoftBarcodeReader` SDK has been refactored to integrate with `DynamsoftCaptureVision (DCV)` architecture. To upgrade from version 9.x or earlier to 10.x, we recommend you to follow the [User Guide]({{site.cpp}}user-guide.html) and re-write your codes.

Notice the following break changes when upgrading your SDK.

### Update the Included Headers, libs & DLLs

Since the SDK architecture is changed, you have to change you code for including the headers, libs and DLLs. You can use the following code to replace your previous code.

```cpp
#include "[INSTALLATION FOLDER]/Include/DynamsoftCaptureVisionRouter.h"

using namespace std;
using namespace dynamsoft::license;
using namespace dynamsoft::cvr;
using namespace dynamsoft::dbr;
using namespace dynamsoft::utility;

#if defined(_WIN64) || defined(_WIN32)
    #ifdef _WIN64
        #pragma comment(lib, "[INSTALLATION FOLDER]/Lib/Windows/x64/DynamsoftCorex64.lib")
        #pragma comment(lib, "[INSTALLATION FOLDER]/Lib/Windows/x64/DynamsoftLicensex64.lib")
        #pragma comment(lib, "[INSTALLATION FOLDER]/Lib/Windows/x64/DynamsoftCaptureVisionRouterx64.lib")
        #pragma comment(lib, "[INSTALLATION FOLDER]/Lib/Windows/x64/DynamsoftUtilityx64.lib")
    #else
        #pragma comment(lib, "[INSTALLATION FOLDER]/Lib/Windows/x86/DynamsoftCorex86.lib")
        #pragma comment(lib, "[INSTALLATION FOLDER]/Lib/Windows/x86/DynamsoftLicensex86.lib")
        #pragma comment(lib, "[INSTALLATION FOLDER]/Lib/Windows/x86/DynamsoftCaptureVisionRouterx86.lib")
        #pragma comment(lib, "[INSTALLATION FOLDER]/Lib/Windows/x86/DynamsoftUtilityx86.lib")
    #endif
#endif
```

Put the following **.dll/.so** files in your executable path:

* Windows
  * x64:
    * DynamsoftBarcodeReaderx64.dll
    * DynamsoftCaptureVisionRouterx64.dll
    * DynamsoftCorex64.dll
    * DynamsoftImageProcessingx64.dll
    * DynamsoftLicensex64.dll
    * DynamsoftUtilityx64.dll
  * x86:
    * DynamsoftBarcodeReaderx86.dll
    * DynamsoftCaptureVisionRouterx86.dll
    * DynamsoftCorex86.dll
    * DynamsoftImageProcessingx86.dll
    * DynamsoftLicensex86.dll
    * DynamsoftUtilityx86.dll

* Linux
  * x64:
    * libDynamsoftBarcodeReader.so
    * libDynamsoftCaptureVisionRouter.so
    * libDynamsoftCore.so
    * libDynamsoftImageProcessing.so
    * libDynamsoftLicense.so
    * libDynamsoftUtility.so

### Migrate from Class CBarcodeReader to Class CCaptureVisionRouter

Class `CCaptureVisionRouter` is added to replace class `CBarcodeReader`. Class `CCaptureVisionRouter` APIs includes the following features:

* Retrieving images from the `ImageSourceAdapter`.
* Updating templates and configuring settings.
* Dynamically loading the `DynamsoftBarcodeReader` module for barcode decoding.
* Dispatching the results to registered receivers of type `CapturedResultReceiver`.
  
### Templates

The template system is upgraded. The template you used for the previous version can't be directly recognized by the new version. Please <a href="https://download2.dynamsoft.com/dcv/TemplateConverter.zip" target="_blank">download the TemplateConverter tool</a> or <a href="https://www.dynamsoft.com/company/customer-service/#contact" target="_blank">contact us</a> to upgrade your template.

<!-- 
### Replace PublicRuntimeSettings APIs with SimplifiedSettings APIs

The setting configuration APIs are refactored. Struct `PublicRuntimeSettings` is removed. Though a series of settings are still available via struct `SimplifiedCaptureVisionSettings`, the majority of settings are "template only". Please view the API reference of struct [`SimplifiedCaptureVisionSettings`]({{ site.dcv_cpp_api }}capture-vision-router/structs/simplified-capture-vision-settings.html) and [`SimplifiedBarcodeReaderSettings`]({{ site.cpp_api }}simplified-barcode-reader-settings.html) to see whether your settings are still available. If they are no longer supported, please <a href="https://www.dynamsoft.com/company/customer-service/#contact" target="_blank">contact us</a>. We will help you on generating a new template that supports your previous settings. -->

### Update Your Image Decoding Codes

#### Single Image Decoding

Since class `CBarcodeReader` is replaced with class `CCaptureVisionRouter`. You have to use the following `Capture` APIs instead of the `Decode` APIs:

```cpp
// Capture from a file.
CCapturedResult* Capture(const char* filePath, const char* templateName="");
// Capture from a file in memory.
CCapturedResult* Capture(const unsigned char *fileBytes, int fileSize, const char* templateName="");
// Capture from a CImageData object.
CCapturedResult* Capture(const CImageData* pImageData, const char* templateName="");
```

**The Corresponding Capture APIs of the Decode APIs**

| Removed APIs | New APIs |
| :----------- | :------- |
| `DecodeFile` | `Capture(const char* filePath, const char* templateName="")` |
| `DecodeFileInMemory` | `Capture(const unsigned char *fileBytes, int fileSize, const char* templateName="")` |
| `DecodeBuffer` | `Capture(const CImageData* pImageData, const char* templateName="")` |
| `DecodeBase64String` | **Currently not available**. |
| `DecodeDIB` | **Currently not available**. |

#### Batch Image Decoding

DCV architecture allows you to set a folder as an image source to fetch image from. To use this feature, you have to set `CDirectoryFetcher` as the input via class `CCaptureVisionRouter`.

```cpp
int main()
{
   CCaptureVisionRouter *cvr = new CCaptureVisionRouter;
   // Create a CDirectoryFetcher instance and set is as the input of cvr
   CDirectoryFetcher *fetcher = new CDirectoryFetcher;
   // Replace the following directory path with your directory path:
   fetcher->SetDirectory("C:\\my-directory-folder\\");
   cvr->SetInput(fetcher);
   // Create a CCapturedResultReceiver instance 
   CCapturedResultReceiver *capturedReceiver = new MyCapturedResultReceiver;
   cvr->AddResultReceiver(capturedReceiver);
   // Start capturing
   errorCode = cvr->StartCapturing(CPresetTemplate::PT_READ_BARCODES, true, errorMsg, 512);
}
```

### Update Your Video Streaming Decoding Codes

`CImageSourceAdapter` is added to replace the `FrameDecodeingParameters` and the previous video methods. The following steps shows how to implement video streaming barcode decoding with `CImageSourceAdapter`:

```cpp
class MyImageSource : public CImageSourceAdapter 
{
  // Add code to implement CImageSourceAdapter
};
int main()
{
  MyImageSource *source = new MyImageSource;
  cvr->SetInput(source);
}
```

### Result Obtaining

If you are using batch image decoding or video streaming decoding, you have to register a [`CCapturedResultReceiver`]({{ site.dcv_cpp_api }}core/basic-structures/captured-result-receiver.html) to receive the barcode decoding results.

If you are using `Capture` APIs to process a single image, the barcode decoding results are returned from the `Capture` APIs.

### Migrate Your PublicRuntimeSettings

The setting configuration APIs are refactored. Struct `PublicRuntimeSettings` is removed. Though a series of settings are still available via struct `SimplifiedCaptureVisionSettings`, the majority of settings are "template only". Please view the following instructions to update your settings.

#### Migrate to SimplifiedCaptureVisionSettings

The following parameters are replaced by similar parameters under `SimplifiedCaptureVisionSettings`. They can also be set via a template file(String).

| PublicRuntimeSettings | SimplifiedCaptureVisionSettings | Template File |
| --------------------- | ------------------------------- | ------------- |
| `region` | `roi` & `roiMeasuredInPercentage` | [`TargetROIDefOptions.Location.Offset`]({{ site.dcv_parameters_reference }}target-roi-def/location.html) |
| `timeout` | `timeout` | [`CaptureVisionTemplates.Timeout`]({{ site.dcv_parameters_reference }}capture-vision-template/timeout.html) |

#### Migrate to SimplifiedBarcodeReaderSettings

The following parameters are replaced by similar parameters under `SimplifiedBarcodeReaderSettings`. The majority of them can also be set via a template file(String).

| PublicRuntimeSettings | SimplifiedBarcodeReaderSettings | Template File |
| --------------------- | ------------------------------- | ------------- |
| `minBarcodeTextLength` | `minBarcodeTextLength` | [`BarcodeFormatSpecificationOptions.BarcodeTextLengthRangeArray`]({{ site.dcv_parameters_reference }}barcode-format-specification/barcode-text-length-range-array.html) |
| `minResultConfidence` | `minResultConfidence` | [`BarcodeFormatSpecificationOptions.MinResultConfidence`]({{ site.dcv_parameters_reference }}barcode-format-specification/min-result-confidence.html) |
| `localizationModes` | `localizationModes` | [`BarcodeReaderTaskSettingOptions.LocationModes`]({{ site.dcv_parameters_reference }}barcode-reader-task-settings/localization-modes.html) |
| `expectedBarcodesCount` | `expectedBarcodesCount` | [`BarcodeReaderTaskSettingOptions.LocationModes`]({{ site.dcv_parameters_reference }}barcode-reader-task-settings/expected-barcodes-count.html) |
| `barcodeFormatIds` | `barcodeFormatIds` | [`BarcodeReaderTaskSettingOptions.BarcodeFormatIds`]({{ site.dcv_parameters_reference }}barcode-reader-task-settings/barcode-format-ids.html) |
| `barcodeFormatIds_2` | `barcodeFormatIds`. | [`BarcodeReaderTaskSettingOptions.BarcodeFormatIds`]({{ site.dcv_parameters_reference }}barcode-reader-task-settings/barcode-format-ids.html) |
| `deblurModes` | `deblurModes` | [`BarcodeReaderTaskSettingOptions.DeblurModes`]({{ site.dcv_parameters_reference }}barcode-reader-task-settings/deblur-modes.html) |
| `deblurLevel` | `deblurModes` | [`BarcodeReaderTaskSettingOptions.DeblurModes`]({{ site.dcv_parameters_reference }}barcode-reader-task-settings/deblur-modes.html) |

> Remarks:
>
> * The 2 groups of barcode formats are merged.
> * `DeblurLevel` is deprecated. You can use `DeblurModes` instead.

| FurtherModes | SimplifiedBarcodeReaderSettings | Template File |
| ------------ | ------------------------------- | ------------- |
| `grayscaleTransformationModes` | `grayscaleTransformationModes` | [`ImageParameterOptions.GrayscaleTransformationModes`]({{ site.dcv_parameters_reference }}image-parameter/grayscale-enhancement-modes.html) |
| `imagePreprocessingModes` | `grayscaleEnhancementModes` | [`ImageParameterOptions.GrayscaleEnhancementModes`]({{ site.dcv_parameters_reference }}image-parameter/grayscale-transformation-modes.html) |

> Remarks: The mode `IPM_MORPHOLOGY` of `imagePreprocessingModes` is migrated to `BinarizationModes`. The mode arguments `MorphOperation`, `MorphOperationKernelSizeX`, `MorphOperationKernelSizeY`, `MorphShape` are now available for all modes of `BinarizationModes`.

#### Migrate to Template File

| PublicRuntimeSettings | Template File |
| --------------------- | ------------- |
| `scaleDownThreshold` | [`ScaleDownThreshold`]({{ site.dcv_parameters_reference }}image-parameter/scale-down-threshold.html) |
| `binarizationModes` | [`BinarizationModes`]({{ site.dcv_parameters_reference }}image-parameter/binarization-modes.html) |
| `resultCoordinateType` | [`ResultCoordinateType`]({{ site.dcv_parameters_reference }}barcode-reader-task-settings/result-coordinate-type.html) |
| `textResultOrderModes` | [`TextResultOrderModes`]({{ site.dcv_parameters_reference }}barcode-reader-task-settings/text-result-order-modes.html) |
| `returnBarcodeZoneClarity` | [`ReturnBarcodeZoneClarity`]({{ site.dcv_parameters_reference }}barcode-reader-task-settings/return-barcode-zone-clarity.html) |
| `scaleUpModes` | [`ScaleUpModes`]({{ site.dcv_parameters_reference }}image-parameter/scale-up-modes.html) |
| `barcodeZoneMinDistanceToImageBorders` | [`BarcodeZoneMinDistanceToImageBorders`]({{ site.dcv_parameters_reference }}barcode-format-specification/barcode-zone-min-distance-to-image-borders.html) |

| FurtherModes | Template File |
| ------------ | ------------- |
| `colourConversionModes` | [`ColourConversionModes`]({{ site.dcv_parameters_reference }}image-parameter/colour-conversion-modes.html) |
| `regionPredetectionModes` | [`RegionPredetectionModes`]({{ site.dcv_parameters_reference }}image-parameter/region-predetection-modes.html) |
| `textureDetectionModes` | [`TextureDetectionModes`]({{ site.dcv_parameters_reference }}image-parameter/texture-detection-modes.html) |
| `textFilterModes` | [`TextFilterModes`]({{ site.dcv_parameters_reference }}image-parameter/text-detection-mode.html & image-parameter/if-erase-text-zone.html) |
| `dpmCodeReadingModes` | [`DPMCodeReadingModes`]({{ site.dcv_parameters_reference }}barcode-reader-task-settings/dpm-code-reading-modes.html) |
| `deformationResistingModes` | [`DeformationResistingModes`]({{ site.dcv_parameters_reference }}barcode-reader-task-settings/deformation-resisting-modes.html) |
| `barcodeComplementModes` | [`BarcodeComplementModes`]({{ site.dcv_parameters_reference }}barcode-reader-task-settings/barcode-complement-modes.html) |
| `barcodeColourModes` | [`BarcodeColourModes`]({{ site.dcv_parameters_reference }}barcode-reader-task-settings/barcode-colour-modes.html) |
| `terminatePhase` | [`TerminateSettings`]({{ site.dcv_parameters_reference }}barcode-reader-task-settings/terminate-setting.html) |
| `maxAlgorithmThreadCount` | [`MaxThreadsInOneTask`]({{ site.dcv_parameters_reference }}barcode-reader-task-settings/max-threads-in-one-task.html) |

#### Migrate to Other APIs

The PDF paremeters of PublicRuntimeSettings are moved to set via the `setPDFReadingParameter` method of `DirectoryFetcher` and `FileFetcher` with a `CPDFReadingParameter` parameter.

| PDF Parameters of PublicRuntimeSettings |
| --------------------------------------- |
| `pdfReadingMode` |
| `pdfRasterDPI` |

Class [`CPDFReadingParameter`]({{ site.dcv_cpp_api }}core/basic-structures/pdf-reading-parameter.html) is defined as follows:

```cpp
class DS_API CPDFReadingParameter {
public:
    PDFReadingMode mode;
    int dpi;
    RasterDataSource rasterDataSource;
};
```

The `IntermediateResult` system is redesigned and the following parameters are deprecated.

| PublicRuntimeSettings |
| --------------------- |
| `intermediateResultTypes` |
| `intermediateResultSavingMode` |

#### Removed

The following parameter is removed.

| PublicRuntimeSettings |
| --------------------- |
| `colourClusteringModes` |
