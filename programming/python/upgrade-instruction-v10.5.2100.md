---
title: Upgrade Instructions - Dynamsoft Barcode Reader SDK Python Edition
keywords: python, upgrade
description: This page introduces how to upgrade Dynamsoft Barcode Reader SDK Python Edition
needAutoGenerateSidebar: true
needGenerateH3Content: true
---

# How to Upgrade

## From version 9.x or earlier to version 10.x

Dynamsoft Barcode Reader SDK has been refactored to integrate with [`DynamsoftCaptureVision (DCV)`]({{ site.dcvb_architecture }}) architecture. To upgrade from version 9.x or earlier to 10.x, we recommend you to follow the [User Guide]({{ site.dbr_python }}user-guide.html) and re-write your codes.

### Update the License Key

#### Request a 30-Day Free Trial License

Visit the [Request a Trial License](https://www.dynamsoft.com/customer/license/trialLicense?product=dbr&utm_source=docs){:target="_blank"} page to obtain a 30-day free license. This option is ideal for initial evaluation or testing of new SDK features.

#### Annual Online Full License

If you are using an Annual Online Full License, your license will continue to work with the current SDK version without the need for updates. Go to <a href="https://www.dynamsoft.com/customer/license/fullLicense" target="_blank">Customer Portal</a> to get your license key.

#### Perpetual License

For users with a Perpetual License, please contact our sales team to update your license. You can reach out through our [Contacting Us](https://www.dynamsoft.com/contact/){:target="_blank"} page for assistance.

### Migrate to New Package

As of version 10.0, the `dbr` package has been renamed to `dynamsoft-barcode-reader-bundle` to reflect changes in both architecture and API design. Start terminal or command prompt and run the following command to install the new package.

```bash
pip install dynamsoft-barcode-reader-bundle
```

### Update the License Activation Code

Starting from 10.0, we have unified the API for setting licenses across different Dynamsoft products.

| Old APIs | New APIs |
| :----------- | :------- |
| `BarcodeReader.init_license` | [`LicenseManager.init_license`]({{ site.dcvb_python_api }}license/license-manager.html#init_license) |

### Update Single Image Decoding APIs

The APIs for decoding single image has been adjusted as follows:

| Old APIs | New APIs |
| :----------- | :------- |
| `BarcodeReader.decode_file` | [`CaptureVisionRouter.capture`]({{ site.dcvb_python_api }}capture-vision-router/single-file-processing.html#capture) |
| `BarcodeReader.decode_file_stream` | [`CaptureVisionRouter.capture`]({{ site.dcvb_python_api }}capture-vision-router/single-file-processing.html#capture) |
| `BarcodeReader.decode_buffer_manually` | [`CaptureVisionRouter.capture`]({{ site.dcvb_python_api }}capture-vision-router/single-file-processing.html#capture) |
| `class TextResult` | [`class BarcodeResultItem`]({{ site.dbr_python_api }}barcode-result-item.html) |
| `BarcodeReader.decode_base64_string` | **Currently not available**. |
| `BarcodeReader.decode_buffer` | [`CaptureVisionRouter.capture`]({{ site.dcvb_python_api }}capture-vision-router/single-file-processing.html#capture)(Available since v10.4.2100) |

### Update Video Streaming Decoding Code

`ImageSourceAdapter` is added to replace the `FrameDecodeingParameters` and the previous video methods. You should implement `ImageSourceAdapter` to transfer image data from camera or video file to buffer.


### Migrate Your Templates

The template system is upgraded. The template you used for the previous version can't be directly recognized by the new version. Please <a href="https://download2.dynamsoft.com/dcv/TemplateConverter.zip" target="_blank">download the TemplateConverter tool</a> or <a href="https://www.dynamsoft.com/company/customer-service/#contact" target="_blank">contact us</a> to upgrade your template.

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

### Migrate Your PublicRuntimeSetting

The class `PublicRuntimeSetting` has been refactored. It retains commonly used properties via `SimplifiedCaptureVisionSettings` while removing the previously complex property settings, which are now exclusively supported through templates.

The APIs for accessing and updating runtime settings has been adjusted as follows:

| Old APIs | New APIs |
| :----------- | :------- |
| `BarcodeReader.get_runtime_settings` | [`CaptureVisionRouter.get_simplified_settings`]({{ site.dcvb_python_api }}capture-vision-router/settings.html#get_simplified_settings) |
| `BarcodeReader.update_runtime_settings` | [`CaptureVisionRouter.update_settings`]({{ site.dcvb_python_api }}capture-vision-router/settings.html#update_settings) |

#### Migrate to SimplifiedCaptureVisionSettings

The following properties are replaced by similar properties under `SimplifiedCaptureVisionSettings`. They can also be set via a template file(String).

| PublicRuntimeSetting Property | SimplifiedCaptureVisionSettings Parameter | Template File Parameter |
| ------------------------------- | ----------------------------------------- | ----------------------- |
| `region` | [`roi`]({{ site.dcvb_python_api }}capture-vision-router/auxiliary-classes/simplified-capture-vision-settings.html#roi) & [`roi_measured_in_percentage`]({{ site.dcvb_python_api }}capture-vision-router/auxiliary-classes/simplified-capture-vision-settings.html#roi_measured_in_percentage) | [`TargetROIDef.Location.Offset`]({{ site.dcvb_parameters_reference }}target-roi-def/location.html) |
| `timeout` | [`timeout`]({{ site.dcvb_python_api }}capture-vision-router/auxiliary-classes/simplified-capture-vision-settings.html#timeout) | [`CaptureVisionTemplates.Timeout`]({{ site.dcvb_parameters_reference }}capture-vision-template/timeout.html) |

#### Migrate to SimplifiedBarcodeReaderSettings

The following properties are replaced by similar properties under `SimplifiedBarcodeReaderSettings`. The majority of them can also be set via a template file(String).

| PublicRuntimeSetting Property | SimplifiedBarcodeReaderSettings Property | Template File Parameter |
| ------------------------------- | ----------------------------------------- | ----------------------- |
| `min_barcode_text_length` | [`min_barcode_text_length`]({{ site.dbr_python_api }}simplified-barcode-reader-settings.html#min_barcode_text_length) | [`BarcodeFormatSpecification.BarcodeTextLengthRangeArray`]({{ site.dcvb_parameters_reference }}barcode-format-specification/barcode-text-length-range-array.html) |
| `min_result_confidence` | [`min_result_confidence`]({{ site.dbr_python_api }}simplified-barcode-reader-settings.html#min_result_confidence) | [`BarcodeFormatSpecification.MinResultConfidence`]({{ site.dcvb_parameters_reference }}barcode-format-specification/min-result-confidence.html) |
| `localization_modes` | [`localization_modes`]({{ site.dbr_python_api }}simplified-barcode-reader-settings.html#localization_modes) | [`BarcodeReaderTaskSetting.LocationModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/localization-modes.html) |
| `expected_barcodes_count` | [`expected_barcodes_count`]({{ site.dbr_python_api }}simplified-barcode-reader-settings.html#expected_barcodes_count) | [`BarcodeReaderTaskSetting.ExpectedBarcodesCount`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/expected-barcodes-count.html) |
| `barcode_format_ids` | [`barcode_format_ids`]({{ site.dbr_python_api }}simplified-barcode-reader-settings.html#barcode_format_ids) | [`BarcodeReaderTaskSetting.BarcodeFormatIds`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/barcode-format-ids.html) |
| `barcode_format_ids_2` | [`barcode_format_ids`]({{ site.dbr_python_api }}simplified-barcode-reader-settings.html#barcode_format_ids) | [`BarcodeReaderTaskSetting.BarcodeFormatIds`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/barcode-format-ids.html) |
| `deblur_modes` | [`deblur_modes`]({{ site.dbr_python_api }}simplified-barcode-reader-settings.html#deblur_modes) | [`BarcodeReaderTaskSetting.DeblurModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/deblur-modes.html) |
| `deblur_level` | [`deblur_modes`]({{ site.dbr_python_api }}simplified-barcode-reader-settings.html#deblur_modes) | [`BarcodeReaderTaskSetting.DeblurModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/deblur-modes.html) |
| `max_algorithm_thread_count` | [`max_threads_in_one_task`]({{ site.dbr_python_api }}simplified-barcode-reader-settings.html#max_threads_in_one_task) | [`BarcodeReaderTaskSetting.MaxThreadsInOneTask`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/max-threads-in-one-task.html) |
| `grayscale_transformation_modes` | [`grayscale_transformation_modes`]({{ site.dbr_python_api }}simplified-barcode-reader-settings.html#grayscale_transformation_modes) | [`ImageParameter.GrayscaleTransformationModes`]({{ site.dcvb_parameters_reference }}image-parameter/grayscale-enhancement-modes.html) |
| `image_preprocessing_modes` | [`grayscale_enhancement_modes`]({{ site.dbr_python_api }}simplified-barcode-reader-settings.html#grayscale_enhancement_modes) | [`ImageParameter.GrayscaleEnhancementModes`]({{ site.dcvb_parameters_reference }}image-parameter/grayscale-transformation-modes.html) |

> Remarks:
>
> * The 2 groups of barcode formats are merged.
> * `deblur_level` is deprecated. You can use `deblur_modes` instead.
> * The mode `IPM_MORPHOLOGY` of `imagePreprocessingModes` is migrated to `BinarizationModes`. The mode arguments `MorphOperation`, `MorphOperationKernelSizeX`, `MorphOperationKernelSizeY`, `MorphShape` are now available for all modes of `BinarizationModes`.

#### Migrate to Template File

The following properties can only be set via a template file. Please [contact us](https://www.dynamsoft.com/company/customer-service/#contact){:target="_blank"} so that we can help you to transform your current settings to a new template file.

| PublicRuntimeSetting Property | Template File Parameter |
| ------------------------------- | ----------------------- |
| `scale_down_threshold` | [`ImageParameter.ScaleDownThreshold`]({{ site.dcvb_parameters_reference }}image-parameter/scale-down-threshold.html) |
| `binarization_modes` | [`ImageParameter.BinarizationModes`]({{ site.dcvb_parameters_reference }}image-parameter/binarization-modes.html) |
| `text_result_order_modes` | [`BarcodeReaderTaskSetting.TextResultOrderModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/text-result-order-modes.html) |
| `return_barcode_zone_clarity` | [`BarcodeReaderTaskSetting.ReturnBarcodeZoneClarity`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/return-barcode-zone-clarity.html) |
| `scale_up_modes` | [`ImageParameter.ScaleUpModes`]({{ site.dcvb_parameters_reference }}image-parameter/scale-up-modes.html) |
| `barcode_zone_min_distance_to_image_borders` | [`BarcodeFormatSpecification.BarcodeZoneMinDistanceToImageBorders`]({{ site.dcvb_parameters_reference }}barcode-format-specification/barcode-zone-min-distance-to-image-borders.html) |
| `terminate_phase` | [`BarcodeReaderTaskSetting.TerminateSettings`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/terminate-setting.html) |
| `colour_conversion_modes` | [`ImageParameter.ColourConversionModes`]({{ site.dcvb_parameters_reference }}image-parameter/colour-conversion-modes.html) |
| `region_predetection_modes` | [`ImageParameter.RegionPredetectionModes`]({{ site.dcvb_parameters_reference }}image-parameter/region-predetection-modes.html) |
| `texture_detection_modes` | [`ImageParameter.TextureDetectionModes`]({{ site.dcvb_parameters_reference }}image-parameter/texture-detection-modes.html) |
| `text_filter_modes` | [`ImageParameter.TextDetectionMode`]({{ site.dcvb_parameters_reference }}image-parameter/text-detection-mode.html) & [`ImageParameter.IfEraseTextZone`]({{ site.dcvb_parameters_reference }}image-parameter/if-erase-text-zone.html) |
| `dpm_code_reading_modes` | [`BarcodeReaderTaskSetting.DPMCodeReadingModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/dpm-code-reading-modes.html) |
| `deformation_resisting_modes` | [`BarcodeReaderTaskSetting.DeformationResistingModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/deformation-resisting-modes.html) |
| `barcode_complement_modes` | [`BarcodeReaderTaskSetting.BarcodeComplementModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/barcode-complement-modes.html) |
| `barcode_colour_modes` | [`BarcodeReaderTaskSetting.BarcodeColourModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/barcode-colour-modes.html) |

#### Migrate to Other APIs

The PDF properties of `PublicRuntimeSetting` are moved to set via the `set_pdf_reading_parameter` method of [`DirectoryFetcher`]({{ site.dcvb_python_api }}utility/directory-fetcher.html) and [`FileFetcher`]({{ site.dcvb_python_api }}utility/file-fetcher.html) with a [`PDFReadingParameter`]({{ site.dcvb_python_api }}core/basic-classes/pdf-reading-parameter.html) parameter.

| PublicRuntimeSetting Property |
| ----------------------------- |
| `pdf_reading_mode` |
| `pdf_raster_dpi` |

The `Intermediate Result` system is redesigned and the following properties are deprecated.

| PublicRuntimeSetting Property |
| --------------------- |
| `intermediate_result_types` |
| `intermediate_result_saving_mode` |

#### Removed

The following properties are removed.

| PublicRuntimeSetting Property|
| --------------------- |
| `result_coordinate_type` |

| FurtherModes Property|
| --------------------- |
| `colour_clustering_modes` |
