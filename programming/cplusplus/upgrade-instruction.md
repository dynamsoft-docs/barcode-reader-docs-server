---
title: Upgrade Instructions - Dynamsoft Barcode Reader SDK C++ Edition
keywords: c++, cplusplus, upgrade
description: This page introduces how to upgrade Dynamsoft Barcode Reader SDK C++ Edition
needAutoGenerateSidebar: true
needGenerateH3Content: true
---

# How to Upgrade to Version 11.x

## From version 10.x

To upgrade from version 10.x to 11.x, we recommend you to take the following steps.

### 1. Update the License Key

#### Request a 30-Day Free Trial License

Visit the [Request a Trial License](https://www.dynamsoft.com/customer/license/trialLicense?product=dbr&utm_source=docs){:target="_blank"} page to obtain a 30-day free license. This option is ideal for initial evaluation or testing of new SDK features.

#### Annual Online Full License

If you are using an Annual Online Full License, your license will continue to work with the current SDK version without the need for updates. Go to <a href="https://www.dynamsoft.com/customer/license/fullLicense" target="_blank">Customer Portal</a> to get your license key.

#### Perpetual License

For users with a Perpetual License, please contact our sales team to update your license. You can reach out through our [Contacting Us](https://www.dynamsoft.com/contact/){:target="_blank"} page for assistance.

### 2. Update the Assembly Files

<a href="https://www.dynamsoft.com/barcode-reader/downloads/" target="_blank">Download the latest SDK package</a> and update the relevant header and library files. Please note the following changes:

- **Directory Structure Change**: The `Distributables` directory has been renamed to `Dist` in the extracted package.
- **vcomp140.dll Removed**: This DLL is no longer provided in the package. If your application depends on it, ensure it is available in your system environment.

### 3. Migrate Your Templates

The template system is upgraded. The template you used for the previous version can't be directly recognized by the new version. Please use the <a href="https://www.dynamsoft.com/tools/template-upgrade/" target="_blank">template upgrade tool</a> to upgrade your template.

### 4. Rebuild the Project

After updating the SDK files, clean and rebuild your project to ensure all dependencies are properly linked and to avoid potential compatibility issues.


## From version 9.x or earlier

Dynamsoft Barcode Reader SDK has been refactored to integrate with [`DynamsoftCaptureVision (DCV)`]({{ site.dcvb_architecture }}) architecture since version 10. To upgrade from version 9.x or earlier to 11.x, we recommend you to follow the [User Guide]({{site.dbr_cpp}}user-guide.html) and re-write your codes. This section highlights only the key changes and necessary actions for upgrading the SDK.

### Update the License Key

#### Request a 30-Day Free Trial License

Visit the [Request a Trial License](https://www.dynamsoft.com/customer/license/trialLicense?product=dbr&utm_source=docs){:target="_blank"} page to obtain a 30-day free license. This option is ideal for initial evaluation or testing of new SDK features.

#### Annual Online Full License

If you are using an Annual Online Full License, your license will continue to work with the current SDK version without the need for updates. Go to <a href="https://www.dynamsoft.com/customer/license/fullLicense" target="_blank">Customer Portal</a> to get your license key.

#### Perpetual License

For users with a Perpetual License, please contact our sales team to update your license. You can reach out through our [Contacting Us](https://www.dynamsoft.com/contact/){:target="_blank"} page for assistance.

### Update the Included Headers, Libs & DLLs

Since the SDK architecture is changed, you have to change your code for including the headers, libs and DLLs. You can use the following code to replace your previous code.

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

**Distribution**

- Copy `[INSTALLATION FOLDER]/Dist/Templates/DBR-PresetTemplates.json` to the same folder as the executable program.
- Copy the libraries to the same folder as the executable program.
  - For Windows: Copy **ALL** `*.dll` files under `[INSTALLATION FOLDER]/Dist/Lib/Windows/[platform]`. Replace `[platform]` with your project's platform setting.
  - For Linux: Copy **ALL** `*.so` files under `[INSTALLATION FOLDER]/Dist/Lib/Linux/[platform]`. Replace `[platform]` with your project's platform setting.

### Update the License Activation Code

Starting from 10.0, we have unified the API for setting licenses across different Dynamsoft products.

| Old APIs | New APIs |
| :----------- | :------- |
| `CBarcodeReader.InitLicense` | `CLicenseManager.InitLicense` |

### Update Single Image Decoding APIs

The APIs for decoding single image have been adjusted as follows:

| Old APIs | New APIs |
| :----------- | :------- |
| `CBarcodeReader.DecodeFile` | [CCaptureVisionRouter.Capture(const char* filePath, const char* templateName)]({{ site.dcvb_cpp_api }}capture-vision-router/single-file-processing.html#capture) |
| `CBarcodeReader.DecodeFileInMemory` | [CCaptureVisionRouter.Capture(const unsigned char *fileBytes, int fileSize, const char* templateName)]({{ site.dcvb_cpp_api }}capture-vision-router/single-file-processing.html#capture) |
| `CBarcodeReader.DecodeBuffer` | [CCaptureVisionRouter.Capture(const CImageData* pImageData, const char* templateName)]({{ site.dcvb_cpp_api }}capture-vision-router/single-file-processing.html#capture) |
| `struct TextResult` | [class CBarcodeResultItem]({{ site.dbr_cpp_api }}barcode-result-item.html) |
| `struct TextResultArray` | [class CCapturedResult]({{ site.dcvb_cpp_api }}capture-vision-router/auxiliary-classes/captured-result.html) |
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
    CCaptureVisionRouter *cvRouter = new CCaptureVisionRouter;

    // Create your video source and bind it to the router
    MyVideoSource *source = new MyVideoSource;
    cvRouter->SetInput(source);

    // Create a CCapturedResultReceiver instance 
    MyBarcodeResultReceiver *barcodesReceiver = new MyCapturedResultReceiver;
    cvRouter->AddResultReceiver(barcodesReceiver);

    // Start capturing
    errorCode = cvRouter->StartCapturing(CPresetTemplate::PT_READ_BARCODES, true, errorMsg, 512);

    delete barcodesReceiver;
    delete source;
    delete cvRouter;
}
```

### Migrate Your Templates

The template system is upgraded. The template you used for the previous version can't be directly recognized by the new version. Please use the <a href="https://www.dynamsoft.com/tools/template-upgrade/" target="_blank">template upgrade tool</a> to upgrade your template.

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

### Migrate Your PublicRuntimeSettings

The struct `PublicRuntimeSettings` has been refactored. It retains commonly used properties while removing the previously complex property settings, which are now exclusively supported through templates.

The APIs for accessing and updating `PublicRuntimeSettings` have been adjusted as follows:

| Old APIs | New APIs |
| :----------- | :------- |
| `CBarcodeReader.GetRuntimeSettings` | [CCaptureVisionRouter.GetSimplifiedSettings]({{ site.dcvb_cpp_api }}capture-vision-router/settings.html#getsimplifiedsettings) |
| `CBarcodeReader.UpdateRuntimeSettings` | [CCaptureVisionRouter.UpdateSettings]({{ site.dcvb_cpp_api }}capture-vision-router/settings.html#updatesettings) |

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
| `barcodeColourModes` |
| `resultCoordinateType` |
| `terminatePhase` |

| FurtherModes Property|
| --------------------- |
| `colourClusteringModes` |
