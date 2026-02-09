---
layout: default-layout
title: Release Notes v10.x - Dynamsoft Barcode Reader SDK Python Edition
description: This is the release notes page of Dynamsoft Barcode Reader SDK Python Edition v10.x.
keywords: release notes, python
needGenerateH3Content: false
---

# Release Notes for Python Edition - 10.x

## 10.5.2100 (12/05/2024)

### New

- Added `Intermediate Results`, completing DCV's feature set with real-time feedback and interactivity.
- Added support for Python 3.13.

### Fixed

- Removed the `static dependency on NumPy`, allowing users to import it only when needed.

## 10.4.2100 (11/07/2024)

### New

- Added support for `numpy.ndarray` image type in the `capture` interface.

### Improved

- Optimized the usage of list type member variables, allowing modification of individual objects within the list without needing to reassign the entire list.
- Improved the usage of `EnumPresetTemplate` and `EnumBarcodeFormat`, no longer requiring `.value` for accessing enum members.

### Fixed

- Fixed a bug where initializing `FileImageTag` would raise a `TypeError` exception.

## 10.4.2000 (10/10/2024)

### Highlights

`DynamsoftBarcodeReader` SDK has been revamped to integrate with `DynamsoftCaptureVision (DCV)` architecture, which is newly established to aggregate the features of functional products powered by Dynamsoft. The features are designed to be pluggable, customizable and interactable. In addition, the functional products share the computation so that their processing speed is much higher than working individually. To reflect these improvements, the package has been renamed to `dynamsoft-barcode-reader-bundle`.

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