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

> Read more on [Dynamsoft Barcode Reader Features](https://www.dynamsoft.com/barcode-reader/features/)

- [Getting Started with Dynamsoft Barcode Reader SDK C++ Edition](#getting-started-with-dynamsoft-barcode-reader-sdk-c-edition)
  - [Installation](#installation)
  - [Build Your First Application](#build-your-first-application)
    - [Create a New Project](#create-a-new-project)
    - [Include the Library](#include-the-library)
    - [Initialize a Capture Vision Router Instance](#initialize-a-capture-vision-router-instance)
    - [Decode and Output Results](#decode-and-output-results)
    - [Release the Allocated Memory](#release-the-allocated-memory)
    - [Build and Run the Project](#build-and-run-the-project)
  - [Process Multiple Images](#process-multiple-images)
    - [Add an Image Source as the Input](#add-an-image-source-as-the-input)
    - [Add a Result Receiver as the Output](#add-a-result-receiver-as-the-output)
    - [Add an Object to Listen to the Status of the Image Source](#add-an-object-to-listen-to-the-status-of-the-image-source)
    - [Start the Process](#start-the-process)
    - [Release the Allocated Memory](#release-the-allocated-memory-1)
    - [Build and Run the Project Again](#build-and-run-the-project-again)

## Installation

If you haven't downloaded the SDK yet, <a href="https://www.dynamsoft.com/barcode-reader/downloads/?utm_source=docs" target="_blank">download the `C/C++ Package`</a> now and unpack it into a directory of your choice.

> For this tutorial, we will unpack it to a pseudo directory named `[INSTALLATION FOLDER]`. Please change it to your preferred unpacking path for the following content.

> To find out whether your environment is supported, please read the [System Requirements]({{site.dbr_cpp}}index.html#system-requirements).

## Build Your First Application

Let's start by creating a console application which demonstrates how to use the minimum code to read barcodes from an picture of it.

> You can <a href="https://github.com/Dynamsoft/barcode-reader-c-cpp-samples/tree/main/Samples/HelloWorld/ReadAnImage" target="_blank">download the entire source code from here</a>.

### Create a New Project

- For Windows

1. Open Visual Studio. Go to "File > New > Project..." or click "Create a new project" on the starting page, choose "Console App", create a new Empty Project and set the Project name as `DBRCPPSample`.

2. Add a new source file named `DBRCPPSample.cpp` into the project.

- For Linux

   Create a new source file named `DBRCPPSample.cpp` and place it into the folder `[INSTALLATION FOLDER]/DynamsoftBarcodeReader/Samples`.

### Include the Library

Add headers and libs in `DBRCPPSample.cpp`.

```cpp
#include <iostream>
#include <string>
#include "[INSTALLATION FOLDER]/DynamsoftBarcodeReader/Include/DynamsoftCaptureVisionRouter.h"

using namespace std;
using namespace dynamsoft::license;
using namespace dynamsoft::cvr;
using namespace dynamsoft::dbr;

#if defined(_WIN64) || defined(_WIN32)
    #ifdef _WIN64
        #pragma comment(lib, "[INSTALLATION FOLDER]/DynamsoftBarcodeReader/Dist/Lib/Windows/x64/DynamsoftLicensex64.lib")
        #pragma comment(lib, "[INSTALLATION FOLDER]/DynamsoftBarcodeReader/Dist/Lib/Windows/x64/DynamsoftCaptureVisionRouterx64.lib")
    #else
        #pragma comment(lib, "[INSTALLATION FOLDER]/DynamsoftBarcodeReader/Dist/Lib/Windows/x86/DynamsoftLicensex86.lib")
        #pragma comment(lib, "[INSTALLATION FOLDER]/DynamsoftBarcodeReader/Dist/Lib/Windows/x86/DynamsoftCaptureVisionRouterx86.lib")
    #endif
#endif
```

### Initialize a Capture Vision Router Instance

Initialize the license key.

```cpp
char errorMsg[512];
CLicenseManager::InitLicense("DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9", errorMsg, 512);
```

> The string "DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9" here is a free public trial license. Note that network connection is required for this license to work. When it expires, you can request a 30-day free trial license from the <a href="https://www.dynamsoft.com/customer/license/trialLicense?utm_source=guide&product=dbr&package=c_cpp" target="_blank">Customer Portal</a>.

Create an instance of Capture Vision Router.

```cpp
CCaptureVisionRouter* cvRouter = new CCaptureVisionRouter;
```

### Decode and Output Results

Decode barcodes from an image file.

```cpp
string imageFile = "[PATH-TO-A-BARCODE-IMAGE]";
CCapturedResult* result = cvRouter->Capture(imageFile.c_str(), CPresetTemplate::PT_READ_BARCODES);
if (result->GetErrorCode() != 0) {
    cout << "Error: " << result->GetErrorCode() << "," << result->GetErrorString() << endl;
}
CDecodedBarcodesResult *barcodeResult = result->GetDecodedBarcodesResult();
if (barcodeResult == nullptr || barcodeResult->GetItemsCount() == 0)
{
    cout << "No barcode found." << endl;
}
else
{
    int barcodeResultItemCount = barcodeResult->GetItemsCount();
    cout << "Decoded " << barcodeResultItemCount << " barcodes" << endl;
    for (int j = 0; j < barcodeResultItemCount; j++)
    {
        const CBarcodeResultItem *barcodeResultItem = barcodeResult->GetItem(j);
        cout << "Result " << j + 1 << endl;
        cout << "Barcode Format: " << barcodeResultItem->GetFormatString() << endl;
        cout << "Barcode Text: " << barcodeResultItem->GetText() << endl;
    }
}
```

> Note:
> 
> Please change all `[INSTALLATION FOLDER]` in above code snippet to your unpacking path.

### Release the Allocated Memory

```cpp
if (barcodeResult)
    barcodeResult->Release();
result->Release();
delete cvRouter, cvRouter = NULL;
```

### Build and Run the Project

- For Windows

1. In Visual Studio, set the solution to build as Release\|x64.

2. Build the project to generate program `DBRCPPSample.exe`.

3. Copy **ALL** `*.dll` files under `[INSTALLATION FOLDER]/DynamsoftBarcodeReader/Dist/Lib/Windows/x64` to the same folder as the `DBRCPPSample.exe` ("[PROJECT FOLDER]\DBRCPPSample\x64\Release").
   
4. Copy folder `[INSTALLATION FOLDER]/DynamsoftBarcodeReader/Dist/Templates` to the same folder as the `DBRCPPSample.exe`.

5. Run the program `DBRCPPSample.exe`.

> The SDK supports both x86 and x64, please set the platform based on your needs.

- For Linux

   Open a terminal and change to the target directory where `DBRCPPSample.cpp` is located. Build the sample:

    ```bash
    g++ -o DBRCPPSample DBRCPPSample.cpp -lDynamsoftCaptureVisionRouter -lDynamsoftLicense -lDynamsoftCore -lDynamsoftUtility -L ../Dist/Lib/Linux/x64 -Wl,-rpath=../Dist/Lib/Linux/x64 -std=c++11
    ```

   Copy the preset template.

    ```bash
    cp -r ../Dist/Templates ../Dist/Lib/Linux/x64/
    ```

   Run the program `DBRCPPSample`.

    ```bash
    ./DBRCPPSample
    ```

## Process Multiple Images

If, instead of processing one single image, you need to process many images at once, you can follow these steps:

> These steps follow the step [Initialize a Capture Vision Router Instance](#initialize-a-capture-vision-router-instance) mentioned above.

> You can <a href="https://github.com/Dynamsoft/barcode-reader-c-cpp-samples/tree/main/Samples/HelloWorld/ReadMultipleImages" target="_blank">download the entire source code from here</a>.

### Add an Image Source as the Input

The class `CDirectoryFetcher` is capable of converting a local directory to an image source. We will use it to connect multiple images to the image-processing engine.

Include additional `DynamsoftUtility` and `DynamsoftCore` module.

```cpp
// Add the following lines
using namespace dynamsoft::utility;
#ifdef _WIN64
#pragma comment(lib, "[INSTALLATION FOLDER]/DynamsoftBarcodeReader/Dist/Lib/Windows/x64/DynamsoftCorex64.lib")
#pragma comment(lib, "[INSTALLATION FOLDER]/DynamsoftBarcodeReader/Dist/Lib/Windows/x64/DynamsoftUtilityx64.lib")
#else
#pragma comment(lib, "[INSTALLATION FOLDER]/DynamsoftBarcodeReader/Dist/Lib/Windows/x86/DynamsoftCorex86.lib")
#pragma comment(lib, "[INSTALLATION FOLDER]/DynamsoftBarcodeReader/Dist/Lib/Windows/x86/DynamsoftUtilityx86.lib")
#endif
```

Set up a `CDirectoryFetcher` object to retrieve image data sources from a directory.

```cpp
CDirectoryFetcher *fetcher = new CDirectoryFetcher;
fetcher->SetDirectory("[THE DIRECTORY THAT HOLDS THE IMAGES]");
cvRouter->SetInput(fetcher);
```

### Add a Result Receiver as the Output

Create a class `MyCapturedResultReceiver` to implement the `CCapturedResultReceiver` interface, and get the barocde results in `OnDecodedBarcodesReceived` callback function

```cpp
class MyCapturedResultReceiver : public CCapturedResultReceiver {
    void OnDecodedBarcodesReceived(CDecodedBarcodesResult* pResult) {
        const CFileImageTag *tag = dynamic_cast<const CFileImageTag*>(pResult->GetOriginalImageTag());
        cout << "File: " << tag->GetFilePath() << endl;
        if (pResult->GetErrorCode() != EC_OK)
        {
            cout << "Error: " << pResult->GetErrorString() << endl;
        }
        else
        {
            int count = pResult->GetItemsCount();
            cout << "Decoded " << count << " barcodes" << endl;
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
        cout << endl;
    }
};
```

Create and register a `MyCapturedResultReceiver` object as the result receiver.

```cpp
CCapturedResultReceiver *capturedReceiver = new MyCapturedResultReceiver;
cvRouter->AddResultReceiver(capturedReceiver);
```

### Add an Object to Listen to the Status of the Image Source

Create a class `MyImageSourceStateListener` to implement the `CImageSourceStateListenter` interface, and call StopCapturing in `OnImageSourceStateReceived` callback function when the state is `ISS_EXHAUSTED`.

```cpp
class MyImageSourceStateListener : public CImageSourceStateListener {
private:
    CCaptureVisionRouter* m_router;
public:
    MyImageSourceStateListener(CCaptureVisionRouter* router) {
        m_router = router;
    }
    virtual void OnImageSourceStateReceived(ImageSourceState state)
    {
        if (state == ISS_EXHAUSTED)
            m_router->StopCapturing();
    }
};
```

Create and register a `MyImageSourceStateListener` object as the listener.

```cpp
CImageSourceStateListener *listener = new MyImageSourceStateListener(cvRouter);
cvRouter->AddImageSourceStateListener(listener);
```

### Start the Process

Call the method `StartCapturing()` to start processing all the images in the specified folder.

```cpp
int errorCode = cvRouter->StartCapturing(CPresetTemplate::PT_READ_BARCODES, true, errorMsg, 512);        
```

During the process, the callback function `OnDecodedBarcodesReceived()` is triggered each time an image finishes processing. After all images are processed, the listener function `OnImageSourceStateReceived()` will return the image source state as `ISS_EXHAUSTED` and the process is stopped with the method `StopCapturing()`.

### Release the Allocated Memory

```cpp
delete cvRouter, cvRouter = NULL;
delete fetcher, fetcher = NULL;
delete listener, listener = NULL;
delete capturedReceiver, capturedReceiver = NULL;
```

### Build and Run the Project Again

Please refer to [Build and Run the Project](#build-and-run-the-project).

