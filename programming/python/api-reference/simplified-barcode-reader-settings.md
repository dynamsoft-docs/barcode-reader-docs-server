---
layout: default-layout
title: SimplifiedBarcodeReaderSettings Class - Dynamsoft Barcode Reader Module Python Edition API Reference
description: Definition of the SimplifiedBarcodeReaderSettings class in Dynamsoft Barcode Reader Module Python Edition.
keywords: class, python, SimplifiedBarcodeReaderSettings
needAutoGenerateSidebar: true
needGenerateH3Content: true
---

# SimplifiedBarcodeReaderSettings

The `SimplifiedBarcodeReaderSettings` class contains settings for barcode decoding. It is a sub-parameter of [`SimplifiedCaptureVisionSettings`]({{ site.dcvb_python_api }}capture-vision-router/auxiliary-classes/simplified-capture-vision-settings.html).

## Definition

*Module:* dynamsoft_barcode_reader

```python
class SimplifiedBarcodeReaderSettings
```

## Properties

| Property  | Type |
| --------- | ---- |
| [`barcode_format_ids`](#barcode_format_ids) | *ulong* |
| [`expected_barcodes_count`](#expected_barcodes_count) | *int* |
| [`grayscale_transformation_modes`](#grayscale_transformation_modes) | *List[int]* |
| [`grayscale_enhancement_modes`](#grayscale_enhancement_modes) | *List[int]* |
| [`localization_modes`](#localization_modes) | *List[int]* |
| [`deblur_modes`](#deblur_modes) | *List[int]* |
| [`min_result_confidence`](#min_result_confidence) | *int* |
| [`min_barcode_text_length`](#min_barcode_text_length) | *int* |
| [`barcode_text_regex_pattern`](#barcode_text_regex_pattern) | *str* |
| [`max_threads_in_one_task`](#max_threads_in_one_task) | *int* |
| [`scale_down_threshold`](#scale_down_threshold) | *int* |

### barcode_format_ids

Specifies the targeting format(s) of the barcode(s) to be decoded.

It is a bitwise OR combination of one or more values from the [`EnumBarcodeFormat`]({{ site.dbr_python_api }}enum-barcode-format.html) enumeration.

### expected_barcodes_count

Specifies the expected barcode count. The default value is 0.

**Remarks**

* Set `expected_barcodes_count` to 0 if the barcode count is unknown. The library will try to find at least 1 barcode.
* Set `expected_barcodes_count` to 1 to reach the highest speed for processing single barcode.
* Set `expected_barcodes_count` to "n" if there will be "n" barcodes to process from an image.
* Set `expected_barcodes_count` to the highest expected value if there exists multiple barcode but the exact count is not confirmed.

### grayscale_transformation_modes

Specifies how grayscale transformations should be applied, including whether to process inverted grayscale images and the specific transformation mode to use.

It is a list of 8 integers, where each integer represents a mode specified by the [`EnumGrayscaleTransformationMode`]({{ site.dcvb_python_api }}core/enum-grayscale-transformation-mode.html) enumeration.

View the parameter reference page of <a href="{{ site.dcvb_parameters_reference }}image-parameter/grayscale-transformation-modes.html">`GrayscaleTransformationModes`</a> for more detail about grayscale transformation modes.

### grayscale_enhancement_modes

Specifies how to enhance the quality of the grayscale image.

It is a list of 8 integers, where each integer represents a mode specified by the [`EnumGrayscaleEnhancementMode`]({{ site.dcvb_python_api }}core/enum-grayscale-enhancement-mode.html) enumeration.

View the parameter reference page of <a href="{{ site.dcvb_parameters_reference }}image-parameter/grayscale-enhancement-modes.html">`GrayscaleEnhancementModes`</a> for more detail about grayscale enhancement modes.

### localization_modes

Specifies how to localize barcodes. 

It is a list of 8 integers, where each integer represents a mode specified by the [`EnumLocalizationMode`]({{ site.dbr_python_api }}enum-localization-mode.html) enumeration.

View the parameter reference page of <a href="{{ site.dcvb_parameters_reference }}barcode-reader-task-settings/localization-modes.html">`LocalizationModes`</a> for more detail about location modes.

### deblur_modes

Specifies the mode and priority for deblurring. 

It is a list of 10 integers, where each integer represents a mode specified by the [`EnumDeblurMode`]({{ site.dbr_python_api }}enum-deblur-mode.html) enumeration.

View the parameter reference page of <a href="{{ site.dcvb_parameters_reference }}barcode-reader-task-settings/deblur-modes.html">`DeblurModes`</a> for more detail about deblur modes.

### min_result_confidence

Specifies the minimum result confidence to filter out the low confidence results. The default value is 30.

### min_barcode_text_length

Specifies the minimum barcode text length to filter out the unqualified results.

### barcode_text_regex_pattern

Specifies the RegEx pattern of the barcode text to filter out the unqualified results.

### max_threads_in_one_task

Specifies the maximum available threads count in one barcode decoding task.

**Value Range**

[1, 256]

**Default value**

4

### scale_down_threshold

Specifies the threshold for image shrinking.

**Value Range**

[512, 0x7fffffff]

**Default Value**

2300

**Remarks**

If the shorter edge size is larger than the given threshold value, the library will calculate the required height and width of the target image and shrink the image to that size before further operation. Otherwise, the library will perform operation on the original image.

## Methods
  
| Method | Description |
|------- | ---- |
| [`__init__`](#__init__) | Initializes a new instance of the `SimplifiedBarcodeReaderSettings` class. |

### \_\_init\_\_

Initializes a new instance of the `SimplifiedBarcodeReaderSettings` class.

```python
def __init__(self):
```

