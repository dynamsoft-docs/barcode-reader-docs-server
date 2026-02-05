---
title: Migrate from v9.x to v11.x - Dynamsoft Barcode Reader SDK C++ Edition
keywords: c++, cplusplus, upgrade, migrate, v9, v11
description: This page introduces how to migrate Dynamsoft Barcode Reader SDK C++ Edition from version 9.x to 11.x
needAutoGenerateSidebar: true
needGenerateH3Content: true
---

# Migrate from 9.x to 11.x

Dynamsoft Barcode Reader SDK has been refactored to integrate with the [`DynamsoftCaptureVision (DCV)`]({{ site.dcvb_architecture }}) architecture since version 10.0. This guide helps you upgrade from version 9.x by highlighting the key API changes and providing migration paths.

The actual migration effort depends on which APIs you currently use. In many cases, only the interfaces you actively use need to be updated — review the sections below to identify the changes that affect your integration.

> [!NOTE]
> If you are new to the DCV architecture and prefer to start fresh, refer to the [User Guide]({{site.dbr_cpp}}user-guide.html) for a quick-start tutorial.

## Update the License Key

You may need to update your license key before upgrading to version 11.x.

- **30-Day Free Trial License**: Visit the [Request a Trial License](https://www.dynamsoft.com/customer/license/trialLicense?product=dbr&utm_source=docs){:target="_blank"} page to obtain a free license for evaluation.
- **Annual Online Full License**: Your license will continue to work with the new SDK version. Go to <a href="https://www.dynamsoft.com/customer/license/fullLicense" target="_blank">Customer Portal</a> to get your license key.
- **Perpetual License**: Please contact our [sales team](https://www.dynamsoft.com/contact/){:target="_blank"} to update your license.

## Migrate Project Configuration

Since the SDK architecture has changed, you need to update your project configuration including headers, libraries, and runtime files.

### Update Headers and Libraries

```cpp
#include "[INSTALLATION FOLDER]/Include/DynamsoftCaptureVisionRouter.h"

using namespace std;
using namespace dynamsoft::license;
using namespace dynamsoft::cvr;
using namespace dynamsoft::dbr;
using namespace dynamsoft::utility;

#if defined(_WIN64) || defined(_WIN32)
    #ifdef _WIN64
        #pragma comment(lib, "[INSTALLATION FOLDER]/Dist/Lib/Windows/x64/DynamsoftCorex64.lib")
        #pragma comment(lib, "[INSTALLATION FOLDER]/Dist/Lib/Windows/x64/DynamsoftLicensex64.lib")
        #pragma comment(lib, "[INSTALLATION FOLDER]/Dist/Lib/Windows/x64/DynamsoftCaptureVisionRouterx64.lib")
        #pragma comment(lib, "[INSTALLATION FOLDER]/Dist/Lib/Windows/x64/DynamsoftUtilityx64.lib")
    #else
        #pragma comment(lib, "[INSTALLATION FOLDER]/Dist/Lib/Windows/x86/DynamsoftCorex86.lib")
        #pragma comment(lib, "[INSTALLATION FOLDER]/Dist/Lib/Windows/x86/DynamsoftLicensex86.lib")
        #pragma comment(lib, "[INSTALLATION FOLDER]/Dist/Lib/Windows/x86/DynamsoftCaptureVisionRouterx86.lib")
        #pragma comment(lib, "[INSTALLATION FOLDER]/Dist/Lib/Windows/x86/DynamsoftUtilityx86.lib")
    #endif
#endif
```

### Deploy Runtime Files

- Copy the folders `Templates` and `Models` under `[INSTALLATION FOLDER]/Dist/` to the same folder as the executable program.
- Copy the libraries to the same folder as the executable program.
  - For Windows: Copy **ALL** `*.dll` files under `[INSTALLATION FOLDER]/Dist/Lib/Windows/[platform]`. Replace `[platform]` with your project's platform setting.
  - For Linux: Copy **ALL** `*.so` files under `[INSTALLATION FOLDER]/Dist/Lib/Linux/[platform]`. Replace `[platform]` with your project's platform setting.

## Migrate License Activation Code

Starting from 10.0, we have unified the API for setting licenses across different Dynamsoft products.

| Old APIs | New APIs |
| :----------- | :------- |
| `CBarcodeReader.InitLicense` | [CLicenseManager.InitLicense]({{ site.dcvb_cpp_api }}license/license-manager.html#initlicense) |

## Migrate Decoding APIs

### Single Image Decoding

The APIs for decoding single image have been adjusted as follows:

| Old APIs | New APIs |
| :----------- | :------- |
| `CBarcodeReader.DecodeFile` | [CCaptureVisionRouter.Capture]({{ site.dcvb_cpp_api }}capture-vision-router/single-file-processing.html#capture) or [CCaptureVisionRouter.CaptureMultiPages]({{ site.dcvb_cpp_api }}capture-vision-router/single-file-processing.html#capturemultipages) |
| `CBarcodeReader.DecodeFileInMemory` | [CCaptureVisionRouter.Capture]({{ site.dcvb_cpp_api }}capture-vision-router/single-file-processing.html#capture) or [CCaptureVisionRouter.CaptureMultiPages]({{ site.dcvb_cpp_api }}capture-vision-router/single-file-processing.html#capturemultipages) |
| `CBarcodeReader.DecodeBuffer` | [CCaptureVisionRouter.Capture]({{ site.dcvb_cpp_api }}capture-vision-router/single-file-processing.html#capture) |
| `struct TextResult` | [class CBarcodeResultItem]({{ site.dbr_cpp_api }}barcode-result-item.html) |
| `struct TextResultArray` | [class CCapturedResult]({{ site.dcvb_cpp_api }}capture-vision-router/auxiliary-classes/captured-result.html) |
| `CBarcodeReader.DecodeBase64String` | [CImageIO.ReadFromBase64String]({{ site.dcvb_cpp_api }}utility/image-io.html#readfrombase64string) + [CCaptureVisionRouter.Capture]({{ site.dcvb_cpp_api }}capture-vision-router/single-file-processing.html#capture) |
| `CBarcodeReader.DecodeDIB` | **Not available**. |

### Video Streaming Decoding

`CImageSourceAdapter` is added to replace the `FrameDecodingParameters` and the previous video methods. You should implement `CImageSourceAdapter` to transfer image data from camera or video file to buffer. The following code snippet demonstrates basic usage of decoding video frames:

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
    virtual void OnDecodedBarcodesReceived(CDecodedBarcodesResult* result) {
        // Add code to process the result
    }
};

int main()
{
    CCaptureVisionRouter *cvRouter = new CCaptureVisionRouter;

    // Create your video source and bind it to the router
    MyVideoSource *source = new MyVideoSource;
    cvRouter->SetInput(source);

    // Create a CCapturedResultReceiver instance 
    MyBarcodeResultReceiver *barcodesReceiver = new MyBarcodeResultReceiver;
    cvRouter->AddResultReceiver(barcodesReceiver);

    // Start capturing
    char errorMsg[512] = {0};
    int errorCode = cvRouter->StartCapturing(CPresetTemplate::PT_READ_BARCODES, true, errorMsg, 512);

    delete barcodesReceiver;
    delete source;
    delete cvRouter;
}
```

## Upgrade Template Files

The template file format has changed in the new version. Templates created for version 9.x are not compatible with version 11.x. Use the <a href="https://www.dynamsoft.com/tools/template-upgrade/" target="_blank">Template Upgrade Tool</a> to automatically convert your existing templates to the new format.


## Migrate Template APIs

The template-based APIs have been updated as follows:

| Old APIs | New APIs |
| :----------- | :------- |
| `CBarcodeReader.InitRuntimeSettingsWithFile` | [CCaptureVisionRouter.InitSettingsFromFile]({{ site.dcvb_cpp_api }}capture-vision-router/settings.html#initsettingsfromfile) |
| `CBarcodeReader.InitRuntimeSettingsWithString` | [CCaptureVisionRouter.InitSettings]({{ site.dcvb_cpp_api }}capture-vision-router/settings.html#initsettings) |
| `CBarcodeReader.OutputSettingsToFile` | [CCaptureVisionRouter.OutputSettingsToFile]({{ site.dcvb_cpp_api }}capture-vision-router/settings.html#outputsettingstofile) |
| `CBarcodeReader.OutputSettingsToString` | [CCaptureVisionRouter.OutputSettings]({{ site.dcvb_cpp_api }}capture-vision-router/settings.html#outputsettings) |
| `CBarcodeReader.ResetRuntimeSettings` | [CCaptureVisionRouter.ResetSettings]({{ site.dcvb_cpp_api }}capture-vision-router/settings.html#resetsettings) |
| `CBarcodeReader.AppendTplFileToRuntimeSettings` | **Not available**. |
| `CBarcodeReader.AppendTplStringToRuntimeSettings` | **Not available**. |

## Migrate Runtime Settings

The struct `PublicRuntimeSettings` has been refactored. It retains commonly used properties while removing the previously complex property settings, which are now exclusively supported through templates.

The APIs for accessing and updating `PublicRuntimeSettings` have been adjusted as follows:

| Old APIs | New APIs |
| :----------- | :------- |
| `CBarcodeReader.GetRuntimeSettings` | [CCaptureVisionRouter.GetSimplifiedSettings]({{ site.dcvb_cpp_api }}capture-vision-router/settings.html#getsimplifiedsettings) |
| `CBarcodeReader.UpdateRuntimeSettings` | [CCaptureVisionRouter.UpdateSettings]({{ site.dcvb_cpp_api }}capture-vision-router/settings.html#updatesettings) |

### Properties with Direct API Replacement

The following properties are replaced by similar properties under `SimplifiedCaptureVisionSettings` or `SimplifiedBarcodeReaderSettings`. They can also be set via a template file.

#### SimplifiedCaptureVisionSettings

| PublicRuntimeSettings Property | SimplifiedCaptureVisionSettings Parameter | Template File Parameter |
| ------------------------------- | ----------------------------------------- | ----------------------- |
| `region` | [`roi`]({{ site.dcvb_cpp_api }}capture-vision-router/structs/simplified-capture-vision-settings.html#roi) & [`roiMeasuredInPercentage`]({{ site.dcvb_cpp_api }}capture-vision-router/structs/simplified-capture-vision-settings.html#roimeasuredinpercentage) | [`TargetROIDef.Location.Offset`]({{ site.dcvb_parameters_reference }}target-roi-def/location.html) |
| `timeout` | [`timeout`]({{ site.dcvb_cpp_api }}capture-vision-router/structs/simplified-capture-vision-settings.html#timeout) | [`CaptureVisionTemplates.Timeout`]({{ site.dcvb_parameters_reference }}capture-vision-template/timeout.html) |

#### SimplifiedBarcodeReaderSettings

| PublicRuntimeSettings Property | SimplifiedBarcodeReaderSettings Property | Template File Parameter |
| ------------------------------- | ----------------------------------------- | ----------------------- |
| `minBarcodeTextLength` | [`minBarcodeTextLength`]({{ site.dbr_cpp_api }}simplified-barcode-reader-settings.html#minbarcodetextlength) | [`BarcodeFormatSpecification.BarcodeTextLengthRangeArray`]({{ site.dcvb_parameters_reference }}barcode-format-specification/barcode-text-length-range-array.html) |
| `minResultConfidence` | [`minResultConfidence`]({{ site.dbr_cpp_api }}simplified-barcode-reader-settings.html#minresultconfidence) | [`BarcodeFormatSpecification.MinResultConfidence`]({{ site.dcvb_parameters_reference }}barcode-format-specification/min-result-confidence.html) |
| `localizationModes` | [`localizationModes`]({{ site.dbr_cpp_api }}simplified-barcode-reader-settings.html#localizationmodes) | [`BarcodeReaderTaskSetting.LocalizationModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/localization-modes.html) |
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
| `grayscaleTransformationModes` | [`grayscaleTransformationModes`]({{ site.dbr_cpp_api }}simplified-barcode-reader-settings.html#grayscaletransformationmodes) | [`ImageParameter.GrayscaleTransformationModes`]({{ site.dcvb_parameters_reference }}image-parameter/grayscale-transformation-modes.html) |
| `imagePreprocessingModes` | [`grayscaleEnhancementModes`]({{ site.dbr_cpp_api }}simplified-barcode-reader-settings.html#grayscaleenhancementmodes) | [`ImageParameter.GrayscaleEnhancementModes`]({{ site.dcvb_parameters_reference }}image-parameter/grayscale-enhancement-modes.html) |

> Remarks: The mode `IPM_MORPHOLOGY` of `imagePreprocessingModes` is migrated to `BinarizationModes`. The mode arguments `MorphOperation`, `MorphOperationKernelSizeX`, `MorphOperationKernelSizeY`, `MorphShape` are now available for all modes of `BinarizationModes`.

### Properties Requiring Template File

The following properties can only be set via a template file. Please call `CBarcodeReader.OutputSettingsToFile` first with the old version to export the settings and then use the <a href="https://www.dynamsoft.com/tools/template-upgrade/" target="_blank">template upgrade tool</a> to upgrade your template.

| PublicRuntimeSettings Property | Template File Parameter |
| ------------------------------- | ----------------------- |
| `scaleDownThreshold` | [`ImageParameter.ImageScaleSettings`]({{ site.dcvb_parameters_reference }}image-parameter/image-scale-settings.html) |
| `binarizationModes` | [`ImageParameter.BinarizationModes`]({{ site.dcvb_parameters_reference }}image-parameter/binarization-modes.html) |
| `textResultOrderModes` | [`BarcodeReaderTaskSetting.TextResultOrderModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/text-result-order-modes.html) |
| `returnBarcodeZoneClarity` | [`BarcodeReaderTaskSetting.ReturnBarcodeZoneClarity`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/return-barcode-zone-clarity.html) |
| `scaleUpModes` | [`BarcodeReaderTaskSetting.BarcodeScaleModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/barcode-scale-modes.html) |
| `barcodeZoneMinDistanceToImageBorders` | [`BarcodeFormatSpecification.BarcodeZoneMinDistanceToImageBorders`]({{ site.dcvb_parameters_reference }}barcode-format-specification/barcode-zone-min-distance-to-image-borders.html) |

| FurtherModes Property | Template File Parameter |
| ---------------------- | ----------------------- |
| `colourConversionModes` | [`ImageParameter.ColourConversionModes`]({{ site.dcvb_parameters_reference }}image-parameter/colour-conversion-modes.html) |
| `regionPredetectionModes` | [`BarcodeReaderTaskSetting.RegionPredetectionModes`]({{ site.dcvb_parameters_reference }}image-parameter/region-predetection-modes.html) |
| `textureDetectionModes` | [`ImageParameter.TextureDetectionModes`]({{ site.dcvb_parameters_reference }}image-parameter/texture-detection-modes.html) |
| `textFilterModes` | [`ImageParameter.TextDetectionMode`]({{ site.dcvb_parameters_reference }}image-parameter/text-detection-mode.html) & [`ImageParameter.IfEraseTextZone`]({{ site.dcvb_parameters_reference }}image-parameter/if-erase-text-zone.html) |
| `dpmCodeReadingModes` | [`BarcodeReaderTaskSetting.DPMCodeReadingModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/dpm-code-reading-modes.html) |
| `deformationResistingModes` | [`BarcodeReaderTaskSetting.DeformationResistingModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/deformation-resisting-modes.html) |
| `barcodeComplementModes` | [`BarcodeReaderTaskSetting.BarcodeComplementModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/barcode-complement-modes.html) |

### Properties Migrated to Other APIs

The PDF properties of PublicRuntimeSettings are moved to set via the `setPDFReadingParameter` method of `CDirectoryFetcher` and `CFileFetcher` with a [`CPDFReadingParameter`]({{ site.dcvb_cpp_api }}core/basic-structures/pdf-reading-parameter.html) parameter.

| PublicRuntimeSettings Property |
| --------------------------------------- |
| `pdfReadingMode` |
| `pdfRasterDPI` |

### Removed Properties (No Replacement)

The following properties are removed.

| PublicRuntimeSettings Property|
| --------------------- |
| `barcodeColourModes` |
| `intermediateResultTypes` |
| `intermediateResultSavingMode` |
| `resultCoordinateType` |
| `terminatePhase` |

| FurtherModes Property|
| --------------------- |
| `colourClusteringModes` |
