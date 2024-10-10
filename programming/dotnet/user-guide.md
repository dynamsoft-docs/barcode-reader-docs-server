---
layout: default-layout
title: User Guide - Dynamsoft Barcode Reader SDK .NET Edition
description: This is the user guide of Dynamsoft Barcode Reader SDK .NET Edition.
keywords: user guide, .NET
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# Getting Started with Dynamsoft Barcode Reader SDK .NET Edition

In this guide, you will learn step by step on how to build a barcode reading application with Dynamsoft Barcode Reader SDK using C#.

> Read more on [Dynamsoft Barcode Reader Features](https://www.dynamsoft.com/barcode-reader/features/)

- [Getting Started with Dynamsoft Barcode Reader SDK .NET Edition](#getting-started-with-dynamsoft-barcode-reader-sdk-net-edition)
  - [System Requirements](#system-requirements)
  - [Build Your First Application](#build-your-first-application)
    - [Create a New Project](#create-a-new-project)
    - [Install the NuGet Package](#install-the-nuget-package)
    - [Import the Namespace](#import-the-namespace)
    - [Initialize the License Key](#initialize-the-license-key)
    - [Create a CaptureVisionRouter Instance](#create-a-capturevisionrouter-instance)
    - [Invoke the Barcode Capturing](#invoke-the-barcode-capturing)
    - [Filter and Get Barcode Details](#filter-and-get-barcode-details)
    - [Build and Run the Project](#build-and-run-the-project)
  - [Process Multiple Images](#process-multiple-images)
    - [Import the Additional Namespace.](#import-the-additional-namespace)
    - [Create an ImageSource as the Input](#create-an-imagesource-as-the-input)
    - [Implement a CapturedResultReceiver as the Output Listener](#implement-a-capturedresultreceiver-as-the-output-listener)
    - [Handle Capture Stoppage by Implementing a ImageSource State Listener](#handle-capture-stoppage-by-implementing-a-imagesource-state-listener)
    - [Register the Input, Output Listener and ImageSource State Listener to the CaptureVisionRouter Instance](#register-the-input-output-listener-and-imagesource-state-listener-to-the-capturevisionrouter-instance)
    - [Start the Capturing Process](#start-the-capturing-process)
    - [Build and Run the Project Again](#build-and-run-the-project-again)

## System Requirements

To find out whether your environment is supported, please read the [System Requirements]({{ site.dbr_dotnet}}index.html#system-requirements).

## Build Your First Application

Let's start by creating a console application which demonstrates how to use the minimum code to read barcodes from an image file.

> You can <a href="https://github.com/Dynamsoft/barcode-reader-dotnet-samples/tree/main/Samples/HelloWorld/ReadAnImage" target="_blank">download the entire source code from here</a>.

### Create a New Project

Start Visual Studio or your preferred C# IDE.

Create a new C# Console Application project. Let's name it `DBRCSharpSample`.

### Install the NuGet Package

In the Solution Explorer, right-click on your project and select Manage NuGet Packages.

Search for and install the `Dynamsoft.DotNet.BarcodeReader.Bundle` nuget package.

> If you prefer to use the offline packages, please
> 
> <a href="https://www.dynamsoft.com/barcode-reader/downloads/?utm_source=docs" target="_blank">Download the `.NET Package`</a> now and extract it into a directory of your choice.
> 
> You can find the nuget package under `.\DynamsoftBarcodeReader\Packages`.



### Import the Namespace

Open the `Program.cs` file and add the following namespaces.

```csharp
using Dynamsoft.DBR;
using Dynamsoft.Core;
using Dynamsoft.CVR;
using Dynamsoft.License;
```

### Initialize the License Key

Open the `Program.cs` file and add the following code inside the `Main` method to initialize the license for using the SDK in the application:

```csharp
int errorCode = 1;
string errorMsg;
errorCode = LicenseManager.InitLicense("DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9", out errorMsg);
if (errorCode != (int)EnumErrorCode.EC_OK && errorCode != (int)EnumErrorCode.EC_LICENSE_CACHE_USED)
    Console.WriteLine("License initialization error: " + errorMsg);
```

> The string "DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9" here is a free public trial license. Note that network connection is required for this license to work. When it expires, you can request a 30-day free trial license from the <a href="https://www.dynamsoft.com/customer/license/trialLicense?utm_source=guide&product=dbr&package=dotnet" target="_blank">Customer Portal</a>.

### Create a CaptureVisionRouter Instance

```csharp
using (CaptureVisionRouter cvr = new CaptureVisionRouter())
{
    //code for invoking the barcode capturing
}
```

### Invoke the Barcode Capturing

```csharp
using (CaptureVisionRouter cvr = new CaptureVisionRouter())
{
    string imageFile = "[PATH-TO-THE-IMAGE-FILE]";
    CapturedResult? result = cvr.Capture(imageFile, PresetTemplate.PT_READ_BARCODES);
    //code for filtering and getting barcode details
}
```

> Please change the `[PATH-TO-THE-IMAGE-FILE]` to a real barcode image file path.

### Filter and Get Barcode Details

```csharp
if (result == null)
{
    Console.WriteLine("No barcode detected.");
}
else if(result.GetErrorCode() != 0)
{
    Console.WriteLine("Error: " + result.GetErrorCode() + ", " + result.GetErrorString());
}
else
{
    DecodedBarcodesResult barcodesResult = result.GetDecodedBarcodesResult();
    if (barcodesResult != null)
    {
        BarcodeResultItem[] items = barcodesResult.GetItems();
        Console.WriteLine("Decoded " + items.Length + " barcodes");
        foreach (BarcodeResultItem barcodeItem in items)
        {
            Console.WriteLine("Result " + (Array.IndexOf(items, barcodeItem) + 1));
            Console.WriteLine("Barcode Format: " + barcodeItem.GetFormatString());
            Console.WriteLine("Barcode Text: " + barcodeItem.GetText());
        }
    }
}
```

### Build and Run the Project

Save the `Program.cs` file and then compile and run the program using your IDE (such as Visual Studio). You will see the output message in the console like

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

> You can <a href="https://github.com/Dynamsoft/barcode-reader-dotnet-samples/tree/main/Samples/HelloWorld/ReadMultipleImages" target="_blank">download the entire source code from here</a>.

### Import the Additional Namespace.

```csharp
using Dynamsoft.Utility;
```

### Create an ImageSource as the Input

An `ImageSource` is required when creating a multi-image processing application. You can either utilize ready-made image sources such as [`FileFetcher`]({{ site.dcv_dotnet_api }}utility/file-fetcher.html) and [`DirectoryFetcher`]({{ site.dcv_dotnet_api }}utility/directory-fetcher.html), or customize your own image source based on the base class [`ImageSourceAdapter`]({{ site.dcv_dotnet_api }}core/basic-classes/image-source-adapter.html).

In this sample, we will use the `DirectoryFetcher` to retrieve images from a local directory.

```csharp
DirectoryFetcher fetcher = new DirectoryFetcher();
fetcher.SetDirectory("[THE DIRECTORY THAT HOLDS THE IMAGES]");
```

> Please change the `[THE DIRECTORY THAT HOLDS THE IMAGES]` to full path of the directory holding barcode image files.

### Implement a CapturedResultReceiver as the Output Listener

Create a class `MyCapturedResultReceiver` to implement the `CapturedResultReceiver` interface, and get the barocde results in `OnDecodedBarcodesReceived` callback function.

```csharp
class MyCapturedResultReceiver : CapturedResultReceiver
{
    public override void OnDecodedBarcodesReceived(DecodedBarcodesResult result)
    {
        FileImageTag? tag = (FileImageTag?)result.GetOriginalImageTag();
        Console.WriteLine("File: " + tag.GetFilePath());
        if (result.GetErrorCode() != (int)EnumErrorCode.EC_OK)
        {
            Console.WriteLine("Error: " + result.GetErrorString());
        }
        else
        {
            BarcodeResultItem[] items = result.GetItems();
            Console.WriteLine("Decoded " + items.Length + " barcodes");
            foreach (BarcodeResultItem item in items)
            {
                Console.WriteLine("Result " + (Array.IndexOf(items, item) + 1));
                Console.WriteLine("Barcode Format: " + item.GetFormatString());
                Console.WriteLine("Barcode Text: " + item.GetText());
            }
        }
        Console.WriteLine();
    }
}
```

### Handle Capture Stoppage by Implementing a ImageSource State Listener

Create a class `MyImageSourceStateListener` to implement the `IImageSourceStateListener` interface, and call StopCapturing in `OnImageSourceStateReceived` callback function when the state is `ISS_EXHAUSTED`.

```csharp
class MyImageSourceStateListener : IImageSourceStateListener
{
    private CaptureVisionRouter? cvr = null;
    public MyImageSourceStateListener(CaptureVisionRouter cvr)
    {
        this.cvr = cvr;
    }
    public void OnImageSourceStateReceived(EnumImageSourceState state)
    {
        if (state == EnumImageSourceState.ISS_EXHAUSTED)
        {
            if (cvr != null)
            {
                cvr.StopCapturing();
            }
        }
    }
}
```

### Register the Input, Output Listener and ImageSource State Listener to the CaptureVisionRouter Instance

```csharp
cvr.SetInput(fetcher);
CapturedResultReceiver receiver = new MyCapturedResultReceiver();
cvr.AddResultReceiver(receiver);
MyImageSourceStateListener listener = new MyImageSourceStateListener(cvr);
cvr.AddImageSourceStateListener(listener);
```

### Start the Capturing Process

Call the method `StartCapturing()` to start processing all the images in the specified folder.

```csharp
errorCode = cvr.StartCapturing(PresetTemplate.PT_READ_BARCODES, true, out errorMsg);
if (errorCode != (int)EnumErrorCode.EC_OK)
{
    Console.WriteLine("error: " + errorMsg);
}
```

During the process, the callback function `OnDecodedBarcodesReceived()` is triggered each time processing of an image is finished. After all images are processed, the listener function `OnImageSourceStateReceived()` will be triggered while the image source state is `ISS_EXHAUSTED` and the process is stopped with the method `StopCapturing()`.

### Build and Run the Project Again

Please refer to [Build and Run the Project](#build-and-run-the-project).

