---
layout: default-layout
title: Release Notes v10.x - Dynamsoft Barcode Reader SDK .NET Edition
description: This is the release notes page of Dynamsoft Barcode Reader SDK .NET Edition v10.x.
keywords: release notes, .NET
needGenerateH3Content: false
---

# Release Notes for .NET Edition - 10.x

## 10.4.2000 (10/10/2024)

### Highlights

- Added to-the-latest overlapping feature.
- Improved the error handling logic of `Capture`, `StartCapturing` and `InitLicense` methods to clearly report a licensing issue.

### Changelogs

#### New

- Added new functions `SetMaxOverlappingFrames`, `GetMaxOverlappingFrames`, `EnableLatestOverlapping` and `IsLatestOverlappingEnabled` to the class `CMultiFrameResultCrossFilter`.

- Added new error codes
  - `EC_LICENSE_WARNING`
  - `EC_BARCODE_READER_LICENSE_NOT_FOUND`

- Added new properties to the `QRCodeDetails` class
  - `codewords`
  - `dataMaskPattern`

#### Fixed

- Fixed a crash bug caused by the usage of RegEx.
- Fixed a bug that could prevent the reading of `GS1_DATABAR_EXPANDED_STACKED` barcodes.
- Small fixes and tweaks.

#### Changed

- Changed the template loading mode. By default, the library loads all template files from the `Templates` folder in the same directory as the library file.
- Changed the enumeration value of `EnumBarcodeFormat.BF_ALL` to 0xFFFFFFFEFFFFFFFF.
- Integrated the previously separate nuget packages directly into the `Dynamsoft.DotNet.BarcodeReader.Bundle` package. As a result, the following nuget packages have been announced as deprecated.
    - Dynamsoft.DotNet.BarcodeReader
    - Dynamsoft.DotNet.CaptureVisionRouter
    - Dynamsoft.DotNet.Core
    - Dynamsoft.DotNet.ImageProcessing
    - Dynamsoft.DotNet.License
    - Dynamsoft.DotNet.Utility


## 10.2.12 (06/19/2024)

- Fixed a bug that caused 32-bit applications to crash on startup under .NET Framework.

## 10.2.11 (06/12/2024)

- Fixed a bug where calling the method `GetSimplifiedSettings` would throw a `System.IO.FileNotFoundException` with the message "Could not load file or assembly ...".

## 10.2.10 (05/30/2024)

### Highlights

`DynamsoftBarcodeReader` SDK has been revamped to integrate with `DynamsoftCaptureVision (DCV)` architecture, which is newly established to aggregate the features of functional products powered by Dynamsoft. The features are designed to be pluggable, customizable and interactable. In addition, the functional products share the computation so that their processing speed is much higher than working individually.

* `DynamsoftCaptureVision` architecture consists of:
  * `ImageSourceAdapter(ISA)`, the standard input interface for you to convert image data from different sources into the standard input image data. In addition, `ISA` incorporates an image buffer management system that allows instant access to the buffered image data.
  * `CaptureVisionRouter (CVR)`, an engine for you to update templates, retrieve images from `ISA`, coordinate corresponding functional products and dispatch the results to the receivers.
  * Functional products that perform image processing, content understanding and semantic processing. The functional products are pluggable and passively called by CVR when they are required.
  * Result receiver interfaces. You can implement `CapturedResultReceiver (CRR)` to receive the `CapturedResults` that output when the processing on an image is finalized.
* The parameter template system has been comprehensively upgraded.
  * Multiple algorithm task settings are available. You can define barcode decoding, label recognizing, document scanning and semantic processing tasks in one template file.
  * Extended the feature of the ROI system. By configuring the `target ROI` parameters, you can not only specify an `ROI` on the original image but also define the dependencies of the algorithm tasks. This feature enables you to customize the workflow when processing complex scenarios.
  * The image processing parameters are separated from the task parameters so that the template settings become more clear and concise.
* The `intermediate result` system has been improved.
  * Achieved the `intermediate result` sharing between different functional products. The results that have the same image source and processing parameters are directly reused, which speeds up the image processing workflow. You don’t need to add any additional code to enable the `intermediate result` sharing. The library can recognize all the reusable results automatically based on the template file you uploaded.