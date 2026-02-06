---
title: Migrate from v9.x to v11.x - Dynamsoft Barcode Reader SDK .NET Edition
keywords: .NET, upgrade, migrate, v9, v11
description: This page introduces how to migrate Dynamsoft Barcode Reader SDK .NET Edition from version 9.x to 11.x
needAutoGenerateSidebar: true
needGenerateH3Content: true
---

# Migrate from 9.x to 11.x

Dynamsoft Barcode Reader SDK has been refactored to integrate with the [`DynamsoftCaptureVision (DCV)`]({{ site.dcvb_architecture }}) architecture since version 10.0. This guide helps you upgrade from version 9.x by highlighting the key API changes and providing migration paths.

The actual migration effort depends on which APIs you currently use. In many cases, only the interfaces you actively use need to be updated — review the sections below to identify the changes that affect your integration.

> [!NOTE]
> If you are new to the DCV architecture and prefer to start fresh, refer to the [User Guide]({{ site.dbr_dotnet}}user-guide.html) for a quick-start tutorial.

## Update the License Key

You may need to update your license key before upgrading to version 11.x.

- **30-Day Free Trial License**: Visit the [Request a Trial License](https://www.dynamsoft.com/customer/license/trialLicense?product=dbr&utm_source=docs){:target="_blank"} page to obtain a free license for evaluation.
- **Annual Online Full License**: Your license will continue to work with the new SDK version. Go to <a href="https://www.dynamsoft.com/customer/license/fullLicense" target="_blank">Customer Portal</a> to get your license key.
- **Perpetual License**: Please contact our [sales team](https://www.dynamsoft.com/contact/){:target="_blank"} to update your license.

## Migrate to New Package

As of version 10.0, the NuGet package `Dynamsoft.DotNet.Barcode` has been renamed to `Dynamsoft.DotNet.BarcodeReader.Bundle` to reflect changes in both architecture and API design. Run the following command to install the new package:

```
NuGet\Install-Package Dynamsoft.DotNet.BarcodeReader.Bundle
```

## Migrate License Activation Code

Starting from 10.0, we have unified the API for setting licenses across different Dynamsoft products.

| Old APIs | New APIs |
| :----------- | :------- |
| `BarcodeReader.InitLicense` | [LicenseManager.InitLicense]({{ site.dcvb_dotnet_api }}license/license-manager.html#initlicense) |

## Migrate Decoding APIs

### Single Image Decoding

The APIs for decoding single image have been adjusted as follows:

| Old APIs | New APIs |
| :----------- | :------- |
| `BarcodeReader.DecodeFile` | [CaptureVisionRouter.Capture]({{ site.dcvb_dotnet_api }}capture-vision-router/single-file-processing.html#capture) |
| `BarcodeReader.DecodeFileInMemory` | [CaptureVisionRouter.Capture]({{ site.dcvb_dotnet_api }}capture-vision-router/single-file-processing.html#capture) |
| `BarcodeReader.DecodeBuffer` | [CaptureVisionRouter.Capture]({{ site.dcvb_dotnet_api }}capture-vision-router/single-file-processing.html#capture) |
| `class TextResult` | [class BarcodeResultItem]({{ site.dbr_dotnet_api }}barcode-result-item.html) |
| `BarcodeReader.DecodeBase64String` | [ImageIO.ReadFromBase64String]({{ site.dcvb_dotnet_api }}utility/image-io.html#readfrombase64string) + [CaptureVisionRouter.Capture]({{ site.dcvb_dotnet_api }}capture-vision-router/single-file-processing.html#capture) |
| `BarcodeReader.DecodeBitmap` | [ImageIO.ReadFromBitmap]({{ site.dcvb_dotnet_api }}utility/image-io.html#readfrombitmap) + [CaptureVisionRouter.Capture]({{ site.dcvb_dotnet_api }}capture-vision-router/single-file-processing.html#capture) |

### Video Streaming Decoding

`ImageSourceAdapter` is added to replace the `FrameDecodingParameters` and the previous video methods. You should implement `ImageSourceAdapter` to transfer image data from camera or video file to buffer.

## Migrate Template APIs

The template-based APIs have been updated as follows:

| Old APIs | New APIs |
| :----------- | :------- |
| `BarcodeReader.InitRuntimeSettingsWithFile` | [CaptureVisionRouter.InitSettingsFromFile]({{ site.dcvb_dotnet_api }}capture-vision-router/settings.html#initsettingsfromfile) |
| `BarcodeReader.InitRuntimeSettingsWithString` | [CaptureVisionRouter.InitSettings]({{ site.dcvb_dotnet_api }}capture-vision-router/settings.html#initsettings) |
| `BarcodeReader.OutputSettingsToFile` | [CaptureVisionRouter.OutputSettingsToFile]({{ site.dcvb_dotnet_api }}capture-vision-router/settings.html#outputsettingstofile) |
| `BarcodeReader.OutputSettingsToString` | [CaptureVisionRouter.OutputSettings]({{ site.dcvb_dotnet_api }}capture-vision-router/settings.html#outputsettings) |
| `BarcodeReader.ResetRuntimeSettings` | [CaptureVisionRouter.ResetSettings]({{ site.dcvb_dotnet_api }}capture-vision-router/settings.html#resetsettings) |
| `BarcodeReader.AppendTplFileToRuntimeSettings` | **Not available**. |
| `BarcodeReader.AppendTplStringToRuntimeSettings` | **Not available**. |
| `BarcodeReader.GetAllParameterTemplateNames` | **Not available**. |

## Upgrade Template Files

The template file format has changed in the new version. Templates created for version 9.x are not compatible with version 11.x. Use the <a href="https://www.dynamsoft.com/tools/template-upgrade/" target="_blank">Template Upgrade Tool</a> to automatically convert your existing templates to the new format.

## Migrate Runtime Settings

The struct `PublicRuntimeSettings` has been refactored. It retains commonly used properties via `SimplifiedCaptureVisionSettings` while removing the previously complex property settings, which are now exclusively supported through templates.

The APIs for accessing and updating `PublicRuntimeSettings` have been adjusted as follows:

| Old APIs | New APIs |
| :----------- | :------- |
| `BarcodeReader.GetRuntimeSettings` | [CaptureVisionRouter.GetSimplifiedSettings]({{ site.dcvb_dotnet_api }}capture-vision-router/settings.html#getsimplifiedsettings) |
| `BarcodeReader.UpdateRuntimeSettings` | [CaptureVisionRouter.UpdateSettings]({{ site.dcvb_dotnet_api }}capture-vision-router/settings.html#updatesettings) |

### Properties with Direct API Replacement

The following properties are replaced by similar properties under `SimplifiedCaptureVisionSettings` or `SimplifiedBarcodeReaderSettings`. They can also be set via a template file.

#### SimplifiedCaptureVisionSettings

| PublicRuntimeSettings Property | SimplifiedCaptureVisionSettings Parameter | Template File Parameter |
| ------------------------------- | ----------------------------------------- | ----------------------- |
| `Region` | [roi]({{ site.dcvb_dotnet_api }}capture-vision-router/auxiliary-classes/simplified-capture-vision-settings.html#roi) & [roiMeasuredInPercentage]({{ site.dcvb_dotnet_api }}capture-vision-router/auxiliary-classes/simplified-capture-vision-settings.html#roimeasuredinpercentage) | [TargetROIDef.Location.Offset]({{ site.dcvb_parameters_reference }}target-roi-def/location.html) |
| `Timeout` | [timeout]({{ site.dcvb_dotnet_api }}capture-vision-router/auxiliary-classes/simplified-capture-vision-settings.html#timeout) | [CaptureVisionTemplates.Timeout]({{ site.dcvb_parameters_reference }}capture-vision-template/timeout.html) |

#### SimplifiedBarcodeReaderSettings

| PublicRuntimeSettings Property | SimplifiedBarcodeReaderSettings Property | Template File Parameter |
| ------------------------------- | ----------------------------------------- | ----------------------- |
| `MinBarcodeTextLength` | [minBarcodeTextLength]({{ site.dbr_dotnet_api }}simplified-barcode-reader-settings.html#minbarcodetextlength) | [BarcodeFormatSpecification.BarcodeTextLengthRangeArray]({{ site.dcvb_parameters_reference }}barcode-format-specification/barcode-text-length-range-array.html) |
| `MinResultConfidence` | [minResultConfidence]({{ site.dbr_dotnet_api }}simplified-barcode-reader-settings.html#minresultconfidence) | [BarcodeFormatSpecification.MinResultConfidence]({{ site.dcvb_parameters_reference }}barcode-format-specification/min-result-confidence.html) |
| `LocalizationModes` | [localizationModes]({{ site.dbr_dotnet_api }}simplified-barcode-reader-settings.html#localizationmodes) | [BarcodeReaderTaskSetting.LocalizationModes]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/localization-modes.html) |
| `ExpectedBarcodesCount` | [expectedBarcodesCount]({{ site.dbr_dotnet_api }}simplified-barcode-reader-settings.html#expectedbarcodescount) | [BarcodeReaderTaskSetting.ExpectedBarcodesCount]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/expected-barcodes-count.html) |
| `BarcodeFormatIds` | [barcodeFormatIds]({{ site.dbr_dotnet_api }}simplified-barcode-reader-settings.html#barcodeformatids) | [BarcodeReaderTaskSetting.BarcodeFormatIds]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/barcode-format-ids.html) |
| `BarcodeFormatIds_2` | [barcodeFormatIds]({{ site.dbr_dotnet_api }}simplified-barcode-reader-settings.html#barcodeformatids) | [BarcodeReaderTaskSetting.BarcodeFormatIds]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/barcode-format-ids.html) |
| `DeblurModes` | [deblurModes]({{ site.dbr_dotnet_api }}simplified-barcode-reader-settings.html#deblurmodes) | [BarcodeReaderTaskSetting.DeblurModes]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/deblur-modes.html) |
| `DeblurLevel` | [deblurModes]({{ site.dbr_dotnet_api }}simplified-barcode-reader-settings.html#deblurmodes) | [BarcodeReaderTaskSetting.DeblurModes]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/deblur-modes.html) |
| `MaxAlgorithmThreadCount` | [maxThreadsInOneTask]({{ site.dbr_dotnet_api }}simplified-barcode-reader-settings.html#maxthreadsinonetask) | [BarcodeReaderTaskSetting.MaxThreadsInOneTask]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/max-threads-in-one-task.html) |

> Remarks:
>
> * The 2 groups of barcode formats are merged.
> * `DeblurLevel` is deprecated. You can use `DeblurModes` instead.

| FurtherModes Property | SimplifiedBarcodeReaderSettings Property | Template File Parameter |
| ---------------------- | ----------------------------------------- | ----------------------- |
| `GrayscaleTransformationModes` | [grayscaleTransformationModes]({{ site.dbr_dotnet_api }}simplified-barcode-reader-settings.html#grayscaletransformationmodes) | [ImageParameter.GrayscaleTransformationModes]({{ site.dcvb_parameters_reference }}image-parameter/grayscale-transformation-modes.html) |
| `ImagePreprocessingModes` | [grayscaleEnhancementModes]({{ site.dbr_dotnet_api }}simplified-barcode-reader-settings.html#grayscaleenhancementmodes) | [ImageParameter.GrayscaleEnhancementModes]({{ site.dcvb_parameters_reference }}image-parameter/grayscale-enhancement-modes.html) |

> Remarks: The mode `IPM_MORPHOLOGY` of `ImagePreprocessingModes` is migrated to `BinarizationModes`. The mode arguments `MorphOperation`, `MorphOperationKernelSizeX`, `MorphOperationKernelSizeY`, `MorphShape` are now available for all modes of `BinarizationModes`.

### Properties Requiring Template File

The following properties can only be set via a template file. Please call `BarcodeReader.OutputSettingsToFile` first with the old version to export the settings and then use the <a href="https://www.dynamsoft.com/tools/template-upgrade/" target="_blank">Template Upgrade Tool</a> to upgrade your template.

| PublicRuntimeSettings Property | Template File Parameter |
| ------------------------------- | ----------------------- |
| `ScaleDownThreshold` | [ImageParameter.ImageScaleSettings]({{ site.dcvb_parameters_reference }}image-parameter/image-scale-settings.html) |
| `BinarizationModes` | [ImageParameter.BinarizationModes]({{ site.dcvb_parameters_reference }}image-parameter/binarization-modes.html) |
| `TextResultOrderModes` | [BarcodeReaderTaskSetting.TextResultOrderModes]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/text-result-order-modes.html) |
| `ReturnBarcodeZoneClarity` | [BarcodeReaderTaskSetting.ReturnBarcodeZoneClarity]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/return-barcode-zone-clarity.html) |
| `ScaleUpModes` | [BarcodeReaderTaskSetting.BarcodeScaleModes]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/barcode-scale-modes.html) |
| `BarcodeZoneMinDistanceToImageBorders` | [BarcodeFormatSpecification.BarcodeZoneMinDistanceToImageBorders]({{ site.dcvb_parameters_reference }}barcode-format-specification/barcode-zone-min-distance-to-image-borders.html) |

| FurtherModes Property | Template File Parameter |
| ---------------------- | ----------------------- |
| `ColourConversionModes` | [ImageParameter.ColourConversionModes]({{ site.dcvb_parameters_reference }}image-parameter/colour-conversion-modes.html) |
| `RegionPredetectionModes` | [BarcodeReaderTaskSetting.RegionPredetectionModes]({{ site.dcvb_parameters_reference }}image-parameter/region-predetection-modes.html) |
| `TextureDetectionModes` | [ImageParameter.TextureDetectionModes]({{ site.dcvb_parameters_reference }}image-parameter/texture-detection-modes.html) |
| `TextFilterModes` | [ImageParameter.TextDetectionMode]({{ site.dcvb_parameters_reference }}image-parameter/text-detection-mode.html) & [ImageParameter.IfEraseTextZone]({{ site.dcvb_parameters_reference }}image-parameter/if-erase-text-zone.html) |
| `DPMCodeReadingModes` | [BarcodeReaderTaskSetting.DPMCodeReadingModes]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/dpm-code-reading-modes.html) |
| `DeformationResistingModes` | [BarcodeReaderTaskSetting.DeformationResistingModes]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/deformation-resisting-modes.html) |
| `BarcodeComplementModes` | [BarcodeReaderTaskSetting.BarcodeComplementModes]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/barcode-complement-modes.html) |

### Properties Migrated to Other APIs

The PDF properties of PublicRuntimeSettings are moved to set via the `SetPDFReadingParameter` method of `DirectoryFetcher` and `FileFetcher` with a [PDFReadingParameter]({{ site.dcvb_dotnet_api }}core/basic-classes/pdf-reading-parameter.html) parameter.

| PublicRuntimeSettings Property |
| --------------------------------------- |
| `PDFReadingMode` |
| `PDFRasterDPI` |

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
| `ColourClusteringModes` |
