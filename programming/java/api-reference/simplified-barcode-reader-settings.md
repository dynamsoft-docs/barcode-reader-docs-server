---
layout: default-layout
title: SimplifiedBarcodeReaderSettings Class - Dynamsoft Barcode Reader Java Edition API Reference
description: Definition of the SimplifiedBarcodeReaderSettings class in Dynamsoft Barcode Reader Java Edition.
keywords: class, java, SimplifiedBarcodeReaderSettings
needAutoGenerateSidebar: true
needGenerateH3Content: true
---

# SimplifiedBarcodeReaderSettings

The `SimplifiedBarcodeReaderSettings` class contains settings for barcode decoding. It is a sub-parameter of [`SimplifiedCaptureVisionSettings`]({{ site.dcvb_java_api }}capture-vision-router/auxiliary-classes/simplified-capture-vision-settings.html).

## Definition

*Package:* com.dynamsoft.dbr

```java
public class SimplifiedBarcodeReaderSettings
```

## Attributes

| Attribute | Type | Description |
| --------- | ---- | ----------- |
| [`barcodeFormatIds`](#barcodeformatids) | *long* | Specifies the targeting format(s) of the barcode(s) to be decoded. |
| [`expectedBarcodesCount`](#expectedbarcodescount) | *int* | Specifies the expected barcode count. |
| [`grayscaleTransformationModes`](#grayscaletransformationmodes) | *int[]* | Sets the grayscale transformation modes. |
| [`grayscaleEnhancementModes`](#grayscaleenhancementmodes) | *int[]* | Sets the grayscale enhancement modes. |
| [`localizationModes`](#localizationmodes) | *int[]* | Sets the localization modes. |
| [`deblurModes`](#deblurmodes) | *int[]* | Sets the deblur modes. |
| [`minResultConfidence`](#minresultconfidence) | *int* | Sets the minimum result confidence. |
| [`minBarcodeTextLength`](#minbarcodetextlength) | *int* | Sets the minimum barcode text length. |
| [`barcodeTextRegExPattern`](#barcodetextregexpattern) | *String* | Sets the regex pattern for barcode text. |
| [`maxThreadsInOneTask`](#maxthreadsinonetask) | *int* | Sets the maximum threads in one task. |
| [`scaleDownThreshold`](#scaledownthreshold) | *int* | Sets the scale down threshold. |

## Attribute Details

### barcodeFormatIds

Specifies the targeting format(s) of the barcode(s) to be decoded.

```java
public long barcodeFormatIds
```

It is a bitwise OR combination of one or more values from the [`EnumBarcodeFormat`]({{ site.dbr_java_api }}enum-barcode-format.html) enumeration.

### expectedBarcodesCount

Specifies the expected barcode count. The default value is 0.

```java
public int expectedBarcodesCount
```

**Remarks**

* Set `expectedBarcodesCount` to 0 if the barcode count is unknown. The library will try to find at least 1 barcode.
* Set `expectedBarcodesCount` to 1 to reach the highest speed for processing single barcode.
* Set `expectedBarcodesCount` to "n" if there will be "n" barcodes to process from an image.
* Set `expectedBarcodesCount` to the highest expected value if there exists multiple barcode but the exact count is not confirmed.

### grayscaleTransformationModes

Specifies how grayscale transformations should be applied, including whether to process inverted grayscale images and the specific transformation mode to use.

```java
public int[] grayscaleTransformationModes
```

It is an array of 8 integers, where each integer represents a mode specified by the [`EnumGrayscaleTransformationMode`]({{ site.dcvb_java_api }}core/enum-grayscale-transformation-mode.html) enumeration.

View the parameter reference page of <a href="{{ site.dcvb_parameters_reference }}image-parameter/grayscale-transformation-modes.html">`GrayscaleTransformationModes`</a> for more detail about grayscale transformation modes.

### grayscaleEnhancementModes

Specifies how to enhance the quality of the grayscale image.

```java
public int[] grayscaleEnhancementModes
```

It is an array of 8 integers, where each integer represents a mode specified by the [`EnumGrayscaleEnhancementMode`]({{ site.dcvb_java_api }}core/enum-grayscale-enhancement-mode.html) enumeration.

View the parameter reference page of <a href="{{ site.dcvb_parameters_reference }}image-parameter/grayscale-enhancement-modes.html">`GrayscaleEnhancementModes`</a> for more detail about grayscale enhancement modes.

### localizationModes

Specifies how to localize barcodes.

```java
public int[] localizationModes
```

It is an array of 8 integers, where each integer represents a mode specified by the [`EnumLocalizationMode`]({{ site.dbr_java_api }}enum-localization-mode.html) enumeration.

View the parameter reference page of <a href="{{ site.dcvb_parameters_reference }}barcode-reader-task-settings/localization-modes.html">`LocalizationModes`</a> for more detail about location modes.

### deblurModes

Specifies the mode and priority for deblurring.

```java
public int[] deblurModes
```

It is an array of 10 integers, where each integer represents a mode specified by the [`EnumDeblurMode`]({{ site.dbr_java_api }}enum-deblur-mode.html) enumeration.

View the parameter reference page of <a href="{{ site.dcvb_parameters_reference }}barcode-reader-task-settings/deblur-modes.html">`DeblurModes`</a> for more detail about deblur modes.

### minResultConfidence

Specifies the minimum result confidence to filter out the low confidence results. The default value is 30.

```java
public int minResultConfidence
```

### minBarcodeTextLength

Specifies the minimum barcode text length to filter out the unqualified results.

```java
public int minBarcodeTextLength
```

### barcodeTextRegExPattern

Specifies the RegEx pattern of the barcode text to filter out the unqualified results.

```java
public String barcodeTextRegExPattern
```

### maxThreadsInOneTask

Specifies the maximum available threads count in one barcode decoding task.

```java
public int maxThreadsInOneTask
```

**Value Range**

[1, 256]

**Default value**

4

### scaleDownThreshold

Specifies the threshold for image shrinking.

```java
public int scaleDownThreshold
```

**Value Range**

[512, 0x7fffffff]

**Default Value**

2300

**Remarks**

If the shorter edge size is larger than the given threshold value, the library will calculate the required height and width of the target image and shrink the image to that size before further operation. Otherwise, the library will perform operation on the original image.

