---
layout: default-layout
title: User Guide - Dynamsoft Barcode Reader SDK C++ Edition
description: This is the user guide of Dynamsoft Barcode Reader SDK C++ Edition.
keywords: user guide, c++
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# Getting Started with Dynamsoft Barcode Reader SDK C++ Edition

In this guide, you will learn step by step on how to build a barcode reading application with Dynamsoft Barcode Reader SDK using C++ language.

> Read more on [Dynamsoft Barcode Reader Features](https://www.dynamsoft.com/barcode-reader/docs/introduction/index.html)

- [Installation](#installation)
- [Build Your First Application](#build-your-first-application)
  - [Create a New Project](#create-a-new-project)
  - [Include the Library](#include-the-library)
  - [Initialize a Capture Vision Router Instance](#initialize-a-capture-vision-router-instance)
  - [Decode and Output Results](#decode-and-output-results)
  - [Build and Run the Project](#build-and-run-the-project)
- [Process Multiple Images](#process-multiple-images)
  - [Add an Image Source as the Input](#add-an-image-source-as-the-input)
  - [Add a Result Receiver as the Output](#add-a-result-receiver-as-the-output)
  - [Add an Object to Listener to the Status of the Image Source](#add-an-object-to-listener-to-the-status-of-the-image-source)
  - [Start the Process](#start-the-process)
  - [Build and Run the Project Again](#build-and-run-the-project-again)

## Installation

If you haven't downloaded the SDK yet, <a href="https://www.dynamsoft.com/barcode-reader/downloads/?utm_source=docs" target="_blank">download the `C/C++ Package`</a> now and unpack the package into a directory of your choice.

> For this tutorial, we unpack it to a pseudo directory `[INSTALLATION FOLDER]`, change it to your unpacking path for the following content.

> To find out whether your environment is supported, read the [System Requirements](https://www.dynamsoft.com/barcode-reader/docs/server/programming/cplusplus/#system-requirements).

## Build Your First Application

Let's start by creating a console application which demonstrates how to use the minimum code to read barcodes from an picture of it.

> You can <a href="https://github.com/Dynamsoft/barcode-reader-c-cpp-samples/tree/main/Samples/C%2B%2B/HelloWorld" target="_blank">download the entire source code from here</a>.

### Create a New Project

- For Windows

1. Open Visual Studio. Go to "File > New > Project..." or click "Create a new project" on the starting page, choose "Console App", create a new Empty Project and set the Project name as `DBRCPPSample`.

2. Add a new source file named `DBRCPPSample.cpp` into the project.

- For Linux

1. Create a new source file named `DBRCPPSample.cpp` and place it into the folder `[INSTALLATION FOLDER]/Samples`.

### Include the Library

1. Add headers and libs in `DBRCPPSample.cpp`.

    ```cpp
    #include <iostream>
    #include <string>
    #include "[INSTALLATION FOLDER]/Include/DynamsoftCore.h"
    #include "[INSTALLATION FOLDER]/Include/DynamsoftLicense.h"
    #include "[INSTALLATION FOLDER]/Include/DynamsoftCaptureVisionRouter.h"
    #include "[INSTALLATION FOLDER]/Include/DynamsoftBarcodeReader.h"

    using namespace std;
    using namespace dynamsoft::license;
    using namespace dynamsoft::cvr;
    using namespace dynamsoft::dbr;

    #if defined(_WIN64) || defined(_WIN32)
        #ifdef _WIN64
            #pragma comment(lib, "[INSTALLATION FOLDER]/Lib/Windows/x64/DynamsoftCorex64.lib")
            #pragma comment(lib, "[INSTALLATION FOLDER]/Lib/Windows/x64/DynamsoftLicensex64.lib")
            #pragma comment(lib, "[INSTALLATION FOLDER]/Lib/Windows/x64/DynamsoftCaptureVisionx64.lib")
            #pragma comment(lib, "[INSTALLATION FOLDER]/Lib/Windows/x64/DynamsoftBarcodeReaderx64.lib")
        #else
            #pragma comment(lib, "[INSTALLATION FOLDER]/Lib/Windows/x64/DynamsoftCorex86.lib")
            #pragma comment(lib, "[INSTALLATION FOLDER]/Lib/Windows/x86/DynamsoftLicensex86.lib")
            #pragma comment(lib, "[INSTALLATION FOLDER]/Lib/Windows/x86/DynamsoftCaptureVisionx86.lib")
            #pragma comment(lib, "[INSTALLATION FOLDER]/Lib/Windows/x64/DynamsoftBarcodeReaderx86.lib")
        #endif
    #endif
    ```

### Initialize a Capture Vision Router Instance

1. Initialize the license key.

    ```cpp
    char errorMsg1[256];
    CLicenseManager::InitLicense("DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9", errorMsg1, 256);
    ```

    > The string "DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9" here is a free public trial license. Note that network connection is required for this license to work. When it expires, you can request a 30-day free trial license from the <a href="https://www.dynamsoft.com/customer/license/trialLicense?utm_source=guide&product=dbr&package=desktop" target="_blank">Customer Portal</a>.

2. Create an instance of Capture Vision Router.

    ```cpp
    CCaptureVisionRouter cvr;
    ```

### Decode and Output Results

1. Decode barcodes from an image file.

    ```cpp
    CCapturedResultArray* results = cvr.Capture("[INSTALLATION FOLDER]/Images/sample-image.jpg", PresetTemplate::PT_READ_BARCODES);
    int capturedResultCount = results->GetCount();
    for (int i = 0; i < count; i++) {
        const CCapturedResult* capturedResult = results->GetResult(i);
        int capturedResultItemCount = capturedResult->GetCount();
        for (int j = 0; j < capturedResultItemCount; j++) {
            const CCapturedResultItem* capturedResultItem = capturedResult->GetItem(j);
            /*
            * There can be multiple types of result items per image.
            * We check each of these items until we find the barcode result.
            */
            CapturedResultItemType type = capturedResultItem->GetType();
            if (type | CapturedResultItemType::CRIT_BARCODE) {
                CBarcodeResultItem* barcodeResultItem = dynamic_cast<const CBarcodeResultItem*> (capturedResultItem);
                cout << "Barcode Format: " << barcodeResultItem->GetFormatString() << endl;
                cout << "Barcode Text: " << barcodeResultItem->GetText() << endl;
            }
        }
    }
    ```

> Note:
> 
> Please change all `[INSTALLATION FOLDER]` in above code snippet to your unpacking path.

### Build and Run the Project

- For Windows

1. In Visual Studio, set the solution to build as Release\|x64.

2. Build the project to generate program `DBRCPPSample.exe`.

3. Copy **ALL** `*.dll` files under `[INSTALLATION FOLDER]\Lib\Windows\x64` to the same folder as the `DBRCPPSample.exe` ("[PROJECT FOLDER]\DBRCPPSample\x64\Debug").

4. Run the program `DBRCPPSample.exe`.

> The SDK supports both x86 and x64, please set the platform based on your needs.

- For Linux

1. Open a terminal and change to the target directory where `DBRCPPSample.cpp` is located. Build the sample:

    ```bash
    g++ -o DBRCPPSample DBRCPPSample.cpp -lDynamsoftCore -lDynamsoftBarcodeReader -L ../Lib/Linux -Wl,-rpath=../Lib/Linux -std=c++11
    ```

2. Run the program `DBRCPPSample`.

    ```bash
    ./DBRCPPSample
    ```

> You can <a href="https://github.com/Dynamsoft/barcode-reader-c-cpp-samples/tree/main/Samples/C%2B%2B/HelloWorld" target="_blank">download the entire source code from here</a>.

## Process Multiple Images

If, instead of processing one single image, you need to process many images at once, you can follow these steps:

> These steps follow the step [Initialize a Capture Vision Router Instance](#initialize-a-capture-vision-router-instance) mentioned above.

### Add an Image Source as the Input

The class `DirectoryFetcher` is capable of converting a local directory to an image source. We will use it to connect multiple images to the image-processing engine.

1. Include the header file.

    ```cpp
    // Add the following lines
    #include "Include/DynamsoftUtility.h"
    using namespace dynamsoft::utility;
    #ifdef _WIN64
    #pragma comment(lib, "Lib/x64/DynamsoftUtilityx64.lib")
    #else
    #pragma comment(lib, "Lib/x86/DynamsoftUtilityx86.lib")
    #endif
    ```

2. Create a `DirectoryFetcher` object and use it as the image source.

    ```cpp
    CDirectoryFetcher fetcher;
    fetcher.SetDirectory("[THE DIRECTORY THAT HOLDS THE IMAGES]");
    cvr.SetInput(&fetcher);
    ```

### Add a Result Receiver as the Output

1. Define the receiver class.

    ```cpp
    class MyCapturedResultReceiver : public CCapturedResultReceiver {
        void OnDecodedBarcodesReceived(const CDecodedBarcodesResult* pResult) {
            int count = pResult->GetCount();
            for (int i = 0; i < count; i++) {
                const CBarcodeResultItem* barcodeResultItem = pResult->GetItem(i);
                if (barcodeResultItem != NULL)
                {
                    cout << "Result " << i + 1 << endl;
                    cout << "Barcode Format: " << barcodeResultItem->GetFormatString() << endl;
                    cout << "Barcode Text: " << barcodeResultItem->GetText() << endl;
                }
            }
        }
    };
    ```

2. Create a receiver object and set it as the output.

    ```cpp
    MyCapturedResultReceiver capturedReceiver;
    cvr.AddResultReceiver(&capturedReceiver);
    ```

### Add an Object to Listener to the Status of the Image Source

1. Define the listener class.

    ```cpp
    class MyImageSourceAdapterStateListener : public virtual CImageSourceAdapterStateListener {
    public:
        CCaptureVisionRouter* cvr = NULL;
        void OnImageSourceAdapterStateChanged(ImageSourceState state) {
            if (state == ISS_EXHAUSTED) {
                cvr->StopCapturing();
            }
        }
    };
    ```

2. Create a listener object and connect it to the image source

    ```cpp
    MyImageSourceAdapterStateListener listener;
    listener.cvr = &cvr;
    cvr.AddImageSourceAdapterStateListener(&listener);
    ```

### Start the Process

Call the method `StartCapturing()` to start processing all the images in the specified folder.

```cpp
char error2[512];
int ret2 = cvr.StartCapturing(PresetTemplate::PT_READ_BARCODES, true, error2, 512);        
```

During the process, the callback function `OnDecodedBarcodesReceived()` is triggered each time an image finishes processing. After all images are processed, the listener function `OnImageSourceAdapterStateChanged()` will return the image source state as `ISS_EXHAUSTED` and the process is stopped with the method `StopCapturing()`.

### Build and Run the Project Again

Please refer to [Build and Run the Project](#build-and-run-the-project).
