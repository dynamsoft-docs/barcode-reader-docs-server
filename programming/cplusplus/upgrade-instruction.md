---
title: Upgrade Instructions - Dynamsoft Barcode Reader SDK C++ Edition
keywords: c++, cplusplus, upgrade
description: This page introduces how to upgrade Dynamsoft Barcode Reader SDK C++ Edition
needAutoGenerateSidebar: true
needGenerateH3Content: true
permalink: /programming/cplusplus/upgrade-instruction.html
---

# How to Upgrade

## From version 9.x or earlier to version 10.x

Dynamsoft Barcode Reader SDK has been refactored to integrate with [`DynamsoftCaptureVision (DCV)`]({{ site.dcvb_architecture }}) architecture. To upgrade from version 9.x or earlier to 10.x, we recommend you to follow the [User Guide]({{site.dbr_cpp}}user-guide.html) and re-write your codes.

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
        #pragma comment(lib, "[INSTALLATION FOLDER]/Distributables/Lib/Windows/x64/DynamsoftCorex64.lib")
        #pragma comment(lib, "[INSTALLATION FOLDER]/Distributables/Lib/Windows/x64/DynamsoftLicensex64.lib")
        #pragma comment(lib, "[INSTALLATION FOLDER]/Distributables/Lib/Windows/x64/DynamsoftCaptureVisionRouterx64.lib")
        #pragma comment(lib, "[INSTALLATION FOLDER]/Distributables/Lib/Windows/x64/DynamsoftUtilityx64.lib")
    #else
        #pragma comment(lib, "[INSTALLATION FOLDER]/Distributables/Lib/Windows/x86/DynamsoftCorex86.lib")
        #pragma comment(lib, "[INSTALLATION FOLDER]/Distributables/Lib/Windows/x86/DynamsoftLicensex86.lib")
        #pragma comment(lib, "[INSTALLATION FOLDER]/Distributables/Lib/Windows/x86/DynamsoftCaptureVisionRouterx86.lib")
        #pragma comment(lib, "[INSTALLATION FOLDER]/Distributables/Lib/Windows/x86/DynamsoftUtilityx86.lib")
    #endif
#endif
```

**Distribution**

- Copy `[INSTALLATION FOLDER]/Distributables/DBR-PresetTemplates.json` to the same folder as the executable program.
- Copy the libraries to the same folder as the executable program.
  - For Windows: Copy **ALL** `*.dll` files under `[INSTALLATION FOLDER]/Distributables/Lib/Windows/[platform]`. Replace `[platform]` with your project's platform setting.

  - For Linux: Copy **ALL** `*.so` files under `[INSTALLATION FOLDER]/Distributables/Lib/Linux/[platform]`. Replace `[platform]` with your project's platform setting.

### Update the License Activation Code

Starting from 10.0, we have unified the API for setting licenses across different Dynamsoft products.

| Old APIs | New APIs |
| :----------- | :------- |
| `CBarcodeReader.InitLicense` | `CLicenseManager.InitLicense` |

### Update Single Image Decoding APIs

The APIs for decoding single image has been adjusted as follows:

| Old APIs | New APIs |
| :----------- | :------- |
| `CBarcodeReader.DecodeFile` | `CCaptureVisionRouter.Capture(const char* filePath, const char* templateName)` |
| `CBarcodeReader.DecodeFileInMemory` | `CCaptureVisionRouter.Capture(const unsigned char *fileBytes, int fileSize, const char* templateName)` |
| `CBarcodeReader.DecodeBuffer` | `CCaptureVisionRouter.Capture(const CImageData* pImageData, const char* templateName)` |
| `struct TextResult` | `class CBarcodeResultItem` |
| `struct TextResultArray` | `class CCapturedResult` |
| `CBarcodeReader.DecodeBase64String` | **Currently not available**. |
| `CBarcodeReader.DecodeDIB` | **Currently not available**. |

### Update Video Streaming Decoding Code

`CImageSourceAdapter` is added to replace the `FrameDecodeingParameters` and the previous video methods. You should implement `CImageSourceAdapter` to transfer image data from camera or video file to buffer. The following code snippet demonstrate basic usage of decoding video frames:

```cpp
class MyVideoSource : public CProactiveImageSourceAdapter 
{
    // You should implement the `HasNextImageToFetch` method to indicate if there is a next frame
    bool HasNextImageToFetch() const override 
    {
        return true;
    }

    // You should implement the `FetchImage` method to get the next frame
    CImageData* FetchImage() override
    {
        // Add code to get the video frame from camera or video file
    }
};

class MyBarcodeResultReceiver: public CCapturedResultReceiver
{
public:
    virtual void OnDecodedBarcodesReceived(DecodedBarcodesResult * result) {
        // Add code to process the result
    }
};

int main()
{
    CCaptureVisionRouter *cvr = new CCaptureVisionRouter;

    // Create your video source and bind it to the router
    MyVideoSource *source = new MyVideoSource;
    cvr->SetInput(source);

    // Create a CCapturedResultReceiver instance 
    MyBarcodeResultReceiver *barcodesReceiver = new MyCapturedResultReceiver;
    cvr->AddResultReceiver(barcodesReceiver);

    // Start capturing
    errorCode = cvr->StartCapturing(CPresetTemplate::PT_READ_BARCODES, true, errorMsg, 512);

    delete barcodesReceiver;
    delete source;
    delete cvr;
}
```

### Migrate Your Templates

The template system is upgraded. The template you used for the previous version can't be directly recognized by the new version. Please <a href="https://download2.dynamsoft.com/dcv/TemplateConverter.zip" target="_blank">download the TemplateConverter tool</a> or <a href="https://www.dynamsoft.com/company/customer-service/#contact" target="_blank">contact us</a> to upgrade your template.

The template-based APIs have been updated as follows:

| Old APIs | New APIs |
| :----------- | :------- |
| `CBarcodeReader.InitRuntimeSettingsWithFile` | `CCaptureVisionRouter.InitSettingsFromFile` |
| `CBarcodeReader.InitRuntimeSettingsWithString` | `CCaptureVisionRouter.InitSettings` |
| `CBarcodeReader.OutputSettingsToFile` | `CCaptureVisionRouter.OutputSettingsToFile` |
| `CBarcodeReader.OutputSettingsToString` | `CCaptureVisionRouter.OutputSettings` |
| `CBarcodeReader.ResetRuntimeSettings` | `CCaptureVisionRouter.ResetSettings` |
| `CBarcodeReader.AppendTplFileToRuntimeSettings` | **Not available**. |
| `CBarcodeReader.AppendTplStringToRuntimeSettings` | **Not available**. |

### Migrate Your PublicRuntimeSettings

The struct `PublicRuntimeSettings` has been refactored. It retains commonly used properties while removing the previously complex property settings, which are now exclusively supported through templates.

The APIs for accessing and updating `PublicRuntimeSettings` has been adjusted as follows:

| Old APIs | New APIs |
| :----------- | :------- |
| `CBarcodeReader.GetRuntimeSettings` | `CCaptureVisionRouter.GetSimplifiedSettings` |
| `CBarcodeReader.UpdateRuntimeSettings` | `CCaptureVisionRouter.UpdateSettings` |

#### Migrate to SimplifiedCaptureVisionSettings

The following properties are replaced by similar properties under `SimplifiedCaptureVisionSettings`. They can also be set via a template file(String).

| PublicRuntimeSettings Property | SimplifiedCaptureVisionSettings Parameter | Template File Parameter |
| ------------------------------- | ----------------------------------------- | ----------------------- |
| `region` | [`roi`]({{ site.dcvb_cpp_api }}capture-vision-router/structs/simplified-capture-vision-settings.html#roi) & [`roiMeasuredInPercentage`]({{ site.dcvb_cpp_api }}capture-vision-router/structs/simplified-capture-vision-settings.html#roimeasuredinpercentage) | [`TargetROIDef.Location.Offset`]({{ site.dcvb_parameters_reference }}target-roi-def/location.html) |
| `timeout` | [`timeout`]({{ site.dcvb_cpp_api }}capture-vision-router/structs/simplified-capture-vision-settings.html#timeout) | [`CaptureVisionTemplates.Timeout`]({{ site.dcvb_parameters_reference }}capture-vision-template/timeout.html) |

#### Migrate to SimplifiedBarcodeReaderSettings

The following properties are replaced by similar properties under `SimplifiedBarcodeReaderSettings`. The majority of them can also be set via a template file(String).

| PublicRuntimeSettings Property | SimplifiedBarcodeReaderSettings Property | Template File Parameter |
| ------------------------------- | ----------------------------------------- | ----------------------- |
| `minBarcodeTextLength` | [`minBarcodeTextLength`]({{ site.dbr_cpp_api }}simplified-barcode-reader-settings.html#minbarcodetextlength) | [`BarcodeFormatSpecification.BarcodeTextLengthRangeArray`]({{ site.dcvb_parameters_reference }}barcode-format-specification/barcode-text-length-range-array.html) |
| `minResultConfidence` | [`minResultConfidence`]({{ site.dbr_cpp_api }}simplified-barcode-reader-settings.html#minresultconfidence) | [`BarcodeFormatSpecification.MinResultConfidence`]({{ site.dcvb_parameters_reference }}barcode-format-specification/min-result-confidence.html) |
| `localizationModes` | [`localizationModes`]({{ site.dbr_cpp_api }}simplified-barcode-reader-settings.html#localizationmodes) | [`BarcodeReaderTaskSetting.LocationModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/localization-modes.html) |
| `expectedBarcodesCount` | [`expectedBarcodesCount`]({{ site.dbr_cpp_api }}simplified-barcode-reader-settings.html#expectedbarcodescount) | [`BarcodeReaderTaskSetting.ExpectedBarcodesCount`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/expected-barcodes-count.html) |
| `barcodeFormatIds` | [`barcodeFormatIds`]({{ site.dbr_cpp_api }}simplified-barcode-reader-settings.html#barcodeformatids) | [`BarcodeReaderTaskSetting.BarcodeFormatIds`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/barcode-format-ids.html) |
| `barcodeFormatIds_2` | [`barcodeFormatIds`]({{ site.dbr_cpp_api }}simplified-barcode-reader-settings.html#barcodeformatids) | [`BarcodeReaderTaskSetting.BarcodeFormatIds`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/barcode-format-ids.html) |
| `deblurModes` | [`deblurModes`]({{ site.dbr_cpp_api }}simplified-barcode-reader-settings.html#deblurmodes) | [`BarcodeReaderTaskSetting.DeblurModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/deblur-modes.html) |
| `deblurLevel` | [`deblurModes`]({{ site.dbr_cpp_api }}simplified-barcode-reader-settings.html#deblurmodes) | [`BarcodeReaderTaskSetting.DeblurModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/deblur-modes.html) |
| `maxAlgorithmThreadCount` | [`maxThreadsInOneTask`]({{ site.dbr_cpp_api }}simplified-barcode-reader-settings.html#maxthreadsinonetask) | [`BarcodeReaderTaskSetting.MaxThreadsInOneTask`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/max-threads-in-one-task.html) |

> Remarks:
>
> * The 2 groups of barcode formats are merged.
> * `DeblurLevel` is deprecated. You can use `DeblurModes` instead.

| FurtherModes Property | SimplifiedBarcodeReaderSettings Property | Template File Parameter |
| ---------------------- | ----------------------------------------- | ----------------------- |
| `grayscaleTransformationModes` | [`grayscaleTransformationModes`]({{ site.dbr_cpp_api }}simplified-barcode-reader-settings.html#grayscaletransformationmodes) | [`ImageParameter.GrayscaleTransformationModes`]({{ site.dcvb_parameters_reference }}image-parameter/grayscale-enhancement-modes.html) |
| `imagePreprocessingModes` | [`grayscaleEnhancementModes`]({{ site.dbr_cpp_api }}simplified-barcode-reader-settings.html#grayscaleenhancementmodes) | [`ImageParameter.GrayscaleEnhancementModes`]({{ site.dcvb_parameters_reference }}image-parameter/grayscale-transformation-modes.html) |

> Remarks: The mode `IPM_MORPHOLOGY` of `imagePreprocessingModes` is migrated to `BinarizationModes`. The mode arguments `MorphOperation`, `MorphOperationKernelSizeX`, `MorphOperationKernelSizeY`, `MorphShape` are now available for all modes of `BinarizationModes`.

#### Migrate to Template File

The following properties can only be set via a template file. Please [contact us](https://www.dynamsoft.com/company/customer-service/#contact){:target="_blank"} so that we can help you to transform your current settings to a new template file.

| PublicRuntimeSettings Property | Template File Parameter |
| ------------------------------- | ----------------------- |
| `scaleDownThreshold` | [`ImageParameter.ScaleDownThreshold`]({{ site.dcvb_parameters_reference }}image-parameter/scale-down-threshold.html) |
| `binarizationModes` | [`ImageParameter.BinarizationModes`]({{ site.dcvb_parameters_reference }}image-parameter/binarization-modes.html) |
| `textResultOrderModes` | [`BarcodeReaderTaskSetting.TextResultOrderModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/text-result-order-modes.html) |
| `returnBarcodeZoneClarity` | [`BarcodeReaderTaskSetting.ReturnBarcodeZoneClarity`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/return-barcode-zone-clarity.html) |
| `scaleUpModes` | [`ImageParameter.ScaleUpModes`]({{ site.dcvb_parameters_reference }}image-parameter/scale-up-modes.html) |
| `barcodeZoneMinDistanceToImageBorders` | [`BarcodeFormatSpecification.BarcodeZoneMinDistanceToImageBorders`]({{ site.dcvb_parameters_reference }}barcode-format-specification/barcode-zone-min-distance-to-image-borders.html) |
| `terminatePhase` | [`BarcodeReaderTaskSetting.TerminateSettings`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/terminate-setting.html) |

| FurtherModes Property | Template File Parameter |
| ---------------------- | ----------------------- |
| `colourConversionModes` | [`ImageParameter.ColourConversionModes`]({{ site.dcvb_parameters_reference }}image-parameter/colour-conversion-modes.html) |
| `regionPredetectionModes` | [`ImageParameter.RegionPredetectionModes`]({{ site.dcvb_parameters_reference }}image-parameter/region-predetection-modes.html) |
| `textureDetectionModes` | [`ImageParameter.TextureDetectionModes`]({{ site.dcvb_parameters_reference }}image-parameter/texture-detection-modes.html) |
| `textFilterModes` | [`ImageParameter.TextDetectionMode`]({{ site.dcvb_parameters_reference }}image-parameter/text-detection-mode.html) & [`ImageParameter.IfEraseTextZone`]({{ site.dcvb_parameters_reference }}image-parameter/if-erase-text-zone.html) |
| `dpmCodeReadingModes` | [`BarcodeReaderTaskSetting.DPMCodeReadingModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/dpm-code-reading-modes.html) |
| `deformationResistingModes` | [`BarcodeReaderTaskSetting.DeformationResistingModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/deformation-resisting-modes.html) |
| `barcodeComplementModes` | [`BarcodeReaderTaskSetting.BarcodeComplementModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/barcode-complement-modes.html) |
| `barcodeColourModes` | [`BarcodeReaderTaskSetting.BarcodeColourModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/barcode-colour-modes.html) |

#### Migrate to Other APIs

The PDF properties of PublicRuntimeSettings are moved to set via the `setPDFReadingParameter` method of `CDirectoryFetcher` and `CFileFetcher` with a [`CPDFReadingParameter`]({{ site.dcvb_cpp_api }}core/basic-structures/pdf-reading-parameter.html) parameter.

| PublicRuntimeSettings Property |
| --------------------------------------- |
| `pdfReadingMode` |
| `pdfRasterDPI` |

The `Intermediate Result` system is redesigned and the following properties are deprecated.

| PublicRuntimeSettings Property |
| --------------------- |
| `intermediateResultTypes` |
| `intermediateResultSavingMode` |

#### Removed

The following properties are removed.

| PublicRuntimeSettings Property|
| --------------------- |
| `resultCoordinateType` |

| FurtherModes Property|
| --------------------- |
| `colourClusteringModes` |
