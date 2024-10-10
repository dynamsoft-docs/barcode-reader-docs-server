---
layout: default-layout
title: SimplifiedBarcodeReaderSettings Class - Dynamsoft Barcode Reader Module .NET Edition API Reference
description: Definition of the SimplifiedBarcodeReaderSettings class of the CaptureVisionRouter class in Dynamsoft Barcode Reader Module .NET Edition.
keywords: class, .NET, SimplifiedBarcodeReaderSettings
needAutoGenerateSidebar: true
needGenerateH3Content: true
---

# SimplifiedBarcodeReaderSettings

The `SimplifiedBarcodeReaderSettings` class contains settings for barcode decoding. It is a sub-parameter of [`SimplifiedCaptureVisionSettings`]({{ site.dcv_dotnet_api }}capture-vision-router/auxiliary-classes/simplified-capture-vision-settings.html).

## Definition

*Namespace:* Dynamsoft.DBR

*Assembly:* Dynamsoft.BarcodeReader.dll

```csharp
public class SimplifiedBarcodeReaderSettings
```

## Attributes

| Attribute | Type |
| --------- | ---- |
| [`barcodeFormatIds`](#barcodeformatids) | *ulong* |
| [`expectedBarcodesCount`](#expectedbarcodescount) | *int* |
| [`grayscaleTransformationModes`](#grayscaletransformationmodes) | *EnumGrayscaleTransformationMode[]* |
| [`grayscaleEnhancementModes`](#grayscaleenhancementmodes) | *EnumGrayscaleEnhancementMode[]* |
| [`localizationModes`](#localizationmodes) | *EnumLocalizationMode[]* |
| [`deblurModes`](#deblurmodes) | *EnumDeblurMode[]* |
| [`minResultConfidence`](#minresultconfidence) | *int* |
| [`minBarcodeTextLength`](#minbarcodetextlength) | *int* |
| [`barcodeTextRegExPattern`](#barcodetextregexpattern) | *string* |
| [`maxThreadsInOneTask`](#maxthreadsinonetask) | *int* |
| [`scaleDownThreshold`](#scaledownthreshold) | *int* |

### barcodeFormatIds

Input a combined value of enumeration [`EnumBarcodeFormat`]({{ site.dcvb_enumerations }}barcode-reader/barcode-format.html?lang=dotnet) to specify the targeting barcode formats.

```csharp
ulong barcodeFormatIds;
```

### expectedBarcodesCount

Set the expected barcode count. The default value is 0.

```csharp
int expectedBarcodesCount;
```

**Remarks**

* Set `expectedBarcodesCount` to 0 if the barcode count is unknown. The library will try to find at least 1 barcode.
* Set `expectedBarcodesCount` to 1 to reach the highest speed for processing single barcode.
* Set `expectedBarcodesCount` to "n" if there will be "n" barcodes to process from an image.
* Set `expectedBarcodesCount` to the highest expected value if there exists multiple barcode but the exact count is not confirmed.

### grayscaleTransformationModes

Set the grayscale transformation modes using an [`EnumGrayscaleTransformationMode`]({{ site.dcvb_enumerations }}core/grayscale-transformation-mode.html?lang=dotnet) array with 8 elements. View the reference page of <a href="{{ site.dcvb_parameters_reference }}image-parameter/grayscale-transformation-modes.html">`GrayscaleTransformationModes`</a> for more detail about grayscale transformation modes.

```csharp
EnumGrayscaleTransformationMode[] grayscaleTransformationModes;
```

### grayscaleEnhancementModes

Set the grayscale enhancement modes using an [`EnumGrayscaleEnhancementMode`]({{ site.dcvb_enumerations }}core/grayscale-enhancement-mode.html?lang=dotnet) array with 8 elements. View the reference page of <a href="{{ site.dcvb_parameters_reference }}image-parameter/grayscale-enhancement-modes.html">`GrayscaleEnhancementModes`</a> for more detail about grayscale enhancement modes.

```csharp
EnumGrayscaleEnhancementMode[] grayscaleEnhancementModes;
```

### localizationModes

Set the location modes using an [`EnumLocalizationMode`]({{ site.dcvb_enumerations }}barcode-reader/localization-mode.html?lang=dotnet) array with 8 elements. View the reference page of <a href="{{ site.dcvb_parameters_reference }}barcode-reader-task-settings/localization-modes.html">`LocalizationModes`</a> for more detail about location modes.

```csharp
EnumLocalizationMode[] localizationModes;
```

### deblurModes

Set the deblur modes using an [`EnumDeblurMode`]({{ site.dcvb_enumerations }}barcode-reader/deblur-mode.html?lang=dotnet) array with 10 elements. View the reference page of <a href="{{ site.dcvb_parameters_reference }}barcode-reader-task-settings/deblur-modes.html">`DeblurModes`</a> for more detail about deblur modes.

```csharp
EnumDeblurMode[] deblurModes;
```

### minResultConfidence

Set the minimum result confidence to filter out the low confidence results. The default value is 30.

```csharp
int minResultConfidence;
```

### minBarcodeTextLength

Set the minimum barcode text length to filter out the unqualified results.

```csharp
int minBarcodeTextLength;
```

### barcodeTextRegExPattern

Set the RegEx pattern of the barcode text to filter out the unqualified results.

```csharp
string barcodeTextRegExPattern;
```

### maxThreadsInOneTask

Set the maximum available threads count in one barcode decoding task.

```csharp
int maxThreadsInOneTask;
```

**Value Range**

[1, 256]

**Default value**

4

### scaleDownThreshold

Set the threshold for image shrinking.

```csharp
int scaleDownThreshold;
```

**Value Range**

[512, 0x7fffffff]

**Default Value**

2300

**Remarks**

If the shorter edge size is larger than the given threshold value, the library will calculate the required height and width of the target image and shrink the image to that size before further operation. Otherwise, the library will perform operation on the original image.

