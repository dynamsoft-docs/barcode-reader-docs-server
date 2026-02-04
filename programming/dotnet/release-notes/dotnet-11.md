---
layout: default-layout
title: Release Notes v11.x - Dynamsoft Barcode Reader SDK .NET Edition
description: This is the release notes page of Dynamsoft Barcode Reader SDK .NET Edition v11.x.
keywords: release notes, .NET
needGenerateH3Content: false
---

# Release Notes for .NET Edition - 11.x

## 11.4.1000 (02/05/2026)

### Highlights

#### AI-Powered Barcode Detection and Decoding

- **PDF417 Localization Model** – Introduces the [`PDF417Localization`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/localization-modes.html#modelnamearray) neural network model for improved detection of PDF417 barcodes, especially in challenging conditions.

- **Code39/ITF Decoding Model** – Adds the [`Code39ITFDecoder`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/deblur-modes.html#modelnamearray) model for enhanced decoding of Code 39 and ITF barcodes under blur or low-resolution conditions.

- **Deblur Models for 2D Barcodes** – New [`DataMatrixQRCodeDeblur`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/deblur-modes.html#modelnamearray) and [`PDF417Deblur`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/deblur-modes.html#modelnamearray) models provide more effective recovery from motion and focus blur for DataMatrix, QR Code, and PDF417 barcodes.

#### ECI (Extended Channel Interpretation) Support

- **ECI Information Return** – Added support for retrieving Extended Channel Interpretation (ECI) data from barcodes. The new [`ECISegment`]({{ site.dbr_dotnet_api }}eci-segment.html) class along with `GetECISegmentsCount()` and `GetECISegment()` methods in [`BarcodeResultItem`]({{ site.dbr_dotnet_api }}barcode-result-item.html#getecisegment) and [`DecodedBarcodeElement`]({{ site.dbr_dotnet_api }}decoded-barcode-element.html#getecisegment) classes enable access to character encoding information embedded in barcodes.

- **Automatic UTF-8 Conversion** – Barcode text now respects ECI segments when available, improving compatibility with international character sets.

#### Performance Improvements

- **On-Demand Model Loading** – Implemented lazy loading for AI models, reducing initialization time by loading models only when first needed.

- **Smart Model Selection** – Models are now loaded based on configured barcode formats, minimizing memory usage by excluding unused models.

- **Improved Confidence Scoring** – Enhanced confidence score calculation for results from neural network models, providing more accurate quality indicators.

- **DPM Barcode Optimization** – Improved recognition rate for Direct Part Marking (DPM) barcodes commonly used in industrial and manufacturing environments.

### New

- Added [`BarcodeZoneWidthToHeightRatioRangeArray`]({{ site.dcvb_parameters_reference }}barcode-format-specification/barcode-zone-width-to-height-ratio-range-array.html) parameter for filtering barcodes based on aspect ratio constraints.

- Added [`SetResultCrossVerificationCriteria()`]({{ site.dcvb_dotnet_api }}utility/multi-frame-result-cross-filter.html#setresultcrossverificationcriteria) and [`GetResultCrossVerificationCriteria()`]({{ site.dcvb_dotnet_api }}utility/multi-frame-result-cross-filter.html#getresultcrossverificationcriteria) methods to `MultiFrameResultCrossFilter` for configurable multi-frame result verification.

### Changed

- `CaptureMultiPages` now returns results sorted by page number.

- Barcode text encoding fallback changed from UTF-8 to ISO-8859-1 when no ECI information is present in the barcode.

- Improved license binding stability on MacOS devices.

- Updated default value of `compensation` parameter in [`ImageProcessor.ConvertToBinaryLocal()`]({{ site.dcvb_dotnet_api }}utility/image-processor.html#converttobinarylocal) from 0 to 10.

- [`ConvertToBinaryGlobal()`]({{ site.dcvb_dotnet_api }}utility/image-processor.html#converttobinaryglobal) and [`ConvertToBinaryLocal()`]({{ site.dcvb_dotnet_api }}utility/image-processor.html#converttobinarylocal) of `ImageProcessor` class now support color and binary images as input in addition to grayscale images.

- Removed `DataMatrixModuleIsotropic` parameter – use [`BarcodeZoneWidthToHeightRatioRangeArray`]({{ site.dcvb_parameters_reference }}barcode-format-specification/barcode-zone-width-to-height-ratio-range-array.html) instead.

- Removed `MinRatioOfBarcodeZoneWidthToHeight` parameter – use [`BarcodeZoneWidthToHeightRatioRangeArray`]({{ site.dcvb_parameters_reference }}barcode-format-specification/barcode-zone-width-to-height-ratio-range-array.html) instead.

### Fixed

- Fixed incorrect coordinate in barcode result when using neural network models with a specified region.
- Fixed crash and hang issues that could occur in certain scenarios.
- Fixed various minor bugs and improved overall stability.


## 11.2.5000 (12/16/2025)

This release includes security maintenance updates to ensure continued protection of the product.

### Security Updates

- Updated third-party libraries to incorporate the latest security fixes.

### Bug Fixes

- Fixed memory leak, crash, and hang issues in various scenarios.
- Improved stability in multi-threading operations.

## 11.2.1000 (10/14/2025)

### 🎉Milestone Release
Version 11.2.1000 introduces a series of AI-driven improvements designed to enhance barcode detection accuracy, processing speed, and configuration flexibility.

This release focuses on practical performance gains for production environments across retail, logistics, and manufacturing workflows.

### ✨ Key Highlights
#### AI-Powered Barcode Detection and Decoding

- New Localization Models – Introduces [`OneDLocalization`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/localization-modes.html#modelnamearray) and [`DataMatrixQRCodeLocalization`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/localization-modes.html#modelnamearray) neural network models for improved detection of **blurred / low-resolution 1D codes**, or **partially damaged DataMatrix/QR codes**.
- Specialized Decoders – Adds [`EAN13Decoder`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/deblur-modes.html#modelnamearray) and [`Code128Decoder`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/deblur-modes.html#modelnamearray) models optimized for **long-distance** and **motion-blurred** decoding scenarios.
- Redesigned Deblur Model – The [`OneDDeblur`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/deblur-modes.html#modelnamearray) model now provides more effective recovery from **motion and focus blur**.
- Configurable Model Selection – The new `ModelNameArray` parameter supports flexible model loading and fine-grained control for specific barcode types.

#### Precision and Processing Control

- Enhanced Deblur Methods – [`DM_DEEP_ANALYSIS`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/deblur-modes.html#dm_deep_analysis) now includes sub-level control with `OneDGeneral`, `TwoDGeneral`, and `EAN13Enhanced` options.
- Barcode Count Expectation – The new [`ExpectedBarcodesCount`]({{ site.dcvb_parameters_reference }}barcode-format-specification/expected-barcodes-count.html) parameter enables **format-specific quantity control** and **early termination** in fixed-count workflows.
- Improved Region Detection – The new [`RPM_GRAY_CONSISTENCY`]({{ site.dcvb_parameters_reference }}image-parameter/region-predetection-modes.html#rpm_gray_consistency) mode provides more precise region extraction based on **grayscale uniformity** and **local consistency** for document and label processing.

### Performance Highlights

#### Barcode Workflows

- Up to **26.5%** higher read rates under blur conditions with as much as **44%** faster processing.
- Reliable decoding of DataMatrix and QR codes with missing or damaged finder patterns.
- Extended operational range beyond 75 cm for long-distance barcode scanning.

### Developer Notes

- Backward Compatibility – Fully compatible with existing integrations; no code-level changes required for upgrade.
- Configuration Flexibility – Expanded parameter set allows comprehensive model configuration for scenario-specific tuning.
- Production Stability – All new models validated in enterprise environments.

### Changed

#### Parameter Defaults

- [`MaxThreadsInOneTask`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/max-threads-in-one-task.html): default changed from 4 → 0 (auto-detection).
- [`IncludeTrailingCheckDigit`]({{ site.dcvb_parameters_reference }}barcode-format-specification/include-trailing-check-digit.html): default changed from 1 → 0. Code128 results will no longer include the trailing check digit by default for improved compliance with standard decoding practices.

### Deprecations

- `DeblurModelNameArray` argument of [`DeblurModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/deblur-modes.html) → use `ModelNameArray`.
- `AppendModelBuffer` method of `CaptureVisionRouter` → use [`AppendDLModelBuffer`]({{ site.dcvb_dotnet_api }}capture-vision-router/auxiliary-methods.html#appenddlmodelbuffer).

### Fixed

- Fixed an issue where `MultiFrameResultCrossFilter` was not working properly.

## 11.0.6000 (08/06/2025)

### Changed

- `StartCapturing` now stops immediately and returns a license-related error code if none of the tasks have a valid license, instead of proceeding and returning an empty result.

### Fixed

- Fixed a bug that caused a crash when using a specific type of license.
- Fixed a crash that occurred when calling the default constructor of `FileImageTag` or `VideoFrameTag`.
- Fixed various minor bugs and improved overall stability.

## 11.0.4000 (07/15/2025)

### New

- **Tile-Based TIFF Image Support**: Added support for TIFF images with tile-based storage format.

- **Base64 String Conversion**: Enabled bidirectional conversion between `ImageData` and Base64 strings.

- **Template Version Validation**: Introduced version checking for templates to prevent compatibility issues and mismatches.

### Changed

- **License Validation Behavior**: Instead of stopping execution immediately on an invalid license module, the library now continues processing and returns results from modules with valid licenses. An error is still reported to indicate the license issue.

- **PDFR License Control Removal**: Removed the license check for the PDFR module.

- **Property Renamed in `PDFReadingParameter`**: The property `dip` has been renamed to `dpi` to fix a naming error.

### Fixed

- Fixed various minor bugs and improved overall stability.

## 11.0.3000 (05/13/2025)

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
  - Implemented conversion functionality between `ImageData` and image files, including both on-disk and in-memory files.