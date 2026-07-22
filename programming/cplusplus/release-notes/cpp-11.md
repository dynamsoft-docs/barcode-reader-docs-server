---
layout: default-layout
title: Release Notes v11.x - Dynamsoft Barcode Reader SDK C++ Edition
description: Release notes for Dynamsoft Barcode Reader SDK C++ Edition v11.x, highlighting AI-powered barcode detection models, ECI support, on-demand model loading, and performance improvements.
keywords: release notes, c++
needGenerateH3Content: false
---

# Release Notes for C++ Edition - 11.x

## 11.6.1000 (07/23/2026)

### Highlights

#### Multimodal PDF Content Extraction

- **New PDF Reading Mode** - Added [`PDFRM_MULTIMODAL`]({{ site.dcvb_cpp_api }}core/enum-pdf-reading-mode.html) to [`PDFReadingMode`]({{ site.dcvb_cpp_api }}core/enum-pdf-reading-mode.html), now the default for [`PDFReadingParameter`]({{ site.dcvb_cpp_api }}core/basic-structures/pdf-reading-parameter.html). It extracts vector graphics, text content, and embedded images from PDF files, enabling stronger barcode reading performance in multimodal PDF scenarios.
- **Performance Behavior Update** - Compared with full-page raster rendering, [`PDFRM_MULTIMODAL`]({{ site.dcvb_cpp_api }}core/enum-pdf-reading-mode.html) usually improves speed by avoiding unnecessary rendering of irrelevant regions.

#### Multi-Threaded Barcode Decoding

- **Get results sooner with parallel processing** - Barcode decoding now uses a breadth-first strategy that decomposes a single DBR Task into one Localization Work and one or more Decoding Works. This improves thread utilization and reduces the chance that a slow `DeblurMode` attempt blocks other faster decoding attempts, helping valid results come back sooner.

#### DataMatrix Color Inversion Detection

- **Handle normal and inverted DataMatrix more efficiently** - Added [`AutoDetectColorInversion`]({{ site.dcvb_parameters_reference }}barcode-format-specification/auto-detect-color-inversion.html) to automatically handle both normal and inverted DataMatrix barcodes. Instead of processing the whole image twice, the SDK applies dual-polarity handling only to localized DataMatrix regions, which makes processing faster in dual-polarity scenarios.

#### Barcode Layout Analysis

- **Decode dense grid barcodes more completely** - Added [`CLayoutAnalyzer`]({{ site.dcvb_cpp_api }}utility/layout-analyzer.html) to organize barcode locations into logical line or matrix layouts and infer unrecognized barcode regions when gaps exist, enabling workflows such as fast first-pass decoding, missing-region inference, and targeted second-pass decoding on dense N*M barcode layouts.

#### Cross-Version License Support

- **Use a single license across SDK versions** - Full License 1.0 keys (starting with "f") that are non-perpetual are no longer version-checked, so the same key can be used across SDK versions without reactivation.

### New

- Added [`PDFRM_MULTIMODAL`]({{ site.dcvb_cpp_api }}core/enum-pdf-reading-mode.html) value to [`PDFReadingMode`]({{ site.dcvb_cpp_api }}core/enum-pdf-reading-mode.html) enumeration for multimodal PDF content extraction. [`PDFRM_VECTOR`]({{ site.dcvb_cpp_api }}core/enum-pdf-reading-mode.html) is now deprecated.

- Added [`AutoDetectColorInversion`]({{ site.dcvb_parameters_reference }}barcode-format-specification/auto-detect-color-inversion.html) parameter for `BarcodeFormatSpecification` to support automatic color-inversion detection for DataMatrix barcodes.

- Added a new overload of [`CaptureMultiPages()`]({{ site.dcvb_cpp_api }}capture-vision-router/single-file-processing.html#capturemultipages) that accepts a [`CFileFetcher`]({{ site.dcvb_cpp_api }}utility/file-fetcher.html) parameter for more flexible file input handling.

- Added [`CLayoutAnalyzer`]({{ site.dcvb_cpp_api }}utility/layout-analyzer.html) class with [`Analyze()`]({{ site.dcvb_cpp_api }}utility/layout-analyzer.html#analyze) and [`ReleaseResult()`]({{ site.dcvb_cpp_api }}utility/layout-analyzer.html#releaseresult) static methods for quadrilateral layout analysis.

- Added [`LayoutPattern`]({{ site.dcvb_cpp_api }}utility/enum-layout-pattern.html) enumeration with values `LP_UNKNOWN`, `LP_LINES`, and `LP_MATRIX`.

- Added [`LayoutElementSource`]({{ site.dcvb_cpp_api }}utility/enum-layout-element-source.html) enumeration with values `LES_NONE`, `LES_INPUT`, and `LES_INFERRED`.

- Added [`MeasureUnit`]({{ site.dcvb_cpp_api }}core/enum-measure-unit.html) enumeration with values `MU_PIXEL` and `MU_PERCENTAGE`.

- Added structures [`LayoutAxis`]({{ site.dcvb_cpp_api }}utility/layout-axis.html), [`LayoutAnalysisParameter`]({{ site.dcvb_cpp_api }}utility/layout-analysis-parameter.html), [`LayoutElement`]({{ site.dcvb_cpp_api }}utility/layout-element.html), and [`LayoutAnalysisResult`]({{ site.dcvb_cpp_api }}utility/layout-analysis-result.html) for layout analysis configuration and results.

- Added a new `GridBarcodeScanner` sample (with `sample_grid.png`) to demonstrate how to use [`CLayoutAnalyzer`]({{ site.dcvb_cpp_api }}utility/layout-analyzer.html) for barcode grid layout detection and logical row/column mapping.

### Changed

- Default [`PDFReadingMode`]({{ site.dcvb_cpp_api }}core/enum-pdf-reading-mode.html) in [`PDFReadingParameter`]({{ site.dcvb_cpp_api }}core/basic-structures/pdf-reading-parameter.html) constructor changed from [`PDFRM_RASTER`]({{ site.dcvb_cpp_api }}core/enum-pdf-reading-mode.html) to [`PDFRM_MULTIMODAL`]({{ site.dcvb_cpp_api }}core/enum-pdf-reading-mode.html).

- [`MaxParallelTasks`]({{ site.dcvb_parameters_reference }}capture-vision-template/max-parallel-tasks.html) now controls the total number of Work-level threads in the CVR thread pool. For DBR tasks, each Localization Work and Decoding Work occupies one thread slot. DLR and DDN tasks continue to occupy one thread per task.

- [`SetDeviceFriendlyName()`]({{ site.dcvb_cpp_api }}license/license-manager.html#setdevicefriendlyname) now enforces parameter constraints: maximum 64 characters, allowed characters are letters (a-z, A-Z), digits (0-9), hyphen (-), underscore (_), and period (.), and must start and end with a letter or digit. Returns [`EC_PARAMETER_VALUE_INVALID`]({{ site.dcvb_cpp_api }}core/enum-error-code.html) if constraints are not met.

- The Linux ARM64 minimum requirement is now glibc 2.27 (Ubuntu 18.04+, Debian 10+, and CentOS/RHEL 8+).

- The Visual Studio minimum requirement is now VS2015.

### Fixed

- Fixed a crash that could occur in AWS Lambda environments under certain conditions.

- Fixed an issue in GS1-Databar AI `17` (YYMMDD) results where the month field could be missing a leading zero.

### Deprecations

- Marked `PDFRM_VECTOR` as deprecated (covered by [`PDFRM_MULTIMODAL`]({{ site.dcvb_cpp_api }}core/enum-pdf-reading-mode.html)).


## 11.4.3000 (06/30/2026)

### Security Updates

- Updated third-party libraries to incorporate the latest security fixes.

## 11.4.2001 (04/17/2026)

### Security Updates

- Updated third-party libraries to incorporate the latest security fixes.

## 11.4.2000 (03/18/2026)

### Security Updates

- Updated third-party libraries to incorporate the latest security fixes.

### Bug Fixes

- Fixed an issue where the SDK might attempt to load corrupted model resource files in rare cases.

## 11.4.1000 (02/05/2026)

### Highlights

#### AI-Powered Barcode Detection and Decoding

- **PDF417 Localization Model** – Introduces the [`PDF417Localization`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/localization-modes.html#modelnamearray) neural network model for improved detection of PDF417 barcodes, especially under challenging conditions.

- **Code39/ITF Decoding Model** – Adds the [`Code39ITFDecoder`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/deblur-modes.html#modelnamearray) model for enhanced decoding of Code 39 and ITF barcodes under blurred or low-resolution conditions.

- **Deblur Models for 2D Barcodes** – Adds the [`DataMatrixQRCodeDeblur`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/deblur-modes.html#modelnamearray) and [`PDF417Deblur`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/deblur-modes.html#modelnamearray) models to provide more effective recovery from motion and focus blur for DataMatrix, QR Code, and PDF417 barcodes.

#### ECI (Extended Channel Interpretation) Support

- **ECI Information Return** – Adds support for retrieving Extended Channel Interpretation (ECI) data from barcodes. The new [`CECISegment`]({{ site.dbr_cpp_api }}eci-segment.html) class, along with the `GetECISegmentsCount()` and `GetECISegment()` methods in the [`CBarcodeResultItem`]({{ site.dbr_cpp_api }}barcode-result-item.html#getecisegment) and [`CDecodedBarcodeElement`]({{ site.dbr_cpp_api }}decoded-barcode-element.html#getecisegment) classes, enables access to character encoding information embedded in barcodes.

- **ECI-Based Text Interpretation** – Adds support for interpreting ECI segments during barcode decoding, improving compatibility with international character sets.

#### Performance Improvements

- **On-Demand Model Loading** – Implements lazy loading for AI models, reducing initialization time by loading models only when first needed.

- **Smart Model Selection** – Models are now loaded based on configured barcode formats, minimizing memory usage by excluding unused models.

- **Improved Confidence Scoring** – Enhances confidence score calculation for results from neural network models, providing more accurate quality indicators.

- **DPM Barcode Optimization** – Improves recognition rate for Direct Part Marking (DPM) barcodes commonly used in industrial and manufacturing environments.

### New

- Added [`BarcodeZoneWidthToHeightRatioRangeArray`]({{ site.dcvb_parameters_reference }}barcode-format-specification/barcode-zone-width-to-height-ratio-range-array.html) parameter for filtering barcodes based on aspect ratio constraints.

- Added [`SetResultCrossVerificationCriteria()`]({{ site.dcvb_cpp_api }}utility/multi-frame-result-cross-filter.html#setresultcrossverificationcriteria) and [`GetResultCrossVerificationCriteria()`]({{ site.dcvb_cpp_api }}utility/multi-frame-result-cross-filter.html#getresultcrossverificationcriteria) methods to `CMultiFrameResultCrossFilter` for configurable multi-frame result verification.

### Changed

- `CaptureMultiPages` now returns results sorted by page number.

- Barcode text encoding fallback changed from UTF-8 to ISO-8859-1 when no ECI information is present in the barcode.

- Updated default value of `compensation` parameter in [`CImageProcessor::ConvertToBinaryLocal()`]({{ site.dcvb_cpp_api }}utility/image-processor.html#converttobinarylocal) from 0 to 10.

- [`ConvertToBinaryGlobal()`]({{ site.dcvb_cpp_api }}utility/image-processor.html#converttobinaryglobal) and [`ConvertToBinaryLocal()`]({{ site.dcvb_cpp_api }}utility/image-processor.html#converttobinarylocal) of `CImageProcessor` class now support color, binary and grayscale images as input.

### Improved

- Improved license binding stability on macOS devices.

### Removed

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
- `AppendModelBuffer` method of `CaptureVisionRouter` → use [`AppendDLModelBuffer`]({{ site.dcvb_cpp_api }}capture-vision-router/auxiliary-methods.html#appenddlmodelbuffer).

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
