---
title: Upgrade Instructions - Dynamsoft Barcode Reader SDK Java Edition
keywords: java, upgrade
description: This page introduces how to upgrade Dynamsoft Barcode Reader SDK Java Edition
needAutoGenerateSidebar: true
needGenerateH3Content: true
---

# How to Upgrade to Version 11.x

## From version 9.x or earlier

Dynamsoft Barcode Reader SDK has been refactored to integrate with [`DynamsoftCaptureVision (DCV)`]({{ site.dcvb_architecture }}) architecture. To upgrade from version 9.x or earlier to 11.x, we recommend you to follow the [User Guide]({{ site.dbr_java }}user-guide.html) and re-write your codes. This section highlights only the key changes and necessary actions for upgrading the SDK.

### Update the License Key

#### Request a 30-Day Free Trial License

Visit the [Request a Trial License](https://www.dynamsoft.com/customer/license/trialLicense?product=dbr&utm_source=docs){:target="_blank"} page to obtain a 30-day free license. This option is ideal for initial evaluation or testing of new SDK features.

#### Annual Online Full License

If you are using an Annual Online Full License, your license will continue to work with the current SDK version without the need for updates. Go to <a href="https://www.dynamsoft.com/customer/license/fullLicense" target="_blank">Customer Portal</a> to get your license key.

#### Perpetual License

For users with a Perpetual License, please contact our sales team to update your license. You can reach out through our [Contacting Us](https://www.dynamsoft.com/contact/){:target="_blank"} page for assistance.

### Update the Package Version

You need to update the version number in your Maven dependencies to use the latest version. Update your `pom.xml` file with the following version:

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
        <version>11.0.6100</version>
    </dependency>
</dependencies>
```

### Update the License Activation Code

Starting from 11.0, we have unified the API for setting licenses across different Dynamsoft products.

| Old APIs | New APIs |
| :----------- | :------- |
| `BarcodeReader.initLicense` | [`LicenseManager.initLicense`]({{ site.dcvb_java_api }}license/license-manager.html#initlicense) |

### Update Single Image Decoding APIs

The APIs for decoding single image have been adjusted as follows:

| Old APIs | New APIs |
| :----------- | :------- |
| `BarcodeReader.decodeFile` | [`CaptureVisionRouter.capture`]({{ site.dcvb_java_api }}capture-vision-router/single-file-processing.html#capture) |
| `BarcodeReader.decodeFileInMemory` | [`CaptureVisionRouter.capture`]({{ site.dcvb_java_api }}capture-vision-router/single-file-processing.html#capture) |
| `BarcodeReader.decodeBuffer` | [`CaptureVisionRouter.capture`]({{ site.dcvb_java_api }}capture-vision-router/single-file-processing.html#capture) |
| `BarcodeReader.decodeBufferedImage` | [`CaptureVisionRouter.capture`]({{ site.dcvb_java_api }}capture-vision-router/single-file-processing.html#capture) |
| `class TextResult` | [`class BarcodeResultItem`]({{ site.dbr_java_api }}barcode-result-item.html) |
| `BarcodeReader.decodeBase64String` | **Currently not available**. |

### Update Video Streaming Decoding Code

`ImageSourceAdapter` is added to replace the `FrameDecodeingParameters` and the previous video methods. You should implement `ImageSourceAdapter` to transfer image data from camera or video file to buffer.


### Migrate Your Templates

The template system is upgraded. The template you used for the previous version can't be directly recognized by the new version. Please use the <a href="https://www.dynamsoft.com/tools/template-upgrade/" target="_blank">template upgrade tool</a> to upgrade your template.

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

### Migrate Your PublicRuntimeSetting

The class `PublicRuntimeSetting` has been refactored. It retains commonly used properties via `SimplifiedCaptureVisionSettings` while removing the previously complex property settings, which are now exclusively supported through templates.

The APIs for accessing and updating runtime settings have been adjusted as follows:

| Old APIs | New APIs |
| :----------- | :------- |
| `BarcodeReader.getRuntimeSettings` | [`CaptureVisionRouter.getSimplifiedSettings`]({{ site.dcvb_java_api }}capture-vision-router/settings.html#getsimplifiedsettings) |
| `BarcodeReader.updateRuntimeSettings` | [`CaptureVisionRouter.updateSettings`]({{ site.dcvb_java_api }}capture-vision-router/settings.html#updatesettings) |

#### Migrate to SimplifiedCaptureVisionSettings

The following properties are replaced by similar properties under `SimplifiedCaptureVisionSettings`. They can also be set via a template file(String).

| PublicRuntimeSetting Property | SimplifiedCaptureVisionSettings Parameter | Template File Parameter |
| ------------------------------- | ----------------------------------------- | ----------------------- |
| `region` | [`roi`]({{ site.dcvb_java_api }}capture-vision-router/auxiliary-classes/simplified-capture-vision-settings.html#roi) & [`roiMeasuredInPercentage`]({{ site.dcvb_java_api }}capture-vision-router/auxiliary-classes/simplified-capture-vision-settings.html#roimeasuredinpercentage) | [`TargetROIDef.Location.Offset`]({{ site.dcvb_parameters_reference }}target-roi-def/location.html) |
| `timeout` | [`timeout`]({{ site.dcvb_java_api }}capture-vision-router/auxiliary-classes/simplified-capture-vision-settings.html#timeout) | [`CaptureVisionTemplates.Timeout`]({{ site.dcvb_parameters_reference }}capture-vision-template/timeout.html) |

#### Migrate to SimplifiedBarcodeReaderSettings

The following properties are replaced by similar properties under `SimplifiedBarcodeReaderSettings`. The majority of them can also be set via a template file(String).

| PublicRuntimeSetting Property | SimplifiedBarcodeReaderSettings Property | Template File Parameter |
| ------------------------------- | ----------------------------------------- | ----------------------- |
| `minBarcodeTextLength` | [`minBarcodeTextLength`]({{ site.dbr_java_api }}simplified-barcode-reader-settings.html#minbarcodetextlength) | [`BarcodeFormatSpecification.BarcodeTextLengthRangeArray`]({{ site.dcvb_parameters_reference }}barcode-format-specification/barcode-text-length-range-array.html) |
| `minResultConfidence` | [`minResultConfidence`]({{ site.dbr_java_api }}simplified-barcode-reader-settings.html#minresultconfidence) | [`BarcodeFormatSpecification.MinResultConfidence`]({{ site.dcvb_parameters_reference }}barcode-format-specification/min-result-confidence.html) |
| `localizationModes` | [`localizationModes`]({{ site.dbr_java_api }}simplified-barcode-reader-settings.html#localizationmodes) | [`BarcodeReaderTaskSetting.LocationModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/localization-modes.html) |
| `expectedBarcodesCount` | [`expectedBarcodesCount`]({{ site.dbr_java_api }}simplified-barcode-reader-settings.html#expectedbarcodescount) | [`BarcodeReaderTaskSetting.ExpectedBarcodesCount`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/expected-barcodes-count.html) |
| `barcodeFormatIds` | [`barcodeFormatIds`]({{ site.dbr_java_api }}simplified-barcode-reader-settings.html#barcodeformatids) | [`BarcodeReaderTaskSetting.BarcodeFormatIds`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/barcode-format-ids.html) |
| `barcodeFormatIds_2` | [`barcodeFormatIds`]({{ site.dbr_java_api }}simplified-barcode-reader-settings.html#barcodeformatids) | [`BarcodeReaderTaskSetting.BarcodeFormatIds`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/barcode-format-ids.html) |
| `deblurModes` | [`deblurModes`]({{ site.dbr_java_api }}simplified-barcode-reader-settings.html#deblurmodes) | [`BarcodeReaderTaskSetting.DeblurModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/deblur-modes.html) |
| `deblurLevel` | [`deblurModes`]({{ site.dbr_java_api }}simplified-barcode-reader-settings.html#deblurmodes) | [`BarcodeReaderTaskSetting.DeblurModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/deblur-modes.html) |
| `maxAlgorithmThreadCount` | [`maxThreadsInOneTask`]({{ site.dbr_java_api }}simplified-barcode-reader-settings.html#maxthreadsinonetask) | [`BarcodeReaderTaskSetting.MaxThreadsInOneTask`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/max-threads-in-one-task.html) |
| `grayscaleTransformationModes` | [`grayscaleTransformationModes`]({{ site.dbr_java_api }}simplified-barcode-reader-settings.html#grayscaletransformationmodes) | [`ImageParameter.GrayscaleTransformationModes`]({{ site.dcvb_parameters_reference }}image-parameter/grayscale-enhancement-modes.html) |
| `imagePreprocessingModes` | [`grayscaleEnhancementModes`]({{ site.dbr_java_api }}simplified-barcode-reader-settings.html#grayscaleenhancementmodes) | [`ImageParameter.GrayscaleEnhancementModes`]({{ site.dcvb_parameters_reference }}image-parameter/grayscale-transformation-modes.html) |

> Remarks:
>
> * The 2 groups of barcode formats are merged.
> * `deblurLevel` is deprecated. You can use `deblurModes` instead.
> * The mode `IPM_MORPHOLOGY` of `imagePreprocessingModes` is migrated to `BinarizationModes`. The mode arguments `MorphOperation`, `MorphOperationKernelSizeX`, `MorphOperationKernelSizeY`, `MorphShape` are now available for all modes of `BinarizationModes`.

#### Migrate to Template File

The following properties can only be set via a template file. Please call `BarcodeReader.outputSettingsToFile` first with the old version to export the settings and then use the <a href="https://www.dynamsoft.com/tools/template-upgrade/" target="_blank">template upgrade tool</a> to upgrade your template.

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

#### Migrate to Other APIs

The PDF properties of `PublicRuntimeSetting` are moved to set via the `setPDFReadingParameter` method of [`DirectoryFetcher`]({{ site.dcvb_java_api }}utility/directory-fetcher.html) and [`FileFetcher`]({{ site.dcvb_java_api }}utility/file-fetcher.html) with a [`PDFReadingParameter`]({{ site.dcvb_java_api }}core/basic-classes/pdf-reading-parameter.html) parameter.

| PublicRuntimeSetting Property |
| ----------------------------- |
| `pdfReadingMode` |
| `pdfRasterDPI` |

The `Intermediate Result` system is redesigned and the following properties are deprecated.

| PublicRuntimeSetting Property |
| --------------------- |
| `intermediateResultTypes` |
| `intermediateResultSavingMode` |

#### Removed

The following properties are removed.

| PublicRuntimeSetting Property|
| --------------------- |
| `barcodeColourModes` |
| `resultCoordinateType` |
| `terminatePhase` |

| FurtherModes Property|
| --------------------- |
| `colourClusteringModes` |
