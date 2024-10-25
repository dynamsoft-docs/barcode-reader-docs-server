---
title: Upgrade Instructions - Dynamsoft Barcode Reader SDK .NET Edition
keywords: .NET, upgrade
description: This page introduces how to upgrade Dynamsoft Barcode Reader SDK .NET Edition
needAutoGenerateSidebar: true
needGenerateH3Content: true
---

# How to Upgrade

## From version 9.x or earlier to version 10.x

Dynamsoft Barcode Reader SDK has been refactored to integrate with [`DynamsoftCaptureVision (DCV)`]({{ site.dcvb_architecture }}) architecture. To upgrade from version 9.x or earlier to 10.x, we recommend you to follow the [User Guide]({{ site.dbr_dotnet}}user-guide.html) and re-write your codes.


### Migrate to New Package

As of version 10.0, the nuget package `Dynamsoft.DotNet.Barcode` has been renamed to `Dynamsoft.DotNet.BarcodeReader.Bundle` to reflect changes in both architecture and API design. Start command prompt and run the following command to install the new package.

```
NuGet\Install-Package Dynamsoft.DotNet.BarcodeReader.Bundle
```

### Update the License Activation Code

Starting from 10.0, we have unified the API for setting licenses across different Dynamsoft products.

| Old APIs | New APIs |
| :----------- | :------- |
| `BarcodeReader.InitLicense` | `CLicenseManager.InitLicense` |

### Update Single Image Decoding APIs

The APIs for decoding single image has been adjusted as follows:

| Old APIs | New APIs |
| :----------- | :------- |
| `BarcodeReader.DecodeFile` | `CaptureVisionRouter.Capture(string filePath, string templateName="")` |
| `BarcodeReader.DecodeFileInMemory` | `CaptureVisionRouter.Capture(byte[] fileBytes, string templateName="")` |
| `BarcodeReader.DecodeBuffer` | `CaptureVisionRouter.Capture(ImageData imageData, string templateName="")` |
| `class TextResult` | `class BarcodeResultItem` |
| `BarcodeReader.DecodeBase64String` | **Currently not available**. |
| `BarcodeReader.DecodeBitmap` | **Currently not available**. |

### Update Video Streaming Decoding Code

`ImageSourceAdapter` is added to replace the `FrameDecodeingParameters` and the previous video methods. You should implement `ImageSourceAdapter` to transfer image data from camera or video file to buffer.


### Migrate Your Templates

The template system is upgraded. The template you used for the previous version can't be directly recognized by the new version. Please <a href="https://download2.dynamsoft.com/dcv/TemplateConverter.zip" target="_blank">download the TemplateConverter tool</a> or <a href="https://www.dynamsoft.com/company/customer-service/#contact" target="_blank">contact us</a> to upgrade your template.

The template-based APIs have been updated as follows:

| Old APIs | New APIs |
| :----------- | :------- |
| `BarcodeReader.InitRuntimeSettingsWithFile` | `CaptureVisionRouter.InitSettingsFromFile` |
| `BarcodeReader.InitRuntimeSettingsWithString` | `CaptureVisionRouter.InitSettings` |
| `BarcodeReader.OutputSettingsToFile` | `CaptureVisionRouter.OutputSettingsToFile` |
| `BarcodeReader.OutputSettingsToString` | `CaptureVisionRouter.OutputSettings` |
| `BarcodeReader.ResetRuntimeSettings` | `CaptureVisionRouter.ResetSettings` |
| `BarcodeReader.AppendTplFileToRuntimeSettings` | **Not available**. |
| `BarcodeReader.AppendTplStringToRuntimeSettings` | **Not available**. |
| `BarcodeReader.GetAllParameterTemplateNames` | **Not available**. |

### Migrate Your PublicRuntimeSettings

The struct `PublicRuntimeSettings` has been refactored. It retains commonly used properties via `SimplifiedCaptureVisionSettings` while removing the previously complex property settings, which are now exclusively supported through templates.

The APIs for accessing and updating `PublicRuntimeSettings` has been adjusted as follows:

| Old APIs | New APIs |
| :----------- | :------- |
| `BarcodeReader.GetRuntimeSettings` | `CaptureVisionRouter.GetSimplifiedSettings` |
| `BarcodeReader.UpdateRuntimeSettings` | `CaptureVisionRouter.UpdateSettings` |

#### Migrate to SimplifiedCaptureVisionSettings

The following properties are replaced by similar properties under `SimplifiedCaptureVisionSettings`. They can also be set via a template file(String).

| PublicRuntimeSettings Property | SimplifiedCaptureVisionSettings Parameter | Template File Parameter |
| ------------------------------- | ----------------------------------------- | ----------------------- |
| `Region` | [`roi`]({{ site.dcvb_dotnet_api }}capture-vision-router/structs/simplified-capture-vision-settings.html#roi) & [`roiMeasuredInPercentage`]({{ site.dcvb_dotnet_api }}capture-vision-router/structs/simplified-capture-vision-settings.html#roimeasuredinpercentage) | [`TargetROIDef.Location.Offset`]({{ site.dcvb_parameters_reference }}target-roi-def/location.html) |
| `Timeout` | [`timeout`]({{ site.dcvb_dotnet_api }}capture-vision-router/structs/simplified-capture-vision-settings.html#timeout) | [`CaptureVisionTemplates.Timeout`]({{ site.dcvb_parameters_reference }}capture-vision-template/timeout.html) |

#### Migrate to SimplifiedBarcodeReaderSettings

The following properties are replaced by similar properties under `SimplifiedBarcodeReaderSettings`. The majority of them can also be set via a template file(String).

| PublicRuntimeSettings Property | SimplifiedBarcodeReaderSettings Property | Template File Parameter |
| ------------------------------- | ----------------------------------------- | ----------------------- |
| `MinBarcodeTextLength` | [`minBarcodeTextLength`]({{ site.dbr_dotnet_api }}simplified-barcode-reader-settings.html#minbarcodetextlength) | [`BarcodeFormatSpecification.BarcodeTextLengthRangeArray`]({{ site.dcvb_parameters_reference }}barcode-format-specification/barcode-text-length-range-array.html) |
| `MinResultConfidence` | [`minResultConfidence`]({{ site.dbr_dotnet_api }}simplified-barcode-reader-settings.html#minresultconfidence) | [`BarcodeFormatSpecification.MinResultConfidence`]({{ site.dcvb_parameters_reference }}barcode-format-specification/min-result-confidence.html) |
| `LocalizationModes` | [`localizationModes`]({{ site.dbr_dotnet_api }}simplified-barcode-reader-settings.html#localizationmodes) | [`BarcodeReaderTaskSetting.LocationModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/localization-modes.html) |
| `ExpectedBarcodesCount` | [`expectedBarcodesCount`]({{ site.dbr_dotnet_api }}simplified-barcode-reader-settings.html#expectedbarcodescount) | [`BarcodeReaderTaskSetting.ExpectedBarcodesCount`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/expected-barcodes-count.html) |
| `BarcodeFormatIds` | [`barcodeFormatIds`]({{ site.dbr_dotnet_api }}simplified-barcode-reader-settings.html#barcodeformatids) | [`BarcodeReaderTaskSetting.BarcodeFormatIds`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/barcode-format-ids.html) |
| `BarcodeFormatIds_2` | [`barcodeFormatIds`]({{ site.dbr_dotnet_api }}simplified-barcode-reader-settings.html#barcodeformatids) | [`BarcodeReaderTaskSetting.BarcodeFormatIds`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/barcode-format-ids.html) |
| `DeblurModes` | [`deblurModes`]({{ site.dbr_dotnet_api }}simplified-barcode-reader-settings.html#deblurmodes) | [`BarcodeReaderTaskSetting.DeblurModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/deblur-modes.html) |
| `DeblurLevel` | [`deblurModes`]({{ site.dbr_dotnet_api }}simplified-barcode-reader-settings.html#deblurmodes) | [`BarcodeReaderTaskSetting.DeblurModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/deblur-modes.html) |
| `MaxAlgorithmThreadCount` | [`maxThreadsInOneTask`]({{ site.dbr_dotnet_api }}simplified-barcode-reader-settings.html#maxthreadsinonetask) | [`BarcodeReaderTaskSetting.MaxThreadsInOneTask`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/max-threads-in-one-task.html) |

> Remarks:
>
> * The 2 groups of barcode formats are merged.
> * `DeblurLevel` is deprecated. You can use `DeblurModes` instead.

| FurtherModes Property | SimplifiedBarcodeReaderSettings Property | Template File Parameter |
| ---------------------- | ----------------------------------------- | ----------------------- |
| `GrayscaleTransformationModes` | [`grayscaleTransformationModes`]({{ site.dbr_dotnet_api }}simplified-barcode-reader-settings.html#grayscaletransformationmodes) | [`ImageParameter.GrayscaleTransformationModes`]({{ site.dcvb_parameters_reference }}image-parameter/grayscale-enhancement-modes.html) |
| `ImagePreprocessingModes` | [`grayscaleEnhancementModes`]({{ site.dbr_dotnet_api }}simplified-barcode-reader-settings.html#grayscaleenhancementmodes) | [`ImageParameter.GrayscaleEnhancementModes`]({{ site.dcvb_parameters_reference }}image-parameter/grayscale-transformation-modes.html) |

> Remarks: The mode `IPM_MORPHOLOGY` of `ImagePreprocessingModes` is migrated to `BinarizationModes`. The mode arguments `MorphOperation`, `MorphOperationKernelSizeX`, `MorphOperationKernelSizeY`, `MorphShape` are now available for all modes of `BinarizationModes`.

#### Migrate to Template File

The following properties can only be set via a template file. Please [contact us](https://www.dynamsoft.com/company/customer-service/#contact){:target="_blank"} so that we can help you to transform your current settings to a new template file.

| PublicRuntimeSettings Property | Template File Parameter |
| ------------------------------- | ----------------------- |
| `ScaleDownThreshold` | [`ImageParameter.ScaleDownThreshold`]({{ site.dcvb_parameters_reference }}image-parameter/scale-down-threshold.html) |
| `BinarizationModes` | [`ImageParameter.BinarizationModes`]({{ site.dcvb_parameters_reference }}image-parameter/binarization-modes.html) |
| `TextResultOrderModes` | [`BarcodeReaderTaskSetting.TextResultOrderModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/text-result-order-modes.html) |
| `ReturnBarcodeZoneClarity` | [`BarcodeReaderTaskSetting.ReturnBarcodeZoneClarity`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/return-barcode-zone-clarity.html) |
| `ScaleUpModes` | [`ImageParameter.ScaleUpModes`]({{ site.dcvb_parameters_reference }}image-parameter/scale-up-modes.html) |
| `BarcodeZoneMinDistanceToImageBorders` | [`BarcodeFormatSpecification.BarcodeZoneMinDistanceToImageBorders`]({{ site.dcvb_parameters_reference }}barcode-format-specification/barcode-zone-min-distance-to-image-borders.html) |
| `TerminatePhase` | [`BarcodeReaderTaskSetting.TerminateSettings`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/terminate-setting.html) |

| FurtherModes Property | Template File Parameter |
| ---------------------- | ----------------------- |
| `ColourConversionModes` | [`ImageParameter.ColourConversionModes`]({{ site.dcvb_parameters_reference }}image-parameter/colour-conversion-modes.html) |
| `RegionPredetectionModes` | [`ImageParameter.RegionPredetectionModes`]({{ site.dcvb_parameters_reference }}image-parameter/region-predetection-modes.html) |
| `TextureDetectionModes` | [`ImageParameter.TextureDetectionModes`]({{ site.dcvb_parameters_reference }}image-parameter/texture-detection-modes.html) |
| `TextFilterModes` | [`ImageParameter.TextDetectionMode`]({{ site.dcvb_parameters_reference }}image-parameter/text-detection-mode.html) & [`ImageParameter.IfEraseTextZone`]({{ site.dcvb_parameters_reference }}image-parameter/if-erase-text-zone.html) |
| `DPMCodeReadingModes` | [`BarcodeReaderTaskSetting.DPMCodeReadingModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/dpm-code-reading-modes.html) |
| `DeformationResistingModes` | [`BarcodeReaderTaskSetting.DeformationResistingModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/deformation-resisting-modes.html) |
| `BarcodeComplementModes` | [`BarcodeReaderTaskSetting.BarcodeComplementModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/barcode-complement-modes.html) |
| `BarcodeColourModes` | [`BarcodeReaderTaskSetting.BarcodeColourModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/barcode-colour-modes.html) |

#### Migrate to Other APIs

The PDF properties of PublicRuntimeSettings are moved to set via the `setPDFReadingParameter` method of `DirectoryFetcher` and `FileFetcher` with a [`PDFReadingParameter`]({{ site.dcvb_dotnet_api }}core/basic-structures/pdf-reading-parameter.html) parameter.

| PublicRuntimeSettings Property |
| --------------------------------------- |
| `PDFReadingMode` |
| `PDFRasterDPI` |

The `Intermediate Result` system is redesigned and the following properties are deprecated.

| PublicRuntimeSettings Property |
| --------------------- |
| `IntermediateResultTypes` |
| `IntermediateResultSavingMode` |

#### Removed

The following properties are removed.

| PublicRuntimeSettings Property|
| --------------------- |
| `ResultCoordinateType` |

| FurtherModes Property|
| --------------------- |
| `ColourClusteringModes` |
