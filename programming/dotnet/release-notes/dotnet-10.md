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

- Added new functions [`SetMaxOverlappingFrames`]({{ site.dcvb_dotnet_api }}utility/multi-frame-result-cross-filter.html#setmaxoverlappingframes), [`GetMaxOverlappingFrames`]({{ site.dcvb_dotnet_api }}utility/multi-frame-result-cross-filter.html#getmaxoverlappingframes), [`EnableLatestOverlapping`]({{ site.dcvb_dotnet_api }}utility/multi-frame-result-cross-filter.html#enablelatestoverlapping) and [`IsLatestOverlappingEnabled`]({{ site.dcvb_dotnet_api }}utility/multi-frame-result-cross-filter.html#islatestoverlappingenabled) to the class `CMultiFrameResultCrossFilter`.

- Added new error codes
  - `EC_LICENSE_WARNING`
  - `EC_BARCODE_READER_LICENSE_NOT_FOUND`

- Added new properties to the [`QRCodeDetails`]({{ site.dbr_dotnet_api }}qr-code-details.html) class
  - [`codewords`]({{ site.dbr_dotnet_api }}qr-code-details.html#codewords)
  - [`dataMaskPattern`]({{ site.dbr_dotnet_api }}qr-code-details.html#datamaskpattern)

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

{%- include release-notes/dotnet-highlight-10.2.10.md -%}
