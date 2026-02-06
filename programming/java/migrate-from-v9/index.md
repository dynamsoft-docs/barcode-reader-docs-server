---
title: Migrate from v9.x to v11.x - Dynamsoft Barcode Reader SDK Java Edition
keywords: java, upgrade, migrate, v9, v11
description: This page introduces how to migrate Dynamsoft Barcode Reader SDK Java Edition from version 9.x to 11.x
needAutoGenerateSidebar: true
needGenerateH3Content: true
---

# Migrate from 9.x to 11.x

Dynamsoft Barcode Reader SDK has been refactored to integrate with the [`DynamsoftCaptureVision (DCV)`]({{ site.dcvb_architecture }}) architecture since version 10.0. This guide helps you upgrade from version 9.x by highlighting the key API changes and providing migration paths.

The actual migration effort depends on which APIs you currently use. In many cases, only the interfaces you actively use need to be updated — review the sections below to identify the changes that affect your integration.

> [!NOTE]
> If you are new to the DCV architecture and prefer to start fresh, refer to the [User Guide]({{ site.dbr_java }}user-guide.html) for a quick-start tutorial.

## Update the License Key

You may need to update your license key before upgrading to version 11.x.

- **30-Day Free Trial License**: Visit the [Request a Trial License](https://www.dynamsoft.com/customer/license/trialLicense?product=dbr&utm_source=docs){:target="_blank"} page to obtain a free license for evaluation.
- **Annual Online Full License**: Your license will continue to work with the new SDK version. Go to <a href="https://www.dynamsoft.com/customer/license/fullLicense" target="_blank">Customer Portal</a> to get your license key.
- **Perpetual License**: Please contact our [sales team](https://www.dynamsoft.com/contact/){:target="_blank"} to update your license.

## Update the Maven Dependency

Update your `pom.xml` file with the latest version:

```xml
<repositories>
    <repository>
        <id>dbr</id>
        <url>https://download2.dynamsoft.com/maven/dbr/jar</url>
    </repository>
</repositories>

<dependencies>
    <dependency>
        <groupId>com.dynamsoft</groupId>
        <artifactId>dbr</artifactId>
        <version>11.4.1000</version>
    </dependency>
</dependencies>
```

## Migrate License Activation Code

Starting from 10.0, we have unified the API for setting licenses across different Dynamsoft products.

| Old APIs | New APIs |
| :----------- | :------- |
| `BarcodeReader.initLicense` | [`LicenseManager.initLicense`]({{ site.dcvb_java_api }}license/license-manager.html#initlicense) |

## Migrate Decoding APIs

### Single Image Decoding

The APIs for decoding single image have been adjusted as follows:

| Old APIs | New APIs |
| :----------- | :------- |
| `BarcodeReader.decodeFile` | [`CaptureVisionRouter.capture`]({{ site.dcvb_java_api }}capture-vision-router/single-file-processing.html#capture) |
| `BarcodeReader.decodeFileInMemory` | [`CaptureVisionRouter.capture`]({{ site.dcvb_java_api }}capture-vision-router/single-file-processing.html#capture) |
| `BarcodeReader.decodeBuffer` | [`CaptureVisionRouter.capture`]({{ site.dcvb_java_api }}capture-vision-router/single-file-processing.html#capture) |
| `BarcodeReader.decodeBufferedImage` | [`CaptureVisionRouter.capture`]({{ site.dcvb_java_api }}capture-vision-router/single-file-processing.html#capture) |
| `class TextResult` | [`class BarcodeResultItem`]({{ site.dbr_java_api }}barcode-result-item.html) |
| `BarcodeReader.decodeBase64String` | [ImageIO.readFromBase64String]({{ site.dcvb_java_api }}utility/image-io.html#readfrombase64string) + [CaptureVisionRouter.Capture]({{ site.dcvb_java_api }}capture-vision-router/single-file-processing.html#capture) |

### Video Streaming Decoding

`ImageSourceAdapter` is added to replace the `FrameDecodingParameters` and the previous video methods. You should implement `ImageSourceAdapter` to transfer image data from camera or video file to buffer.

## Migrate Template APIs

The template-based APIs have been updated as follows:

| Old APIs | New APIs |
| :----------- | :------- |
| `BarcodeReader.initRuntimeSettingsWithFile` | [`CaptureVisionRouter.initSettingsFromFile`]({{ site.dcvb_java_api }}capture-vision-router/settings.html#initsettingsfromfile) |
| `BarcodeReader.initRuntimeSettingsWithString` | [`CaptureVisionRouter.initSettings`]({{ site.dcvb_java_api }}capture-vision-router/settings.html#initsettings) |
| `BarcodeReader.outputSettingsToFile` | [`CaptureVisionRouter.outputSettingsToFile`]({{ site.dcvb_java_api }}capture-vision-router/settings.html#outputsettingstofile) |
| `BarcodeReader.outputSettingsToString` | [`CaptureVisionRouter.outputSettings`]({{ site.dcvb_java_api }}capture-vision-router/settings.html#outputsettings) |
| `BarcodeReader.resetRuntimeSettings` | [`CaptureVisionRouter.resetSettings`]({{ site.dcvb_java_api }}capture-vision-router/settings.html#resetsettings) |
| `BarcodeReader.appendTplFileToRuntimeSettings` | **Not available**. |
| `BarcodeReader.appendTplStringToRuntimeSettings` | **Not available**. |
| `BarcodeReader.getAllParameterTemplateNames` | **Not available**. |

## Upgrade Template Files

The template file format has changed in the new version. Templates created for version 9.x are not compatible with version 11.x. Use the <a href="https://www.dynamsoft.com/tools/template-upgrade/" target="_blank">Template Upgrade Tool</a> to automatically convert your existing templates to the new format.

## Migrate Runtime Settings

The class `PublicRuntimeSetting` has been refactored. It retains commonly used properties via `SimplifiedCaptureVisionSettings` while removing the previously complex property settings, which are now exclusively supported through templates.

The APIs for accessing and updating runtime settings have been adjusted as follows:

| Old APIs | New APIs |
| :----------- | :------- |
| `BarcodeReader.getRuntimeSettings` | [`CaptureVisionRouter.getSimplifiedSettings`]({{ site.dcvb_java_api }}capture-vision-router/settings.html#getsimplifiedsettings) |
| `BarcodeReader.updateRuntimeSettings` | [`CaptureVisionRouter.updateSettings`]({{ site.dcvb_java_api }}capture-vision-router/settings.html#updatesettings) |

### Properties with Direct API Replacement

The following properties are replaced by similar properties under `SimplifiedCaptureVisionSettings` or `SimplifiedBarcodeReaderSettings`. They can also be set via a template file.

#### SimplifiedCaptureVisionSettings

| PublicRuntimeSetting Property | SimplifiedCaptureVisionSettings Parameter | Template File Parameter |
| ------------------------------- | ----------------------------------------- | ----------------------- |
| `region` | [`roi`]({{ site.dcvb_java_api }}capture-vision-router/auxiliary-classes/simplified-capture-vision-settings.html#roi) & [`roiMeasuredInPercentage`]({{ site.dcvb_java_api }}capture-vision-router/auxiliary-classes/simplified-capture-vision-settings.html#roimeasuredinpercentage) | [`TargetROIDef.Location.Offset`]({{ site.dcvb_parameters_reference }}target-roi-def/location.html) |
| `timeout` | [`timeout`]({{ site.dcvb_java_api }}capture-vision-router/auxiliary-classes/simplified-capture-vision-settings.html#timeout) | [`CaptureVisionTemplates.Timeout`]({{ site.dcvb_parameters_reference }}capture-vision-template/timeout.html) |

#### SimplifiedBarcodeReaderSettings

| PublicRuntimeSetting Property | SimplifiedBarcodeReaderSettings Property | Template File Parameter |
| ------------------------------- | ----------------------------------------- | ----------------------- |
| `minBarcodeTextLength` | [`minBarcodeTextLength`]({{ site.dbr_java_api }}simplified-barcode-reader-settings.html#minbarcodetextlength) | [`BarcodeFormatSpecification.BarcodeTextLengthRangeArray`]({{ site.dcvb_parameters_reference }}barcode-format-specification/barcode-text-length-range-array.html) |
| `minResultConfidence` | [`minResultConfidence`]({{ site.dbr_java_api }}simplified-barcode-reader-settings.html#minresultconfidence) | [`BarcodeFormatSpecification.MinResultConfidence`]({{ site.dcvb_parameters_reference }}barcode-format-specification/min-result-confidence.html) |
| `localizationModes` | [`localizationModes`]({{ site.dbr_java_api }}simplified-barcode-reader-settings.html#localizationmodes) | [`BarcodeReaderTaskSetting.LocalizationModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/localization-modes.html) |
| `expectedBarcodesCount` | [`expectedBarcodesCount`]({{ site.dbr_java_api }}simplified-barcode-reader-settings.html#expectedbarcodescount) | [`BarcodeReaderTaskSetting.ExpectedBarcodesCount`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/expected-barcodes-count.html) |
| `barcodeFormatIds` | [`barcodeFormatIds`]({{ site.dbr_java_api }}simplified-barcode-reader-settings.html#barcodeformatids) | [`BarcodeReaderTaskSetting.BarcodeFormatIds`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/barcode-format-ids.html) |
| `barcodeFormatIds_2` | [`barcodeFormatIds`]({{ site.dbr_java_api }}simplified-barcode-reader-settings.html#barcodeformatids) | [`BarcodeReaderTaskSetting.BarcodeFormatIds`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/barcode-format-ids.html) |
| `deblurModes` | [`deblurModes`]({{ site.dbr_java_api }}simplified-barcode-reader-settings.html#deblurmodes) | [`BarcodeReaderTaskSetting.DeblurModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/deblur-modes.html) |
| `deblurLevel` | [`deblurModes`]({{ site.dbr_java_api }}simplified-barcode-reader-settings.html#deblurmodes) | [`BarcodeReaderTaskSetting.DeblurModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/deblur-modes.html) |
| `maxAlgorithmThreadCount` | [`maxThreadsInOneTask`]({{ site.dbr_java_api }}simplified-barcode-reader-settings.html#maxthreadsinonetask) | [`BarcodeReaderTaskSetting.MaxThreadsInOneTask`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/max-threads-in-one-task.html) |
| `grayscaleTransformationModes` | [`grayscaleTransformationModes`]({{ site.dbr_java_api }}simplified-barcode-reader-settings.html#grayscaletransformationmodes) | [`ImageParameter.GrayscaleTransformationModes`]({{ site.dcvb_parameters_reference }}image-parameter/grayscale-transformation-modes.html) |
| `imagePreprocessingModes` | [`grayscaleEnhancementModes`]({{ site.dbr_java_api }}simplified-barcode-reader-settings.html#grayscaleenhancementmodes) | [`ImageParameter.GrayscaleEnhancementModes`]({{ site.dcvb_parameters_reference }}image-parameter/grayscale-enhancement-modes.html) |

> Remarks:
>
> * The 2 groups of barcode formats are merged.
> * `deblurLevel` is deprecated. You can use `deblurModes` instead.
> * The mode `IPM_MORPHOLOGY` of `imagePreprocessingModes` is migrated to `BinarizationModes`. The mode arguments `MorphOperation`, `MorphOperationKernelSizeX`, `MorphOperationKernelSizeY`, `MorphShape` are now available for all modes of `BinarizationModes`.

### Properties Requiring Template File

The following properties can only be set via a template file. Please call `BarcodeReader.outputSettingsToFile` first with the old version to export the settings and then use the <a href="https://www.dynamsoft.com/tools/template-upgrade/" target="_blank">Template Upgrade Tool</a> to upgrade your template.

| PublicRuntimeSetting Property | Template File Parameter |
| ------------------------------- | ----------------------- |
| `scaleDownThreshold` | [`ImageParameter.ImageScaleSettings`]({{ site.dcvb_parameters_reference }}image-parameter/image-scale-settings.html) |
| `binarizationModes` | [`ImageParameter.BinarizationModes`]({{ site.dcvb_parameters_reference }}image-parameter/binarization-modes.html) |
| `textResultOrderModes` | [`BarcodeReaderTaskSetting.TextResultOrderModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/text-result-order-modes.html) |
| `returnBarcodeZoneClarity` | [`BarcodeReaderTaskSetting.ReturnBarcodeZoneClarity`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/return-barcode-zone-clarity.html) |
| `scaleUpModes` | [`BarcodeReaderTaskSetting.BarcodeScaleModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/barcode-scale-modes.html) |
| `barcodeZoneMinDistanceToImageBorders` | [`BarcodeFormatSpecification.BarcodeZoneMinDistanceToImageBorders`]({{ site.dcvb_parameters_reference }}barcode-format-specification/barcode-zone-min-distance-to-image-borders.html) |
| `colourConversionModes` | [`ImageParameter.ColourConversionModes`]({{ site.dcvb_parameters_reference }}image-parameter/colour-conversion-modes.html) |
| `regionPredetectionModes` | [`BarcodeReaderTaskSetting.RegionPredetectionModes`]({{ site.dcvb_parameters_reference }}image-parameter/region-predetection-modes.html) |
| `textureDetectionModes` | [`ImageParameter.TextureDetectionModes`]({{ site.dcvb_parameters_reference }}image-parameter/texture-detection-modes.html) |
| `textFilterModes` | [`ImageParameter.TextDetectionMode`]({{ site.dcvb_parameters_reference }}image-parameter/text-detection-mode.html) & [`ImageParameter.IfEraseTextZone`]({{ site.dcvb_parameters_reference }}image-parameter/if-erase-text-zone.html) |
| `dpmCodeReadingModes` | [`BarcodeReaderTaskSetting.DPMCodeReadingModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/dpm-code-reading-modes.html) |
| `deformationResistingModes` | [`BarcodeReaderTaskSetting.DeformationResistingModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/deformation-resisting-modes.html) |
| `barcodeComplementModes` | [`BarcodeReaderTaskSetting.BarcodeComplementModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/barcode-complement-modes.html) |

### Properties Migrated to Other APIs

The PDF properties of `PublicRuntimeSetting` are moved to set via the `setPDFReadingParameter` method of [`DirectoryFetcher`]({{ site.dcvb_java_api }}utility/directory-fetcher.html) and [`FileFetcher`]({{ site.dcvb_java_api }}utility/file-fetcher.html) with a [`PDFReadingParameter`]({{ site.dcvb_java_api }}core/basic-classes/pdf-reading-parameter.html) parameter.

| PublicRuntimeSetting Property |
| ----------------------------- |
| `pdfReadingMode` |
| `pdfRasterDPI` |

### Removed Properties (No Replacement)

The following properties are removed.

| PublicRuntimeSetting Property|
| --------------------- |
| `barcodeColourModes` |
| `intermediateResultTypes` |
| `intermediateResultSavingMode` |
| `resultCoordinateType` |
| `terminatePhase` |

| FurtherModes Property|
| --------------------- |
| `colourClusteringModes` |
