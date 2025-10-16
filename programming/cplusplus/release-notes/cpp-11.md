---
layout: default-layout
title: Release Notes v11.x - Dynamsoft Barcode Reader SDK C++ Edition
description: This is the release notes page of Dynamsoft Barcode Reader SDK C++ Edition v11.x.
keywords: release notes, c++
needGenerateH3Content: false
---

# Release Notes for C++ Edition - 11.x

## 11.2.1000 (10/14/2025)

🎉 **Milestone Release** - This version introduces groundbreaking AI-powered enhancements that significantly improve accuracy and performance across various barcode processing scenarios.

### ✨ Key Highlights

**AI-Powered Barcode Detection & Decoding**
- 🧠 **First-to-Market AI Localization**: Revolutionary [`OneDLocalization`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/localization-modes.html#modelnamearray) and [`DataMatrixQRCodeLocalization`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/localization-modes.html#modelnamearray) neural network models for superior detection of **blurred/low-resolution 1D codes** and **DataMatrix/QR codes with missing or damaged finder patterns**
- ⚡ **Specialized Decoders**: Cutting-edge [`EAN13Decoder`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/deblur-modes.html#modelnamearray) and [`Code128Decoder`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/deblur-modes.html#modelnamearray) models deliver unprecedented accuracy for **blurred and long-distance** scenarios
- 🔍 **Enhanced Clarity Processing**: Completely redesigned [`OneDDeblur`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/deblur-modes.html#modelnamearray) model with superior **motion blur and focus blur** recovery algorithms
- 🎯 **Flexible Model Configuration**: Advanced `ModelNameArray` parameter enables on-demand model loading and precise selection for specific barcode scenarios

**Precision Control**
- ⚙️ **Granular Deblur Methods**: Fine-tuned [`DM_DEEP_ANALYSIS`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/deblur-modes.html#dm_deep_analysis) with specialized method control - `OneDGeneral`, `TwoDGeneral`, and `EAN13Enhanced` for targeted optimization
- 🎯 **Smart Barcode Counting**: New [`ExpectedBarcodesCount`]({{ site.dcvb_parameters_reference }}barcode-format-specification/expected-barcodes-count.html) parameter enables **format-specific quantity control** and **early termination optimization** for known-quantity scenarios
- 🔍 **Advanced Region Detection**: New [`RPM_GRAY_CONSISTENCY`]({{ site.dcvb_parameters_reference }}image-parameter/region-predetection-modes.html#rpm_gray_consistency) mode enables precise region detection based on **grayscale uniformity** and **local consistency** for document and label processing


### 💡 What This Means for You

**For Challenging Barcode Scenarios**
- **Blurred conditions**: 26.5% better read rates with 44% faster processing - ideal for handheld scanning and moving objects
- **Extended distance capability**: Breakthrough support for reading distances beyond 75cm - revolutionizing warehouse automation and high-shelf scanning
- **Damaged 2D codes**: Enhanced detection of DataMatrix and QR codes with missing or damaged finder patterns - perfect for manufacturing and logistics applications

**For Enterprise Integration**
- **Retail environments**: Enhanced performance for blurred handheld scanning and long-distance shelf reading
- **Logistics & shipping**: Improved recognition for package tracking with better blur and long-distance scanning capabilities
- **Manufacturing QC**: Improved 2D code reading on printed/etched parts with wear damage

**For Developers**
- **Backward Compatible**: Seamless upgrade with existing code and easy migration path
- **Flexible Configuration**: Extensive parameter customization for specific use cases and comprehensive model configuration options
- **Enterprise Ready**: Battle-tested stability for production environments

### Changed

- Updated the default value of parameter [`MaxThreadsInOneTask`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/max-threads-in-one-task.html) from 4 to 0 (auto-detection).
- Updated the default value of parameter [`IncludeTrailingCheckDigit`]({{ site.dcvb_parameters_reference }}barcode-format-specification/include-trailing-check-digit.html) from 1 to 0. This means Code128 barcode results will no longer include the trailing check digit in the decoded bytes by default, improving compatibility with industry standards.
- Deprecated argument `DeblurModelNameArray` of parameter [`DeblurModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/deblur-modes.html), use `ModelNameArray` instead.
- Deprecated method `AppendModelBuffer` of class [`CaptureVisionRouter`]({{ site.dcvb_cpp_api }}capture-vision-router/capture-vision-router.html), use [`AppendDLModelBuffer`]({{ site.dcvb_cpp_api }}capture-vision-router/auxiliary-methods.html#appenddlmodelbuffer) instead.

## 11.0.6000 (08/06/2025)

### Changed

- `StartCapturing` now stops immediately and returns a license-related error code if none of the tasks have a valid license, instead of proceeding and returning an empty result.

### Fixed

- Fixed a bug that caused a crash when using a specific type of license.
- Fixed various minor bugs and improved overall stability.

## 11.0.4000 (07/15/2025)

### New

- **Tile-Based TIFF Image Support**: Added support for TIFF images with tile-based storage format.

- **Base64 String Conversion**: Enabled bidirectional conversion between `ImageData` and Base64 strings.

- **Template Version Validation**: Introduced version checking for templates to prevent compatibility issues and mismatches.

### Changed

- **License Validation Behavior**: Instead of stopping execution immediately on an invalid license module, the library now continues processing and returns results from modules with valid licenses. An error is still reported to indicate the license issue.

- **PDFR License Control Removal**: Removed the license check for the PDFR module.

### Fixed

- Fixed various minor bugs and improved overall stability.

## 11.0.3000 (05/13/2025)

### New

- Added support for appending pages to PDF files generated by `CImageIO.SaveToFile`. Appending to other PDF files is not supported.
 
### Fixed

- Fixed an issue where calling `StartCapturing` or `Capture` with `templateName` set to an empty string ("") would result in error `-40103`.
- Resolved a performance issue that could cause unusually high CPU and memory usage in some cases.

### Changed

- Removed the licensing requirement for saving PDFs.

## 11.0.1000 (03/04/2025)

### [Highlights](https://www.dynamsoft.com/release-highlights/?product=dbr11.0)

- Workflow Improvements
  - Restructured the parameter control hierarchy at all levels for finer scope definition and more granular process management, with the stage level newly added.
  - Enabled custom combinations and sequences of sections, increasing flexibility and operational customization under specific conditions.

- Deep Learning Integration
  - Improved the reading rate of 1D barcode by introducing a new deblurring deep-learning model.

- Algorithm Enhancements
  - Enabled deduplication at the Region of Interest (ROI) level to consolidate results from multiple tasks.
  - Improved the **CODE_128** and **DataMatrix** DeepAnalysis algorithms for better decoding accuracy and performance.
  - Added support for new barcode types: **CODE_32**, **MATRIX_25**, **KIX**, and **TELEPEN**.

- Engineering Optimizations
  - Unified template-loading logic to reduce I/O overhead.
  - Added support for capturing data from multi-page files, including **PDF** and **TIFF** formats.
  - Implemented conversion functionality between `CImageData` and image files, including both on-disk and in-memory files.
