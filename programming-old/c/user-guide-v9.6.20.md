---
layout: default-layout
title: User Guide - Dynamsoft Barcode Reader SDK C Edition
description: This is the user guide of Dynamsoft Barcode Reader SDK C Edition.
keywords: user guide, c
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
permalink: /programming/c/user-guide.html
---

# Getting Started with C Language

In this guide, you will learn step by step on how to build a barcode reading application with Dynamsoft Barcode Reader SDK using C language.

## Requirements

- Operating System:
  - Windows 7, 8, 10, 11, 2003, 2008, 2008 R2, 2012, 2016, 2019, 2022
  - Linux x64: Ubuntu 14.04.4+ LTS, Debian 8+, etc
  - Linux arm 32bit
  - Linux arm 64bit
  - MacOS 64bit: 10.12+ (not included in the trial package, contact us to get the SDK)

- Developing Tool
  - Visual Studio 2008 or above
  - GCC 5.4+  

>Note:
>Dynamsoft Barcode Reader provides both online and offline license options. The online license option might not work in an environment that doesn't have network connection. In such case, you can get an offline trial license key via <a href="https://www.dynamsoft.com/customer/license/trialLicense?utm_source=guide&product=dbr&package=desktop" target="_blank">Customer Portal</a> or by <a href="https://www.dynamsoft.com/company/contact/" target="_blank">contacting us</a>.

## Installation

If you haven't downloaded the SDK yet, download the `C/C++ Package` now from <a href="https://www.dynamsoft.com/barcode-reader/downloads/?utm_source=docs" target="_blank">Dynamsoft website</a> and unpack the package into the directory of your choice.
>For this tutorial, we unpack it to `[INSTALLATION FOLDER]`, change it to your unpacking path for the following content.

## Build Your First Application

Let's start by creating a console application which demonstrates how to use the minimum code to read barcodes from an image file.  
> You can <a href="https://github.com/Dynamsoft/barcode-reader-c-cpp-samples/tree/v9.6.10/samples/C/GeneralSettings/GeneralSettings.c" target="_blank">download the entire source code here</a>.

### Create a New Project

#### For Windows

1. Open Visual Studio. Go to File > New > Project, create a new Empty Project and set Project name as `DBRCSample`.

2. Add a new source file named `DBRCSample.c` into the project.

#### For Linux/ARM/Mac

1. Create a new source file named `DBRCSample.c` and place it into the folder `[INSTALLATION FOLDER]/Samples`.

### Include the Library

1. Add headers and libs in `DBRCSample.c`.

    ```c
    #include <stdio.h>
    #include "[INSTALLATION FOLDER]/Include/DynamsoftBarcodeReader.h"
    #if defined(_WIN64) || defined(_WIN32)
        #ifdef _WIN64
            #pragma comment(lib, "[INSTALLATION FOLDER]/Lib/Windows/x64/DBRx64.lib")
        #else
            #pragma comment(lib, "[INSTALLATION FOLDER]/Lib/Windows/x86/DBRx86.lib")
        #endif
    #endif
    ```

### Initialize a Barcode Reader Instance

1. Initialize the license key.

    ```c
    int errorCode = 0;
    char szErrorMsg[512];
    errorCode = DBR_InitLicense("<insert DBR license key here>", szErrorMsg, 512);
    if (errorCode != DBR_OK)
    {
        // Add your code for license error processing;
        printf("%s\n", szErrorMsg);
    }
    ```

    >Please replace `<insert DBR license key here>` with a valid DBR licensekey. There are two ways to obtain one:
    >- Search `DBR_InitLicense` and find the license from `[INSTALLATION FOLDER]/Samples/BarcodeReaderDemo/BarcodeReaderDemo.cpp`.
    >- Request a trial license from <a href="https://www.dynamsoft.com/customer/license/trialLicense?utm_source=guide&product=dbr&package=desktop" target="_blank">Customer Portal</a>.

2. Create an instance of Dynamsoft Barcode Reader.

    ```c
    void* dbr = DBR_CreateInstance();
    ```

    *However, please note that if you are using a **concurrent instance license**, please use the new APIs [`DBR_GetInstance`](api-reference/methods/initialize-and-destroy.md#dbr_getinstance) to initialize the barcode reader instance and then [`DBR_RecycleInstance`](api-reference/methods/initialize-and-destroy.md#dbr_recycleinstance) to allow for better concurrent instance management by the library.*

    ```c
    void* dbr = DBR_GetInstance();
    // If no instance is available right away, the application will wait until one becomes available
    if(dbr != NULL)
    {
        // Add your code here to call decoding method, process barcode results and so on
        // ...
        // Recycle the instance to make it idle for other concurrent tasks
        DBR_RecycleInstance(dbr);
    }
    ```

### Configure the Barcode Scanning Behavior

1. Set barcode format and count to read.

    ```c
    char szErrorMsg[512];
    PublicRuntimeSettings settings;
    DBR_GetRuntimeSettings(dbr, &settings);
    settings.barcodeFormatIds = BF_PDF417; 
    settings.barcodeFormatIds_2 = BF2_DOTCODE; 
    settings.expectedBarcodesCount = 2;
    DBR_UpdateRuntimeSettings(dbr, &settings, szErrorMsg, 512);
    ```

    >The barcode formats to enable is highly application-specific. We recommend that you only enable the barcode formats your application requires. Check out [Barcode Format Enumeration]({{ site.c_cpp_enumerations }}format-enums.html) for full supported barcode formats.

    >If you know exactly the barcode count you want to read, specify `expectedBarcodesCount` to speed up the process and improve the accuracy.

    >The Barcode Reader SDK comes with a large array of runtime settings to optimize the performance of the library. To learn about all the runtime settings, please visit the [RuntimeSettings]({{ site.structs }}PublicRuntimeSettings.html?src=c) API page. To learn more about the cases and situations in which the settings can help, please visit the [Explore Features](user-guide/explore-features/index.md) page.

### Decode and Output Results

1. Decode barcodes from an image file.

    ```c
    int errorCode = -1;
    errorCode = DBR_DecodeFile(dbr, "[INSTALLATION FOLDER]/Images/AllSupportedBarcodeTypes.png", "");
    if(errorCode != DBR_OK)
        printf("%s\n", DBR_GetErrorString(errorCode));
    ```

    >For the error handling mechanism, the SDK returns Error Code for each function and provides a function `DBR_GetErrorString` to get the readable message. You should add codes for error handling based on your needs. Check out [Error Code]({{site.c_cpp_enumerations}}error-code.html) for full supported error codes.

2. Get and output barcode results.

    ```c
    TextResultArray* barcodeResults = NULL;
    DBR_GetAllTextResults(dbr, &barcodeResults);
    if (barcodeResults != NULL && barcodeResults->resultsCount > 0)
    {
        printf("%d total barcode(s) found. \n", barcodeResults->resultsCount);
        for (int index = 0; index < barcodeResults->resultsCount; index++)
        {
            printf("Result %d\n", index + 1);
            printf("    Barcode Format: %s\n", barcodeResults->results[index] ->barcodeFormatString);
            printf("    Barcode Text: %s \n", barcodeResults->results[index] ->barcodeText);
        }
    }
    ```

    >The SDK returns multiple barcode information, including barcode count, barcode format, barcode text, location, barcode raw data, etc. Check out [TextResult]({{ site.structs }}TextResult.html?src=c) for full supported result data.

### Release Allocated Memory

1. Release the allocated memory for the barcode results and instance.

    ```c
    if(barcodeResults != NULL)           
        DBR_FreeTextResults(&barcodeResults);
    ```

1. Release the allocated memory for the instance.

    ```c
    if(dbr != NULL)           
        DBR_DestroyInstance(dbr);
    ```

    *However, please note that if you are using a **concurrent instance license**, please use the new APIs [`DBR_RecycleInstance`](api-reference/methods/initialize-and-destroy.md#dbr_recycleinstance) to allow for better concurrent instance management by the library.*

    ```c
    if(dbr != NULL)           
        DBR_RecycleInstance(dbr);
    ```

>Note:  
Please change all `[INSTALLATION FOLDER]` in above code snippet to your unpacking path.

### Build and Run the Project

#### For Windows

1. In Visual Studio, set the solution to build as Release\|x64.

2. Build the project to generate program `DBRCSample.exe`.

3. Copy **ALL** `*.dll` files under `[INSTALLATION FOLDER]\Lib\Windows\x64` to the same folder as the `DBRCSample.exe`.

4. Run the program `DBRCSample.exe`.

>The SDK supports both x86 and x64, please set the platform based on your needs.

#### For Linux/ARM/Mac

1. Open a terminal and change to the target directory where `DBRCSample.c` located in. Build the sample:

    ```bash
    gcc -o DBRCSample DBRCSample.c -lDynamsoftBarcodeReader -L ../Lib/Linux -Wl,-rpath=../Lib/Linux
    ```

    > Please replace `Linux` to `ARM32` or `ARM64` based on your platform.

2. Run the program `DBRCSample`.

    ```bash
    ./DBRCSample
    ```

> You can <a href="https://github.com/Dynamsoft/barcode-reader-c-cpp-samples/tree/v9.6.10/samples/C/GeneralSettings/GeneralSettings.c" target="_blank">download the entire source code here</a>.

## Next Steps

- Learn [How to Upgrade to Latest Version](upgrade-instruction.md)
- [Explore SDK Features](user-guide/explore-features/index.md)
- See how the SDK works in [Popular Use Cases](user-guide/use-cases/index.md)
- Check out the [Official Samples and Demo](samples/index.md)
