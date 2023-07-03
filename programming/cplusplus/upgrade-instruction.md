---
title: Upgrade Instructions - Dynamsoft Barcode Reader C++ Edition
keywords: c++, cplusplus, upgrade
description: This page introduces how to upgrade Dynamsoft Barcode Reader
needAutoGenerateSidebar: false
permalink: /programming/cplusplus/upgrade-instruction.html
---

# How to Upgrade

## From 9.x to 10.x

`DynamsoftBarcodeReader` SDK has been refactored to integrate with `DynamsoftCaptureVision (DCV)` architecture. To upgrade from version 9.x to 10.x, we recommend you to follow the [User Guide](user-guide.md) and re-write your codes.

Notice the following break changes when upgrading your SDK.

### Update the Included Headers, libs & DLLs

Since the SDK architecture is changed, you have to change you code for including the headers, libs and DLLs. You can use the following code to replace your previous code.

```cpp
#include "[INSTALLATION FOLDER]/Include/DynamsoftCaptureVisionRouter.h"

using namespace std;
using namespace dynamsoft::license;
using namespace dynamsoft::cvr;
using namespace dynamsoft::dbr;
using namespace dynamsoft::utility;

#if defined(_WIN64) || defined(_WIN32)
    #ifdef _WIN64
        #pragma comment(lib, "[INSTALLATION FOLDER]/Lib/Windows/x64/DynamsoftCorex64.lib")
        #pragma comment(lib, "[INSTALLATION FOLDER]/Lib/Windows/x64/DynamsoftLicensex64.lib")
        #pragma comment(lib, "[INSTALLATION FOLDER]/Lib/Windows/x64/DynamsoftCaptureVisionRouterx64.lib")
        #pragma comment(lib, "[INSTALLATION FOLDER]/Lib/Windows/x64/DynamsoftUtilityx64.lib")
    #else
        #pragma comment(lib, "[INSTALLATION FOLDER]/Lib/Windows/x86/DynamsoftCorex86.lib")
        #pragma comment(lib, "[INSTALLATION FOLDER]/Lib/Windows/x86/DynamsoftLicensex86.lib")
        #pragma comment(lib, "[INSTALLATION FOLDER]/Lib/Windows/x86/DynamsoftCaptureVisionRouterx86.lib")
        #pragma comment(lib, "[INSTALLATION FOLDER]/Lib/Windows/x86/DynamsoftUtilityx86.lib")
    #endif
#endif
```

Put the following **.dll** files in your lib:

x64:

* DynamsoftBarcodeReaderx64.dll
* DynamsoftCaptureVisionRouterx64.dll
* DynamsoftCorex64.dll
* DynamsoftImageProcessingx64.dll
* DynamsoftLicensex64.dll
* DynamsoftUtilityx64.dll

x86:

* DynamsoftBarcodeReaderx86.dll
* DynamsoftCaptureVisionRouterx86.dll
* DynamsoftCorex86.dll
* DynamsoftImageProcessingx86.dll
* DynamsoftLicensex86.dll
* DynamsoftUtilityx86.dll

### Migrate from Class CBarcodeReader to Class CCaptureVisionRouter

Class `CCaptureVisionRouter` is added to replace class `CBarcodeReader`. Class `CCaptureVisionRouter` APIs includes the following features:

* Retrieve images
* Update templates and configure settings
* Implement barcode decoding
* Dispatch the results

### Templates

The template system is upgraded. The template you used for the previous version can't be directly recognized by the new version. Please go to [this page]() to upgrade your template.

### Replace PublicRuntimeSettings APIs with SimplifiedSettings APIs

The setting configuration APIs are refactored. Struct `PublicRuntimeSettings` is removed. Though a series of settings are still available via struct `SimplifiedCaptureVisionSettings`, the majority of settings are "template only". Please view the API reference of struct [`SimplifiedCaptureVisionSettings`]({{ site.dcv_cpp_api }}capture-vision-router/structs/simplified-capture-vision-settings.html) and [`SimplifiedBarcodeReaderSettings`]({{ site.cpp_api }}simplified-barcode-reader-settings.html) to see whether your settings are still available. If they are no longer supported by SimplifiedSettings, please <a href="https://www.dynamsoft.com/company/customer-service/#contact" target="_blank">contact us</a>. We will help you on generating a new template that supports your previous settings.

### Update Your Image Decoding Codes

#### Single Image Decoding

Since class `CBarcodeReader` is replaced with class `CCaptureVisionRouter`. You have to use the following `Capture` APIs instead of the `Decode` APIs:

```cpp
// Capture from a file.
CCapturedResult* Capture(const char* filePath, const char* templateName="");
// Capture from a file in memory.
CCapturedResult* Capture(const unsigned char *fileBytes, int fileSize, const char* templateName="");
// Capture from a CImageData object.
CCapturedResult* Capture(const CImageData* pImageData, const char* templateName="");
```

**The Corresponding Capture APIs of the Decode APIs**

| Removed APIs | New APIs |
| :----------- | :------- |
| `DecodeFile` | `Capture(const char* filePath, const char* templateName="")` |
| `DecodeFileInMemory` | `Capture(const unsigned char *fileBytes, int fileSize, const char* templateName="")` |
| `DecodeBuffer` | `Capture(const CImageData* pImageData, const char* templateName="")` |
| `DecodeBase64String` | **Currently not available**. |
| `DecodeDIB` | **Currently not available**. |

#### Batch Image Decoding

DCV architecture allows you to set a folder as an image source to fetch image from. To use this feature, you have to set `CDirectoryFetcher` as the input via class `CCaptureVisionRouter`.

```cpp
int main()
{
   CCaptureVisionRouter *cvr = new CCaptureVisionRouter;
   // Create a CDirectoryFetcher instance and set is as the input of cvr
   CDirectoryFetcher *fetcher = new CDirectoryFetcher;
   // Replace the following directory path with your directory path:
   fetcher->SetDirectory("C:\\my-directory-folder\\");
   cvr->SetInput(fetcher);
   // Create a CCapturedResultReceiver instance 
   CCapturedResultReceiver *capturedReceiver = new MyCapturedResultReceiver;
   cvr->AddResultReceiver(capturedReceiver);
   // Start capturing
   errorCode = cvr->StartCapturing(CPresetTemplate::PT_READ_BARCODES, true, errorMsg, 512);
}
```

### Update Your Video Streaming Decoding Codes

`CImageSourceAdapter` is added to replace the `FrameDecodeingParameters` and the previous video methods. The following steps shows how to implement video streaming barcode decoding with `CImageSourceAdapter`:

```cpp
class MyImageSource : public CImageSourceAdapter 
{
  // Add code to implement CImageSourceAdapter
};
int main()
{
  MyImageSource *source = new MyImageSource;
  cvr->SetInput(source);
}
```

### Result Obtaining

If you are using batch image decoding or video streaming decoding, you have to register a `CCapturedResultReceiver` to receive the barcode decoding results.

If you are using `Capture` APIs to process a single image, the barcode decoding results are still available from the return value of the `Capture` APIs.
