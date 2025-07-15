---
layout: default-layout
title: Samples - Dynamsoft Barcode Reader SDK Python Edition
description: Sample list page of Dynamsoft Barcode Reader Python Edition.
keywords: python
needAutoGenerateSidebar: false
---

# Samples and Demos - Python Edition


## Samples

### Basic Barcode Reader Samples

| Sample Name | Description |
| --- | --- |
| <a href="https://github.com/Dynamsoft/barcode-reader-python-samples/blob/master/Samples/read_an_image.py" target="_blank">ReadAnImage</a> | Shows the simplest way to read barcodes from an image file and output barcode format and text. |
| <a href="https://github.com/Dynamsoft/barcode-reader-python-samples/blob/master/Samples/read_multiple_images.py" target="_blank">ReadMultipleImages</a> | Shows the simplest way to read barcodes from directory with image files and output barcode format and text. |
| <a href="https://github.com/Dynamsoft/barcode-reader-python-samples/blob/master/Samples/general_settings.py" target="_blank">GeneralSettings</a> | Shows how to adjust general scan settings, e.g., barcode format, barcode count, scan region. |
| <a href="https://github.com/Dynamsoft/barcode-reader-python-samples/blob/master/Samples/read_dpm_barcode.py" target="_blank">ReadDPMBarcode</a> | Shows how to read DPM (Direct Part Mark) barcodes. |
| <a href="https://github.com/Dynamsoft/barcode-reader-python-samples/blob/master/Samples/video_decoding.py" target="_blank">VideoDecoding</a> | Shows how to decode barcodes from live video or video file. |
| <a href="https://github.com/Dynamsoft/barcode-reader-python-samples/blob/master/Samples/multi_format_image_processing.py" target="_blank">MultiFormatImageProcessing</a> | Shows how to decode barcodes from various image format. |
| <a href="https://github.com/Dynamsoft/barcode-reader-python-samples/blob/master/Samples/parameter_tuner.py" target="_blank">ParameterTuner</a> | This sample demonstrates how to adjust and test different parameter settings to optimize barcode recognition performance. |
| <a href="https://github.com/Dynamsoft/barcode-reader-python-samples/blob/master/Samples/show_localized_vs_decoded_barcodes.py" target="_blank">ShowLocalizedVSDecodedBarcodes</a> | This sample demonstrates how to highlight successfully decoded and only-localized barcodes with different styles of rectangles. |
| <a href="https://github.com/Dynamsoft/barcode-reader-python-samples/blob/master/Samples/server_side_barcode_decoder.py" target="_blank">ServerSideBarcodeDecoder</a> | This sample demonstrates how to decode barcodes on the server side by sending images from a client application. |

### Additional Samples using Capture Vision SDK

In addition to the classic barcode decoding samples listed above, the following samples go a step further by parsing the decoded results and showcasing more structured workflows.

> [!IMPORTANT]
> These samples use the `dynamsoft-capture-vision-bundle` package instead of `dynamsoft-barcode-reader-bundle`. If you're switching to these samples, make sure to install and use the correct package.

| Sample Name | Description |
| --- | --- |
| <a href="https://github.com/Dynamsoft/capture-vision-python-samples/blob/main/Samples/driver_license_scanner.py" target="_blank">DriverLicenseScanner</a> | Shows how to capture and extract user's information from driver license/ID. |
| <a href="https://github.com/Dynamsoft/capture-vision-python-samples/blob/main/Samples/vin_scanner.py" target="_blank">VINScanner</a> | Shows how to capture and extract vehicle's information from Vehicle Identification Number (VIN). |
| <a href="https://github.com/Dynamsoft/capture-vision-python-samples/blob/main/Samples/gs1_ai_scanner.py" target="_blank">GS1AIScanner</a> | Shows how to extract and interpret GS1 Application Identifiers (AIs) from GS1 barcodes. |

## Official Online Demo
This <a href="https://demo.dynamsoft.com/barcode-reader/" target="_blank">Online Demo</a> is an online barcode scanner for all barcode types. All supported parameters are opened for customization to see how Dynamsoft Barcode Reader works in different usage scenarios. 
