---
layout: default-layout
title: User Guide - Dynamsoft Barcode Reader SDK Python Edition
description: This is the user guide of Dynamsoft Barcode Reader SDK Python Edition.
keywords: user guide, python
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# Getting Started with Dynamsoft Barcode Reader SDK Python Edition

In this guide, you will learn step by step on how to build a barcode reading application with Dynamsoft Barcode Reader SDK using python.

> Read more on [Dynamsoft Barcode Reader Features](https://www.dynamsoft.com/barcode-reader/features/)

- [Getting Started with Dynamsoft Barcode Reader SDK Python Edition](#getting-started-with-dynamsoft-barcode-reader-sdk-python-edition)
  - [System Requirements](#system-requirements)
  - [Installation](#installation)
  - [Build Your First Application](#build-your-first-application)
    - [Create a New Project](#create-a-new-project)
    - [Include the Library](#include-the-library)
    - [Initialize the License Key](#initialize-the-license-key)
    - [Create a CaptureVisionRouter Instance](#create-a-capturevisionrouter-instance)
    - [Invoke the Barcode Capturing](#invoke-the-barcode-capturing)
    - [Filter and Get Barcode Details](#filter-and-get-barcode-details)
    - [Build and Run the Project](#build-and-run-the-project)
  - [Process Multiple Images](#process-multiple-images)
    - [Create an ImageSource as the Input](#create-an-imagesource-as-the-input)
    - [Implement a CapturedResultReceiver as the Output Listener](#implement-a-capturedresultreceiver-as-the-output-listener)
    - [Handle Capture Stoppage by Implementing an ImageSource State Listener](#handle-capture-stoppage-by-implementing-an-imagesource-state-listener)
    - [Register the Input, Output Listener and ImageSource State Listener to the CaptureVisionRouter Instance](#register-the-input-output-listener-and-imagesource-state-listener-to-the-capturevisionrouter-instance)
    - [Start the Capturing Process](#start-the-capturing-process)
    - [Build and Run the Project Again](#build-and-run-the-project-again)

## System Requirements

To find out whether your environment is supported, please read the [System Requirements]({{ site.dbr_python }}index.html#system-requirements).

## Installation

Start terminal or command prompt to run the following command:

```
pip install dynamsoft_barcode_reader_bundle
```

## Build Your First Application

Let's start by creating a console application which demonstrates how to use the minimum code to read barcodes from an image file.

> You can <a href="https://github.com/Dynamsoft/barcode-reader-python-samples/blob/master/Samples/read_an_image.py" target="_blank">download the entire source code from here</a>.

### Create a New Project

Create a new source file named `DBRPythonSample.py`.

### Include the Library

Import package `dynamsoft_barcode_reader_bundle` in the source file.

```python
from dynamsoft_barcode_reader_bundle import *
```

### Initialize the License Key

Add the following code inside the `__main__` method to initialize the license for using the SDK in the application:

```python
errorCode, errorMsg = LicenseManager.init_license("DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9")
if errorCode != EnumErrorCode.EC_OK and errorCode != EnumErrorCode.EC_LICENSE_CACHE_USED:
    print("License initialization failed: ErrorCode:", errorCode, ", ErrorString:", errorMsg)
else:
    # codes from following steps
```

> The string "DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9" here is a free public trial license. Note that network connection is required for this license to work. When it expires, you can request a 30-day free trial license from the <a href="https://www.dynamsoft.com/customer/license/trialLicense?utm_source=guide&product=dbr&package=python" target="_blank">Customer Portal</a>.

### Create a CaptureVisionRouter Instance

```python
cvr = CaptureVisionRouter()
```

### Invoke the Barcode Capturing

```python
result = cvr.capture("[PATH-TO-THE-IMAGE-FILE]", EnumPresetTemplate.PT_READ_BARCODES.value)
```

> Please change the `[PATH-TO-THE-IMAGE-FILE]` to a real barcode image file path.

### Filter and Get Barcode Details

```python
if result.get_error_code() != EnumErrorCode.EC_OK:
    print("Error:", result.get_error_code(), result.get_error_string())
barcode_result = result.get_decoded_barcodes_result()
if barcode_result is None or barcode_result.get_items() == 0:
    print("No barcode detected.")
else:
    items = barcode_result.get_items()
    print("Decoded", len(items), "barcodes.")
    for index,item in enumerate(items):
        print("Result", index+1)
        print("Barcode Format:", item.get_format_string())
        print("Barcode Text:", item.get_text())
```

### Build and Run the Project

1. Save the `DBRPythonSample.py` file.
2. Start terminal or command prompt and change to the target directory where `DBRPythonSample.py` located in.
3. Run the command

```
python DBRPythonSample.py
```

4. You will see the output message in the console like

```
Decoded 2 barcodes
Result 1
Barcode Format: XXX
Barcode Text: XXX
Result 2
Barcode Format: XXX
Barcode Text: XXX
```

## Process Multiple Images

If, instead of processing one single image, you need to process many images at once, you can follow these steps:

> These steps follow the step [Create a CaptureVisionRouter Instance](#create-a-capturevisionrouter-instance) mentioned above.

> You can <a href="https://github.com/Dynamsoft/barcode-reader-python-samples/blob/master/Samples/read_multiple_images.py" target="_blank">download the entire source code from here</a>.


### Create an ImageSource as the Input

An `ImageSource` is required when creating a multi-image processing application. You can either utilize ready-made image sources such as [`FileFetcher`]({{ site.dcvb_python_api }}utility/file-fetcher.html) and [`DirectoryFetcher`]({{ site.dcvb_python_api }}utility/directory-fetcher.html), or customize your own image source based on the base class [`ImageSourceAdapter`]({{ site.dcvb_python_api }}core/basic-classes/image-source-adapter.html).

In this sample, we will use the `DirectoryFetcher` to retrieve images from a local directory.

```python
fetcher = DirectoryFetcher()
fetcher.set_directory("[THE DIRECTORY THAT HOLDS THE IMAGES]")
```

> Please change the `[THE DIRECTORY THAT HOLDS THE IMAGES]` to full path of the directory holding barcode image files.

### Implement a CapturedResultReceiver as the Output Listener

Create a class `MyCapturedResultReceiver` to implement the `CapturedResultReceiver` class, and get the barocde results in `on_decoded_barcodes_received` callback function.

```python
class MyCapturedResultReceiver(CapturedResultReceiver):
    def __init__(self) -> None:
        super().__init__()
    def on_decoded_barcodes_received(self, result: "DecodedBarcodesResult") -> None:
        tag = result.get_original_image_tag()
        if isinstance(tag, FileImageTag):
            print("File:", tag.get_file_path())
        if result.get_error_code() != EnumErrorCode.EC_OK:
            print("Error:", result.get_error_string())
        else:
            items = result.get_items()
            print("Detected", len(items), "barcodes.")
            for index, item in enumerate(items):
                print("Result", index+1)
                print("Barcode Format:", item.get_format_string())
                print("Barcode Text:", item.get_text())
```

### Handle Capture Stoppage by Implementing an ImageSource State Listener

Create a class `MyImageSourceStateListener` to implement the `ImageSourceStateListener` class, and call stop_capturing in `on_image_source_state_received` callback function when the state is `ISS_EXHAUSTED`.

```python
class MyImageSourceStateListener(ImageSourceStateListener):
    def __init__(self, cvr:CaptureVisionRouter) -> None:
        super().__init__()
        self.cvr = cvr
    def on_image_source_state_received(self, state: int) -> None:
        if state == EnumImageSourceState.ISS_EXHAUSTED:
            if self.cvr != None:
                self.cvr.stop_capturing()
```

### Register the Input, Output Listener and ImageSource State Listener to the CaptureVisionRouter Instance

```python
cvr.set_input(fetcher)
receiver = MyCapturedResultReceiver()
cvr.add_result_receiver(receiver)
listener = MyImageSourceStateListener(cvr)
cvr.add_image_source_state_listener(listener)
```

### Start the Capturing Process

Call the method `start_capturing()` to start processing all the images in the specified folder.

```python
errorCode, errorMsg = cvr.start_capturing("", True)
if errorCode != EnumErrorCode.EC_OK:
    print("error:", errorMsg)
```

During the process, the callback function `on_decoded_barcodes_received()` is triggered each time processing of an image is finished. After all images are processed, the listener function `on_image_source_state_received()` will be triggered while the image source state is `ISS_EXHAUSTED` and the process is stopped with the method `stop_capturing()`.

### Build and Run the Project Again

Please refer to [Build and Run the Project](#build-and-run-the-project).

