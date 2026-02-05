---
title: Migrate from v9.x to v11.x - Dynamsoft Barcode Reader SDK Python Edition
keywords: python, upgrade, migrate, v9, v11
description: This page introduces how to migrate Dynamsoft Barcode Reader SDK Python Edition from version 9.x to 11.x
needAutoGenerateSidebar: true
needGenerateH3Content: true
---

# Migrate from 9.x to 11.x

Dynamsoft Barcode Reader SDK has been refactored to integrate with the [`DynamsoftCaptureVision (DCV)`]({{ site.dcvb_architecture }}) architecture since version 10.0. This guide helps you upgrade from version 9.x by highlighting the key API changes and providing migration paths.

The actual migration effort depends on which APIs you currently use. In many cases, only the interfaces you actively use need to be updated — review the sections below to identify the changes that affect your integration.

> [!NOTE]
> If you are new to the DCV architecture and prefer to start fresh, refer to the [User Guide]({{ site.dbr_python }}user-guide.html) for a quick-start tutorial.

## Update the License Key

You may need to update your license key before upgrading to version 11.x.

- **30-Day Free Trial License**: Visit the [Request a Trial License](https://www.dynamsoft.com/customer/license/trialLicense?product=dbr&utm_source=docs){:target="_blank"} page to obtain a free license for evaluation.
- **Annual Online Full License**: Your license will continue to work with the new SDK version. Go to <a href="https://www.dynamsoft.com/customer/license/fullLicense" target="_blank">Customer Portal</a> to get your license key.
- **Perpetual License**: Please contact our [sales team](https://www.dynamsoft.com/contact/){:target="_blank"} to update your license.

## Migrate to New Package

As of version 10.0, the `dbr` package has been renamed to `dynamsoft-barcode-reader-bundle` to reflect changes in both architecture and API design. Run the following command to install the new package:

```bash
pip install dynamsoft-barcode-reader-bundle
```

## Migrate License Activation Code

Starting from 10.0, we have unified the API for setting licenses across different Dynamsoft products.

| Old APIs | New APIs |
| :----------- | :------- |
| `BarcodeReader.init_license` | [`LicenseManager.init_license`]({{ site.dcvb_python_api }}license/license-manager.html#init_license) |

## Migrate Decoding APIs

### Single Image Decoding

The APIs for decoding single image have been adjusted as follows:

| Old APIs | New APIs |
| :----------- | :------- |
| `BarcodeReader.decode_file` | [`CaptureVisionRouter.capture`]({{ site.dcvb_python_api }}capture-vision-router/single-file-processing.html#capture) |
| `BarcodeReader.decode_file_stream` | [`CaptureVisionRouter.capture`]({{ site.dcvb_python_api }}capture-vision-router/single-file-processing.html#capture) |
| `BarcodeReader.decode_buffer_manually` | [`CaptureVisionRouter.capture`]({{ site.dcvb_python_api }}capture-vision-router/single-file-processing.html#capture) |
| `BarcodeReader.decode_buffer` | [`CaptureVisionRouter.capture`]({{ site.dcvb_python_api }}capture-vision-router/single-file-processing.html#capture) |
| `class TextResult` | [`class BarcodeResultItem`]({{ site.dbr_python_api }}barcode-result-item.html) |
| `BarcodeReader.decode_base64_string` | **Not available**. |

### Video Streaming Decoding

`ImageSourceAdapter` is added to replace the `FrameDecodingParameters` and the previous video methods. You should implement `ImageSourceAdapter` to transfer image data from camera or video file to buffer.

## Migrate Template APIs

The template-based APIs have been updated as follows:

| Old APIs | New APIs |
| :----------- | :------- |
| `BarcodeReader.init_runtime_settings_with_file` | [`CaptureVisionRouter.init_settings_from_file`]({{ site.dcvb_python_api }}capture-vision-router/settings.html#init_settings_from_file) |
| `BarcodeReader.init_runtime_settings_with_string` | [`CaptureVisionRouter.init_settings`]({{ site.dcvb_python_api }}capture-vision-router/settings.html#init_settings) |
| `BarcodeReader.output_settings_to_json_file` | [`CaptureVisionRouter.output_settings_to_file`]({{ site.dcvb_python_api }}capture-vision-router/settings.html#output_settings_to_file) |
| `BarcodeReader.output_settings_to_json_string` | [`CaptureVisionRouter.output_settings`]({{ site.dcvb_python_api }}capture-vision-router/settings.html#output_settings) |
| `BarcodeReader.reset_runtime_settings` | [`CaptureVisionRouter.reset_settings`]({{ site.dcvb_python_api }}capture-vision-router/settings.html#reset_settings) |
| `BarcodeReader.append_template_file_to_runtime_settings` | **Not available**. |
| `BarcodeReader.append_template_string_to_runtime_settings` | **Not available**. |
| `BarcodeReader.get_all_template_names` | **Not available**. |

## Upgrade Template Files

The template file format has changed in the new version. Templates created for version 9.x are not compatible with version 11.x. Use the <a href="https://www.dynamsoft.com/tools/template-upgrade/" target="_blank">Template Upgrade Tool</a> to automatically convert your existing templates to the new format.

## Migrate Runtime Settings

The class `PublicRuntimeSetting` has been refactored. It retains commonly used properties via `SimplifiedCaptureVisionSettings` while removing the previously complex property settings, which are now exclusively supported through templates.

The APIs for accessing and updating runtime settings have been adjusted as follows:

| Old APIs | New APIs |
| :----------- | :------- |
| `BarcodeReader.get_runtime_settings` | [`CaptureVisionRouter.get_simplified_settings`]({{ site.dcvb_python_api }}capture-vision-router/settings.html#get_simplified_settings) |
| `BarcodeReader.update_runtime_settings` | [`CaptureVisionRouter.update_settings`]({{ site.dcvb_python_api }}capture-vision-router/settings.html#update_settings) |

### Properties with Direct API Replacement

The following properties are replaced by similar properties under `SimplifiedCaptureVisionSettings` or `SimplifiedBarcodeReaderSettings`. They can also be set via a template file.

#### SimplifiedCaptureVisionSettings

| PublicRuntimeSetting Property | SimplifiedCaptureVisionSettings Parameter | Template File Parameter |
| ------------------------------- | ----------------------------------------- | ----------------------- |
| `region` | [`roi`]({{ site.dcvb_python_api }}capture-vision-router/auxiliary-classes/simplified-capture-vision-settings.html#roi) & [`roi_measured_in_percentage`]({{ site.dcvb_python_api }}capture-vision-router/auxiliary-classes/simplified-capture-vision-settings.html#roi_measured_in_percentage) | [`TargetROIDef.Location.Offset`]({{ site.dcvb_parameters_reference }}target-roi-def/location.html) |
| `timeout` | [`timeout`]({{ site.dcvb_python_api }}capture-vision-router/auxiliary-classes/simplified-capture-vision-settings.html#timeout) | [`CaptureVisionTemplates.Timeout`]({{ site.dcvb_parameters_reference }}capture-vision-template/timeout.html) |

#### SimplifiedBarcodeReaderSettings

| PublicRuntimeSetting Property | SimplifiedBarcodeReaderSettings Property | Template File Parameter |
| ------------------------------- | ----------------------------------------- | ----------------------- |
| `min_barcode_text_length` | [`min_barcode_text_length`]({{ site.dbr_python_api }}simplified-barcode-reader-settings.html#min_barcode_text_length) | [`BarcodeFormatSpecification.BarcodeTextLengthRangeArray`]({{ site.dcvb_parameters_reference }}barcode-format-specification/barcode-text-length-range-array.html) |
| `min_result_confidence` | [`min_result_confidence`]({{ site.dbr_python_api }}simplified-barcode-reader-settings.html#min_result_confidence) | [`BarcodeFormatSpecification.MinResultConfidence`]({{ site.dcvb_parameters_reference }}barcode-format-specification/min-result-confidence.html) |
| `localization_modes` | [`localization_modes`]({{ site.dbr_python_api }}simplified-barcode-reader-settings.html#localization_modes) | [`BarcodeReaderTaskSetting.LocalizationModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/localization-modes.html) |
| `expected_barcodes_count` | [`expected_barcodes_count`]({{ site.dbr_python_api }}simplified-barcode-reader-settings.html#expected_barcodes_count) | [`BarcodeReaderTaskSetting.ExpectedBarcodesCount`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/expected-barcodes-count.html) |
| `barcode_format_ids` | [`barcode_format_ids`]({{ site.dbr_python_api }}simplified-barcode-reader-settings.html#barcode_format_ids) | [`BarcodeReaderTaskSetting.BarcodeFormatIds`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/barcode-format-ids.html) |
| `barcode_format_ids_2` | [`barcode_format_ids`]({{ site.dbr_python_api }}simplified-barcode-reader-settings.html#barcode_format_ids) | [`BarcodeReaderTaskSetting.BarcodeFormatIds`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/barcode-format-ids.html) |
| `deblur_modes` | [`deblur_modes`]({{ site.dbr_python_api }}simplified-barcode-reader-settings.html#deblur_modes) | [`BarcodeReaderTaskSetting.DeblurModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/deblur-modes.html) |
| `deblur_level` | [`deblur_modes`]({{ site.dbr_python_api }}simplified-barcode-reader-settings.html#deblur_modes) | [`BarcodeReaderTaskSetting.DeblurModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/deblur-modes.html) |
| `max_algorithm_thread_count` | [`max_threads_in_one_task`]({{ site.dbr_python_api }}simplified-barcode-reader-settings.html#max_threads_in_one_task) | [`BarcodeReaderTaskSetting.MaxThreadsInOneTask`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/max-threads-in-one-task.html) |
| `grayscale_transformation_modes` | [`grayscale_transformation_modes`]({{ site.dbr_python_api }}simplified-barcode-reader-settings.html#grayscale_transformation_modes) | [`ImageParameter.GrayscaleTransformationModes`]({{ site.dcvb_parameters_reference }}image-parameter/grayscale-transformation-modes.html) |
| `image_preprocessing_modes` | [`grayscale_enhancement_modes`]({{ site.dbr_python_api }}simplified-barcode-reader-settings.html#grayscale_enhancement_modes) | [`ImageParameter.GrayscaleEnhancementModes`]({{ site.dcvb_parameters_reference }}image-parameter/grayscale-enhancement-modes.html) |

> Remarks:
>
> * The 2 groups of barcode formats are merged.
> * `deblur_level` is deprecated. You can use `deblur_modes` instead.
> * The mode `IPM_MORPHOLOGY` of `image_preprocessing_modes` is migrated to `BinarizationModes`. The mode arguments `MorphOperation`, `MorphOperationKernelSizeX`, `MorphOperationKernelSizeY`, `MorphShape` are now available for all modes of `BinarizationModes`.

### Properties Requiring Template File

The following properties can only be set via a template file. Please call `BarcodeReader.output_settings_to_json_file` first with the old version to export the settings and then use the <a href="https://www.dynamsoft.com/tools/template-upgrade/" target="_blank">Template Upgrade Tool</a> to upgrade your template.

| PublicRuntimeSetting Property | Template File Parameter |
| ------------------------------- | ----------------------- |
| `scale_down_threshold` | [`ImageParameter.ImageScaleSettings`]({{ site.dcvb_parameters_reference }}image-parameter/image-scale-settings.html) |
| `binarization_modes` | [`ImageParameter.BinarizationModes`]({{ site.dcvb_parameters_reference }}image-parameter/binarization-modes.html) |
| `text_result_order_modes` | [`BarcodeReaderTaskSetting.TextResultOrderModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/text-result-order-modes.html) |
| `return_barcode_zone_clarity` | [`BarcodeReaderTaskSetting.ReturnBarcodeZoneClarity`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/return-barcode-zone-clarity.html) |
| `scale_up_modes` | [`BarcodeReaderTaskSetting.BarcodeScaleModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/barcode-scale-modes.html) |
| `barcode_zone_min_distance_to_image_borders` | [`BarcodeFormatSpecification.BarcodeZoneMinDistanceToImageBorders`]({{ site.dcvb_parameters_reference }}barcode-format-specification/barcode-zone-min-distance-to-image-borders.html) |
| `colour_conversion_modes` | [`ImageParameter.ColourConversionModes`]({{ site.dcvb_parameters_reference }}image-parameter/colour-conversion-modes.html) |
| `region_predetection_modes` | [`BarcodeReaderTaskSetting.RegionPredetectionModes`]({{ site.dcvb_parameters_reference }}image-parameter/region-predetection-modes.html) |
| `texture_detection_modes` | [`ImageParameter.TextureDetectionModes`]({{ site.dcvb_parameters_reference }}image-parameter/texture-detection-modes.html) |
| `text_filter_modes` | [`ImageParameter.TextDetectionMode`]({{ site.dcvb_parameters_reference }}image-parameter/text-detection-mode.html) & [`ImageParameter.IfEraseTextZone`]({{ site.dcvb_parameters_reference }}image-parameter/if-erase-text-zone.html) |
| `dpm_code_reading_modes` | [`BarcodeReaderTaskSetting.DPMCodeReadingModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/dpm-code-reading-modes.html) |
| `deformation_resisting_modes` | [`BarcodeReaderTaskSetting.DeformationResistingModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/deformation-resisting-modes.html) |
| `barcode_complement_modes` | [`BarcodeReaderTaskSetting.BarcodeComplementModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/barcode-complement-modes.html) |

### Properties Migrated to Other APIs

The PDF properties of `PublicRuntimeSetting` are moved to set via the `set_pdf_reading_parameter` method of [`DirectoryFetcher`]({{ site.dcvb_python_api }}utility/directory-fetcher.html) and [`FileFetcher`]({{ site.dcvb_python_api }}utility/file-fetcher.html) with a [`PDFReadingParameter`]({{ site.dcvb_python_api }}core/basic-classes/pdf-reading-parameter.html) parameter.

| PublicRuntimeSetting Property |
| ----------------------------- |
| `pdf_reading_mode` |
| `pdf_raster_dpi` |

### Removed Properties (No Replacement)

The following properties are removed.

| PublicRuntimeSetting Property|
| --------------------- |
| `barcode_colour_modes` |
| `intermediate_result_types` |
| `intermediate_result_saving_mode` |
| `result_coordinate_type` |
| `terminate_phase` |

| FurtherModes Property|
| --------------------- |
| `colour_clustering_modes` |
