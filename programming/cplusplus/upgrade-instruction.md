---
title: Upgrade Instructions - Dynamsoft Barcode Reader C++ Edition
keywords: c++, cplusplus, upgrade
description: This page introduces how to upgrade Dynamsoft Barcode Reader
needAutoGenerateSidebar: true
needGenerateH3Content: true
permalink: /programming/cplusplus/upgrade-instruction.html
---

# How to Upgrade

## From version 9.x or earlier to version 10.x

Dynamsoft Barcode Reader SDK has been refactored to integrate with [`DynamsoftCaptureVision (DCV)`]({{ site.dcv_introduction }}) architecture. To upgrade from version 9.x or earlier to 10.x, we recommend you to follow the [User Guide]({{site.cpp}}user-guide.html) and re-write your codes.

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
| `region` | [`roi`]({{ site.dcv_cpp_api }}capture-vision-router/structs/simplified-capture-vision-settings.html#roi) & [`roiMeasuredInPercentage`]({{ site.dcv_cpp_api }}capture-vision-router/structs/simplified-capture-vision-settings.html#roimeasuredinpercentage) | [`TargetROIDef.Location.Offset`]({{ site.dcv_parameters_reference }}target-roi-def/location.html?product=dbr&repoType=core){:target="_blank"} |
| `timeout` | [`timeout`]({{ site.dcv_cpp_api }}capture-vision-router/structs/simplified-capture-vision-settings.html#timeout) | [`CaptureVisionTemplates.Timeout`]({{ site.dcv_parameters_reference }}capture-vision-template/timeout.html?product=dbr&repoType=core){:target="_blank"} |

#### Migrate to SimplifiedBarcodeReaderSettings

The following properties are replaced by similar properties under `SimplifiedBarcodeReaderSettings`. The majority of them can also be set via a template file(String).

| PublicRuntimeSettings Property | SimplifiedBarcodeReaderSettings Property | Template File Parameter |
| ------------------------------- | ----------------------------------------- | ----------------------- |
| `minBarcodeTextLength` | [`minBarcodeTextLength`]({{ site.cpp_api }}simplified-barcode-reader-settings.html#minbarcodetextlength) | [`BarcodeFormatSpecification.BarcodeTextLengthRangeArray`]({{ site.dcv_parameters_reference }}barcode-format-specification/barcode-text-length-range-array.html?product=dbr&repoType=core){:target="_blank"} |
| `minResultConfidence` | [`minResultConfidence`]({{ site.cpp_api }}simplified-barcode-reader-settings.html#minresultconfidence) | [`BarcodeFormatSpecification.MinResultConfidence`]({{ site.dcv_parameters_reference }}barcode-format-specification/min-result-confidence.html?product=dbr&repoType=core){:target="_blank"} |
| `localizationModes` | [`localizationModes`]({{ site.cpp_api }}simplified-barcode-reader-settings.html#localizationmodes) | [`BarcodeReaderTaskSetting.LocationModes`]({{ site.dcv_parameters_reference }}barcode-reader-task-settings/localization-modes.html?product=dbr&repoType=core){:target="_blank"} |
| `expectedBarcodesCount` | [`expectedBarcodesCount`]({{ site.cpp_api }}simplified-barcode-reader-settings.html#expectedbarcodescount) | [`BarcodeReaderTaskSetting.ExpectedBarcodesCount`]({{ site.dcv_parameters_reference }}barcode-reader-task-settings/expected-barcodes-count.html?product=dbr&repoType=core){:target="_blank"} |
| `barcodeFormatIds` | [`barcodeFormatIds`]({{ site.cpp_api }}simplified-barcode-reader-settings.html#barcodeformatids) | [`BarcodeReaderTaskSetting.BarcodeFormatIds`]({{ site.dcv_parameters_reference }}barcode-reader-task-settings/barcode-format-ids.html?product=dbr&repoType=core){:target="_blank"} |
| `barcodeFormatIds_2` | [`barcodeFormatIds`]({{ site.cpp_api }}simplified-barcode-reader-settings.html#barcodeformatids) | [`BarcodeReaderTaskSetting.BarcodeFormatIds`]({{ site.dcv_parameters_reference }}barcode-reader-task-settings/barcode-format-ids.html?product=dbr&repoType=core){:target="_blank"} |
| `deblurModes` | [`deblurModes`]({{ site.cpp_api }}simplified-barcode-reader-settings.html#deblurmodes) | [`BarcodeReaderTaskSetting.DeblurModes`]({{ site.dcv_parameters_reference }}barcode-reader-task-settings/deblur-modes.html?product=dbr&repoType=core){:target="_blank"} |
| `deblurLevel` | [`deblurModes`]({{ site.cpp_api }}simplified-barcode-reader-settings.html#deblurmodes) | [`BarcodeReaderTaskSetting.DeblurModes`]({{ site.dcv_parameters_reference }}barcode-reader-task-settings/deblur-modes.html?product=dbr&repoType=core){:target="_blank"} |
| `maxAlgorithmThreadCount` | [`maxThreadsInOneTask`]({{ site.cpp_api }}simplified-barcode-reader-settings.html#maxthreadsinonetask) | [`BarcodeReaderTaskSetting.MaxThreadsInOneTask`]({{ site.dcv_parameters_reference }}barcode-reader-task-settings/max-threads-in-one-task.html?product=dbr&repoType=core){:target="_blank"} |

> Remarks:
>
> * The 2 groups of barcode formats are merged.
> * `DeblurLevel` is deprecated. You can use `DeblurModes` instead.

| FurtherModes Property | SimplifiedBarcodeReaderSettings Property | Template File Parameter |
| ---------------------- | ----------------------------------------- | ----------------------- |
| `grayscaleTransformationModes` | [`grayscaleTransformationModes`]({{ site.cpp_api }}simplified-barcode-reader-settings.html#grayscaletransformationmodes) | [`ImageParameter.GrayscaleTransformationModes`]({{ site.dcv_parameters_reference }}image-parameter/grayscale-enhancement-modes.html?product=dbr&repoType=core){:target="_blank"} |
| `imagePreprocessingModes` | [`grayscaleEnhancementModes`]({{ site.cpp_api }}simplified-barcode-reader-settings.html#grayscaleenhancementmodes) | [`ImageParameter.GrayscaleEnhancementModes`]({{ site.dcv_parameters_reference }}image-parameter/grayscale-transformation-modes.html?product=dbr&repoType=core){:target="_blank"} |

> Remarks: The mode `IPM_MORPHOLOGY` of `imagePreprocessingModes` is migrated to `BinarizationModes`. The mode arguments `MorphOperation`, `MorphOperationKernelSizeX`, `MorphOperationKernelSizeY`, `MorphShape` are now available for all modes of `BinarizationModes`.

#### Migrate to Template File

The following properties can only be set via a template file. Please [contact us](https://www.dynamsoft.com/company/customer-service/#contact){:target="_blank"} so that we can help you to transform your current settings to a new template file.

| PublicRuntimeSettings Property | Template File Parameter |
| ------------------------------- | ----------------------- |
| `scaleDownThreshold` | [`ImageParameter.ScaleDownThreshold`]({{ site.dcv_parameters_reference }}image-parameter/scale-down-threshold.html?product=dbr&repoType=core){:target="_blank"} |
| `binarizationModes` | [`ImageParameter.BinarizationModes`]({{ site.dcv_parameters_reference }}image-parameter/binarization-modes.html?product=dbr&repoType=core){:target="_blank"} |
| `textResultOrderModes` | [`BarcodeReaderTaskSetting.TextResultOrderModes`]({{ site.dcv_parameters_reference }}barcode-reader-task-settings/text-result-order-modes.html?product=dbr&repoType=core){:target="_blank"} |
| `returnBarcodeZoneClarity` | [`BarcodeReaderTaskSetting.ReturnBarcodeZoneClarity`]({{ site.dcv_parameters_reference }}barcode-reader-task-settings/return-barcode-zone-clarity.html?product=dbr&repoType=core){:target="_blank"} |
| `scaleUpModes` | [`ImageParameter.ScaleUpModes`]({{ site.dcv_parameters_reference }}image-parameter/scale-up-modes.html?product=dbr&repoType=core){:target="_blank"} |
| `barcodeZoneMinDistanceToImageBorders` | [`BarcodeFormatSpecification.BarcodeZoneMinDistanceToImageBorders`]({{ site.dcv_parameters_reference }}barcode-format-specification/barcode-zone-min-distance-to-image-borders.html?product=dbr&repoType=core){:target="_blank"} |
| `terminatePhase` | [`BarcodeReaderTaskSetting.TerminateSettings`]({{ site.dcv_parameters_reference }}barcode-reader-task-settings/terminate-setting.html?product=dbr&repoType=core){:target="_blank"} |

| FurtherModes Property | Template File Parameter |
| ---------------------- | ----------------------- |
| `colourConversionModes` | [`ImageParameter.ColourConversionModes`]({{ site.dcv_parameters_reference }}image-parameter/colour-conversion-modes.html?product=dbr&repoType=core){:target="_blank"} |
| `regionPredetectionModes` | [`ImageParameter.RegionPredetectionModes`]({{ site.dcv_parameters_reference }}image-parameter/region-predetection-modes.html?product=dbr&repoType=core){:target="_blank"} |
| `textureDetectionModes` | [`ImageParameter.TextureDetectionModes`]({{ site.dcv_parameters_reference }}image-parameter/texture-detection-modes.html?product=dbr&repoType=core){:target="_blank"} |
| `textFilterModes` | [`ImageParameter.TextDetectionMode`]({{ site.dcv_parameters_reference }}image-parameter/text-detection-mode.html?product=dbr&repoType=core){:target="_blank"} & [`ImageParameter.IfEraseTextZone`]({{ site.dcv_parameters_reference }}image-parameter/if-erase-text-zone.html?product=dbr&repoType=core){:target="_blank"} |
| `dpmCodeReadingModes` | [`BarcodeReaderTaskSetting.DPMCodeReadingModes`]({{ site.dcv_parameters_reference }}barcode-reader-task-settings/dpm-code-reading-modes.html?product=dbr&repoType=core){:target="_blank"} |
| `deformationResistingModes` | [`BarcodeReaderTaskSetting.DeformationResistingModes`]({{ site.dcv_parameters_reference }}barcode-reader-task-settings/deformation-resisting-modes.html?product=dbr&repoType=core){:target="_blank"} |
| `barcodeComplementModes` | [`BarcodeReaderTaskSetting.BarcodeComplementModes`]({{ site.dcv_parameters_reference }}barcode-reader-task-settings/barcode-complement-modes.html?product=dbr&repoType=core){:target="_blank"} |
| `barcodeColourModes` | [`BarcodeReaderTaskSetting.BarcodeColourModes`]({{ site.dcv_parameters_reference }}barcode-reader-task-settings/barcode-colour-modes.html?product=dbr&repoType=core){:target="_blank"} |

#### Migrate to Other APIs

The PDF properties of PublicRuntimeSettings are moved to set via the `setPDFReadingParameter` method of `CDirectoryFetcher` and `CFileFetcher` with a [`CPDFReadingParameter`]({{ site.dcv_cpp_api }}core/basic-structures/pdf-reading-parameter.html) parameter.

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
