---
layout: default-layout
title: User Guide - Dynamsoft Barcode Reader SDK Java Edition
description: This is the user guide of Dynamsoft Barcode Reader SDK Java Edition.
keywords: user guide, java
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
permalink: /programming/java/user-guide-v9.6.20.html
---


# Getting Started with Java

In this guide, you will learn step by step on how to build a barcode reading application with Dynamsoft Barcode Reader SDK using Java.

## Requirements

- Operating systems:
  - Windows 7, 8, 10, 11
  - Windows Server 2003, 2008, 2008 R2, 2012, 2019, 2022
  - Linux x64 (Ubuntu 14.04.4+ LTS, Debian 8+, etc.)
  - Linux arm 64bit
  - macOS x64: 10.12+
  - macOS ARM: 11+

- Developing Environment:
  - JDK 1.7 and above

>Note:
>Dynamsoft Barcode Reader provides both online and offline license options. The online license option might not work in an environment that doesn't have network connection. In such case, you can get an offline trial license key via <a href="https://www.dynamsoft.com/customer/license/trialLicense?utm_source=guide&product=dbr&package=desktop" target="_blank">Customer Portal</a> or by <a href="https://www.dynamsoft.com/company/contact/" target="_blank">contacting us</a>.

<iframe width="400" height="225" src="https://www.youtube.com/embed/05UtoF7_HJQ" title="How to Use Dynamsoft Barcode Reader Java SDK | Dynamsoft Tutorial" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Installation

If you haven't downloaded the SDK yet, download the `Java Package` now from <a href="https://www.dynamsoft.com/barcode-reader/downloads/?utm_source=docs" target="_blank">Dynamsoft website</a> and unpack the package into the directory of your choice.
>For this tutorial, we unpack it to `[INSTALLATION FOLDER]`, change it to your unpacking path for the following content.

## Build Your First Application

Let's start by creating a console application which demonstrates how to use the minimum code to read barcodes from an image file.  
> You can <a href="https://github.com/Dynamsoft/barcode-reader-java-samples/blob/main/samples/GeneralSettings/src/main/java/GeneralSettings.java" target="_blank">download the entire source code here</a>.

### Create a New Project

1. Open Eclipse. Go to File > New > Project,  create a new Java project `DBRJavaSample`.

2. Add a new Class named `DBRJavaSample` into the project.

### Add the Library Reference

1. Right click on Project -> Properties > Java Build Path > Libraries > Add external JARs, Browse to `[INSTALLATION FOLDER]\lib` and Select `dynamsoft-barcodereader-{version number}.jar`.

2. Import the package in the file `DBRJavaSample.java`

   ```java
   import com.dynamsoft.dbr.*;
   ```

### Initialize a Barcode Reader Instance

1. Initialize the license key.

    ```java
    BarcodeReader.initLicense("<insert DBR license key here>");
    ```

    >Please replace `<insert DBR license key here>` with a valid DBR licensekey. There are two ways to obtain one:
    >- Search `initLicense` and find the license from `[INSTALLATION FOLDER]/samples/BarcodeReaderDemo/src/com/dynamsoft/demo/BarcodeReaderDemo.java`.
    >- Request a trial license from <a href="https://www.dynamsoft.com/customer/license/trialLicense?utm_source=guide&product=dbr&package=desktop" target="_blank">Customer Portal</a>.

2. Create an instance of Dynamsoft Barcode Reader.

    ```java
    BarcodeReader reader = new BarcodeReader()
    ```

    *However, please note that if you are using a **concurrent instance license**, please use the new APIs [`getInstance`](api-reference/BarcodeReader/initialize-and-destroy.md#getinstance) to initialize the barcode reader instance and then [`recycle`](api-reference/BarcodeReader/initialize-and-destroy.md#recycle) to allow for better concurrent instance management by the library.*

    ```java
    BarcodeReader reader = BarcodeReader.getInstance();
    // If no instance is available right away, the application will wait until one becomes available
    if(reader != null)
    {
        // Add your code here to call decoding method, process barcode results and so on
        // ...
        // Recycle the instance to make it idle for other concurrent tasks
        reader.recycle();
    }
    ```

### Configure the Barcode Scanning Behavior (OPTIONAL)

1. Set barcode format and count to read.

    ```java
    PublicRuntimeSettings runtimeSettings = reader.getRuntimeSettings();
    runtimeSettings.barcodeFormatIds = EnumBarcodeFormat.BF_ONED | EnumBarcodeFormat.BF_QR_CODE;
    runtimeSettings.barcodeFormatIds_2 = EnumBarcodeFormat_2.BF2_POSTALCODE | EnumBarcodeFormat_2.BF2_DOTCODE;
    runtimeSettings.expectedBarcodesCount = 10;
    reader.updateRuntimeSettings(runtimeSettings);
    ```

    >The barcode formats to enable is highly application-specific. We recommend that you only enable the barcode formats your application requires. Check out [Barcode Format Enumeration]({{ site.java_enumerations }}format-enums.html) for full supported barcode formats.

    >If you know exactly the barcode count you want to read, specify `expectedBarcodesCount` to speed up the process and improve the accuracy.

    >The Barcode Reader SDK comes with a large array of runtime settings to optimize the performance of the library. To learn about all the runtime settings, please visit the [RuntimeSettings](api-reference/class/PublicRuntimeSettings.md) API page. To learn more about the cases and situations in which the settings can help, please visit the [Explore Features](user-guide/explore-features/index.md) page.

### Decode and Output Results

1. Decode barcodes from an image file.
2. Get and output barcode results.

    ```java
   try
   {
       TextResult[] results = reader.decodeFile("[INSTALLATION FOLDER]/images/AllSupportedBarcodeTypes.png", "");
       if (results != null && results.length > 0) {
            System.out.println("Total barcodes found: " + results.length);
            for (int iIndex = 0; iIndex < results.length; iIndex++)
            {
                System.out.println("Barcode " + (iIndex + 1));
                System.out.println("    Barcode Format: " + results[iIndex].barcodeFormatString);
                System.out.println("    Barcode Text: " + results[iIndex].barcodeText);
            }
       }     
   }
   catch (BarcodeReaderException exp)
   {
       System.out.println(exp.getMessage());
   }
    ```

    >For the error handling mechanism, the SDK throws [BarcodeReaderException]({{site.java_class}}BarcodeReaderException.html) for each function. You should add codes for exception handling based on your needs.

    >The SDK returns multiple barcode information, including barcode count, barcode format, barcode text, location, barcode raw data, etc. Check out [TextResult]({{ site.java_class }}TextResult.html) for full supported result data.

### Release Resource

1. Destroy the instance to release all resources.

    ```java
    reader.destroy();
    ```

    *However, please note that if you are using a **concurrent instance license**, please use the new APIs [`recycle`](api-reference/BarcodeReader/initialize-and-destroy.md#recycle) to allow for better concurrent instance management by the library.*

    ```java
    if(reader != null)
    {
        reader.recycle();
    }
    ```

>Note:  
Please change all `[INSTALLATION FOLDER]` in above code snippet to your unpacking path.

### Build and Run the Project

1. Right click the project, click Run As > Java Application.

> You can <a href="https://github.com/Dynamsoft/barcode-reader-java-samples/blob/main/samples/GeneralSettings/src/main/java/GeneralSettings.java" target="_blank">download the entire source code here</a>.

## Next Steps

- Learn [How to Upgrade to Latest Version](upgrade-instruction.md)
- [Explore SDK Features](user-guide/explore-features/index.md)
- See how the SDK works in [Popular Use Cases](user-guide/use-cases/index.md)
- Check out the [Official Samples and Demo](samples/index.md)
