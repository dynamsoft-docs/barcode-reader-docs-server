---
layout: default-layout
title: User Guide - Dynamsoft Barcode Reader SDK Java Edition
description: This is the user guide of Dynamsoft Barcode Reader SDK Java Edition.
keywords: user guide, java
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# Getting Started with Dynamsoft Barcode Reader SDK Java Edition

In this guide, you will learn step by step on how to build a barcode reading application with Dynamsoft Barcode Reader SDK using Java.

> Read more on [Dynamsoft Barcode Reader Features](https://www.dynamsoft.com/barcode-reader/features/)

- [Getting Started with Dynamsoft Barcode Reader SDK Java Edition](#getting-started-with-dynamsoft-barcode-reader-sdk-java-edition)
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

To find out whether your environment is supported, please read the [System Requirements]({{ site.dbr_java }}index.html#system-requirements).

## Installation

If you don't have a Maven project, you can create one with the following steps:

1. Create a new directory for your project
2. Navigate to the directory and run the following command to create a Maven project:

```
mvn archetype:generate -DgroupId=com.dynamsoft -DartifactId=dbr-hello-world -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false
```

3. Add the Dynamsoft Barcode Reader dependency to your `pom.xml` file:

```xml
<repositories>
    <repository>
        <id>dbr</id>
        <url>https://download2.dynamsoft.com/maven/dbr/jar</url>
    </repository>
</repositories>

<dependencies>
    <dependency>
        <groupId>com.dynamsoft</groupId>
        <artifactId>dbr</artifactId>
        <version>11.4.1000</version>
    </dependency>
</dependencies>
```

## Build Your First Application

Let's start by creating a console application which demonstrates how to use the minimum code to read barcodes from an image file.

> You can <a href="https://github.com/Dynamsoft/barcode-reader-java-samples/tree/main/Samples/HelloWorld" target="_blank">download the entire source code from here</a>.

### Create a New Project

Create a new Java source file named `ReadAnImage.java` in your project's `src/main/java` directory.

### Include the Library

Import the necessary packages at the beginning of your Java file:

```java
import com.dynamsoft.core.EnumErrorCode;
import com.dynamsoft.cvr.CaptureVisionRouter;
import com.dynamsoft.cvr.CapturedResult;
import com.dynamsoft.cvr.EnumPresetTemplate;
import com.dynamsoft.dbr.BarcodeResultItem;
import com.dynamsoft.dbr.DecodedBarcodesResult;
import com.dynamsoft.license.LicenseError;
import com.dynamsoft.license.LicenseException;
import com.dynamsoft.license.LicenseManager;
```

### Initialize the License Key

Add the following code inside the `main` method to initialize the license for using the SDK in the application:

```java
public class ReadAnImage {
    public static void main(String[] args) {
        try {
            LicenseError licenseError = LicenseManager.initLicense("DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9");
            if (licenseError.getErrorCode() != EnumErrorCode.EC_OK) {
                System.out.println("License initialization failed: ErrorCode: " + licenseError.getErrorCode() + ", ErrorString: " + licenseError.getErrorString());
                return;
            }
        } catch (LicenseException e) {
            System.out.println("License initialization failed: ErrorCode: " + e.getErrorCode() + ", ErrorString: " + e.getErrorString());
            return;
        }
        // codes from following steps
    }
}
```

> The string "DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9" here is a free public trial license. Note that network connection is required for this license to work. Alternatively, you can request a 30-day free offline trial license from the <a href="https://www.dynamsoft.com/customer/license/trialLicense?utm_source=guide&product=dbr&package=java" target="_blank">Customer Portal</a>.

### Create a CaptureVisionRouter Instance

```java
CaptureVisionRouter cvRouter = new CaptureVisionRouter();
```

### Invoke the Barcode Capturing

```java
CapturedResult[] results = cvRouter.captureMultiPages("[PATH-TO-THE-IMAGE-FILE]", EnumPresetTemplate.PT_READ_BARCODES);
```

> Please change the `[PATH-TO-THE-IMAGE-FILE]` to a real barcode image file path.

### Filter and Get Barcode Details

```java
if (results == null || results.length == 0) {
    System.out.println("No barcode detected.");
} else {
    for (int index = 0; index < results.length; index++) {
        CapturedResult result = results[index];
        if (result.getErrorCode() != EnumErrorCode.EC_OK) {
            System.out.println("Error: " + result.getErrorCode() + ", " + result.getErrorString());
        }

        DecodedBarcodesResult barcodeResult = result.getDecodedBarcodesResult();
        BarcodeResultItem[] items = barcodeResult != null ? barcodeResult.getItems() : null;
        if (items == null || items.length == 0) {
            System.out.println("No barcode detected.");
        } else {
            System.out.println("Decoded " + items.length + " barcodes.");
            for (int i = 0; i < items.length; i++) {
                BarcodeResultItem item = items[i];
                System.out.println("Result " + (i + 1));
                System.out.println("Barcode Format: " + item.getFormatString());
                System.out.println("Barcode Text: " + item.getText());
            }
        }
    }
}
```

### Build and Run the Project

1. Save the `ReadAnImage.java` file.
2. Open terminal or command prompt and navigate to the project root directory.
3. Compile and run the project using Maven:

```
mvn compile exec:java -Dexec.mainClass="ReadAnImage"
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

> You can <a href="https://github.com/Dynamsoft/barcode-reader-java-samples/tree/main/Samples/HelloWorld" target="_blank">download the entire source code from here</a>.


### Create an ImageSource as the Input

An `ImageSource` is required when creating a multi-image processing application. You can either utilize ready-made image sources such as [`FileFetcher`]({{ site.dcvb_java_api }}utility/file-fetcher.html) and [`DirectoryFetcher`]({{ site.dcvb_java_api }}utility/directory-fetcher.html), or customize your own image source based on the base class [`ImageSourceAdapter`]({{ site.dcvb_java_api }}core/basic-classes/image-source-adapter.html).

First, you need to import the additional required classes:

```java
import com.dynamsoft.core.basic_structures.FileImageTag;
import com.dynamsoft.core.basic_structures.ImageTag;
import com.dynamsoft.cvr.*;
import com.dynamsoft.utility.DirectoryFetcher;
import com.dynamsoft.utility.UtilityException;
```

In this sample, we will use the `DirectoryFetcher` to retrieve images from a local directory.

```java
DirectoryFetcher fetcher = new DirectoryFetcher();
fetcher.setDirectory("[THE DIRECTORY THAT HOLDS THE IMAGES]");
```

> Please change the `[THE DIRECTORY THAT HOLDS THE IMAGES]` to full path of the directory holding barcode image files.

### Implement a CapturedResultReceiver as the Output Listener

Create a class `MyCapturedResultReceiver` to extend the `CapturedResultReceiver` class, and get the barcode results in `onDecodedBarcodesReceived` callback method.

```java
class MyCapturedResultReceiver extends CapturedResultReceiver {
    @Override
    public void onDecodedBarcodesReceived(DecodedBarcodesResult result) {
        ImageTag tag = result.getOriginalImageTag();
        if (tag instanceof FileImageTag) {
            System.out.println("File: " + ((FileImageTag)tag).getFilePath());
        }
        
        if (result.getErrorCode() != EnumErrorCode.EC_OK) {
            System.out.println("Error: " + result.getErrorString());
        } else {
            BarcodeResultItem[] items = result.getItems();
            System.out.println("Decoded " + items.length + " barcodes.");
            for (int index = 0; index < items.length; index++) {
                BarcodeResultItem item = items[index];
                System.out.println("Result " + (index + 1));
                System.out.println("Barcode Format: " + item.getFormatString());
                System.out.println("Barcode Text: " + item.getText());
            }
        }
    }
}
```

### Handle Capture Stoppage by Implementing an ImageSource State Listener

Create a class `MyImageSourceStateListener` to implement the `ImageSourceStateListener` interface, and call `stopCapturing` in `onImageSourceStateReceived` callback method when the state is `ISS_EXHAUSTED`.

```java
class MyImageSourceStateListener implements ImageSourceStateListener {
    CaptureVisionRouter cvRouter;

    public MyImageSourceStateListener(CaptureVisionRouter cvRouter) {
        this.cvRouter = cvRouter;
    }

    @Override
    public void onImageSourceStateReceived(int state) {
        if (state == EnumImageSourceState.ISS_EXHAUSTED) {
            if (cvRouter != null) {
                cvRouter.stopCapturing();
            }
        }
    }
}
```

### Register the Input, Output Listener and ImageSource State Listener to the CaptureVisionRouter Instance

```java
try {
    cvRouter.setInput(fetcher);
    MyCapturedResultReceiver receiver = new MyCapturedResultReceiver();
    cvRouter.addResultReceiver(receiver);
    MyImageSourceStateListener listener = new MyImageSourceStateListener(cvRouter);
    cvRouter.addImageSourceStateListener(listener);
} catch (CaptureVisionException e) {
    System.out.println("Error setting up capture vision router: " + e.getMessage());
}
```

### Start the Capturing Process

Call the method `startCapturing()` to start processing all the images in the specified folder.

```java
try {
    cvRouter.startCapturing("", true);
} catch (CaptureVisionException e) {
    if (e.getErrorCode() != EnumErrorCode.EC_OK) {
        System.out.println("Error: " + e.getErrorCode());
    }
}
```

During the process, the callback method `onDecodedBarcodesReceived()` is triggered each time processing of an image is finished. After all images are processed, the listener method `onImageSourceStateReceived()` will be triggered while the image source state is `ISS_EXHAUSTED` and the process is stopped with the method `stopCapturing()`.

### Build and Run the Project Again

Please refer to [Build and Run the Project](#build-and-run-the-project).