---
layout: default-layout
title: Release Notes v10.x - Dynamsoft Barcode Reader SDK C++ Edition
description: This is the release notes page of Dynamsoft Barcode Reader SDK C++ Edition v10.x.
keywords: release notes, c++
needGenerateH3Content: false
---

# Release Notes for C++ Edition - 10.x

## 10.4.2000 (10/10/2024)

### Highlights

- Added to-the-latest overlapping feature.
- Added ARM64 and MacOS components back to the SDK.
- Improved the error handling logic of `Capture`, `StartCapturing` and `InitLicense` methods to clearly report a licensing issue.

### Changelogs

#### New

- Added new functions `SetMaxOverlappingFrames`, `GetMaxOverlappingFrames`, `EnableLatestOverlapping` and `IsLatestOverlappingEnabled` to the class `CMultiFrameResultCrossFilter`.

- Added new error codes
  - `EC_LICENSE_WARNING`
  - `EC_BARCODE_READER_LICENSE_NOT_FOUND`

- Added new properties to the `CPDF417Details` class
  - `codewords`
  - `codewordsCount`


#### Fixed

- Fixed a crash bug caused by the usage of RegEx.
- Fixed a bug that could prevent the reading of `GS1_DATABAR_EXPANDED_STACKED` barcodes.
- Small fixes and tweaks.

#### Changed

- Changed the template loading mode. By default, the library loads all template files from the `Templates` folder in the same directory as the library file.
- Changed the enumeration value of `BarcodeFormat::BF_ALL` to 0xFFFFFFFEFFFFFFFF.

### Included Submodules and Their Versions

The following submodules are included in this SDK release along with their respective versions:
- **DynamsoftCaptureVisionRouter** Module: v2.4.20
- **DynamsoftCore** Module: v3.4.20
- **DynamsoftLicense** Module: v3.4.20
- **DynamsoftUtility** Module: v1.4.20
- **DynamsoftImageProcessing** Module: v2.4.20
- **DynamsoftBarcodeReader** Module: v10.4.20

## 10.4.10 (07/23/2024)

### Improved

- Improved the read rate and speed of the following barcode formats:
  - EAN-13
  - DotCode

### New

- Added support for decoding add-on codes (also known as Extension Codes) for UPC-A, UPC-E, EAN-8 and EAN-13 codes.
- Added new properties to the `CQRCodeDetails` class
  - `dataMaskPattern`
  - `codewords`
  - `codewordsCount`
- Added a new function `AddItem` to the class `CDecodedBarcodesResult`.
- Added a new function `SetLocation` to the class `CBarcodeResultItem`.
- Added a new function `Clone` to the class `CCapturedResultItem`.
- Added a new function `AddItem` to the class `CCapturedResult`.

### Changed

- Changed the maximum length of the `name` parameter to 255 for the `SetDeviceFriendlyName` method. If the length exceeds 255, it will be truncated.

- Changed the default value of the `waitForThreadExit` parameter to `true` for the `StopCapturing` method.
 
### Fixed

- Fixed a bug where UPC-E barcodes starting with the digit 1 cannot be decoded.
- Fixed a bug where `CaptureVisionRouter.StartCapturing` would erroneously halt the fetching process when its status was running, leading to an unnecessary stop and restart of the fetching operation.
- Fixed a bug where `CDirectoryFetcher` would prematurely read an image before verifying if the buffer was full, resulting in potential loss of the image that did not make it into the buffer upon calling `StopFetching`.
  
## 10.2.10 (03/01/2024)

### Improved

- Security update for `DynamsoftBarcodeReader` library and other corresponding libraries.
- Supported multiple instances of the class `CCaptureVisionRouter`.
- Improved the usage count logic of the concurrent license mode.
- Improved the experience of local cache usage when failing to connect the license server. The renewal of the local cache is optimized as well.
- Improved the barcode decoding performance:
  - Improved the accuracy when decoding OneD & PDF417 barcodes.
  - Improved the readability of dense DataMatrix codes.

### New

- Added new error codes:
  - `EC_RESULT_TYPE_MISMATCH_IRREPLACEABLE`
  - `EC_LICENSE_CACHE_USED`
- Added a virtual destructor to the interface `CImageSourceErrorListener` to prevent memory leaks.
- Added a new function `GetDecodedBarcodesResult` to the `CCapturedResult` class to get all the result items with the type `CRIT_BARCODE`.
- Added new virtual destructors to the following interfaces to prevent memory leaks.
  - `CCaptureStateListener`
  - `CImageSourceStateListener`

### Changed

- Changed the internal logic of the function `SetResultUnitTypesOnlyForInput` of `ObservationParameters`. The function only takes effect when the callback of the specified result unit is implemented.

### Fixed

- Fixed a crash bug of the Replace method of the `IntermediateResultUnit` class. The method will return the error code `EC_RESULT_TYPE_MISMATCH_IRREPLACEABLE` when the result type is mismatched.
- Fixed a bug where error messages are not output when parsing the parameter templates.
- Fixed a misreading bug of the PDF417 barcodes on the South Carolina driver's license.
- Internal changes to prevent crash bugs in barcode decoding.
- Fixed a bug where the capture might be blocked due to the network latency.
- Fixed a bug where the `DetectAndNormalizeDocument` task might be approved without a valid license.
- Fixed the bugs of usage count.
  - Count twice for a single PDF417 barcode when a code parser task is implemented on the result.
  - The barcode decoding result might not be uploaded timely.
  - The usage count of text line recognition might be double counted when the intermediate results are output.
  - The document boundary detection result might be miscounted.
  - Patchcode might be counted even if there is no Patchcode license item.

## 10.2.0 (01/16/2024)

### Highlights

- Introduced the capability for users to influence the image processing process by altering intermediate results. Users can now clone, edit, and substitute intermediate result units within the callback function of each type. Subsequent operations will then proceed based on the updated unit.
- Introduced a feature for multi-condition filtering across products. Users can now specify filtering criteria for the task results of a `TargetROIDef` by implementing an `OutputTaskSetting` based on the task results of varying products from descendant `TargetROIDef` objects.
- Enhanced the `Offset` parameter in `TargetROIDef`. Users now have the capability to meticulously customize components of the coordinate system, including the origin, X-axis, and Y-axis, for precise offset calculation.

### Changelogs

#### New

- Updated the template system
  - Added `StringLengthRange` for TextDetectionMode.
  - Added Argument `BarcodeFormat` for `DPMCodeReadingModes`. Currently, you can specify "BF_DATAMATRIX"  or "BF_QR_CODE" for the parameter.
  - Added `ReferenceTaskNameArray` under `Location.ReferenceObjectFilter` to filter the reference objects generated by the task name.
  - Added the support of the `OutputTaskSetting` definition. The following subparameters are available in `OutputTaskSetting` object:
    - `OutputCondition`
    - `TaskResultArray`
    - `TargetROIDefName`
    - `TaskSettingNameArray`
    - `BackwardReferenceOutput`
    - `ReferenceTaskNameArray`
    - `ReferenceResultTypeArray`
    - `Operator`
  - Offset parameter is optimized.
  - Added `ReferenceObjectType` to specify whether the reference object is an atomic object or the whole image.
  - Added `ReferenceXAxis` & `ReferenceYAxis` to define the X & Y axis.
  - Modified `FirstPoint`, `SecondPoint`, `ThirdPoint` & `FourthPoint`. You can specify whether the X or Y coordinate of the point is measured by percentage.
  - Deprecated `ReferenceObjectSize` Type.
- The following classes are migrated from `DynamsoftCore` module to the `DynamsoftCaptureVisionRouter` module:
  - `CIntermediateResultReceiver`
  - `CapturedResultReceiver`
  - `CapturedResultFilter`
  - `CIntermediateResultManager`
- Added a new class back method `OnShortLinesUnitReceived` to the `CIntermediateResultReceiver` class.
- Added a new class `CAbstractIntermediateResultReceiver`. It is the super class of the `CIntermediateResultReceiver`.
- Added methods `PauseCapturing` and `ResumeCapturing`. Two new `CapturedState` members, `CS_PAUSED` and `CS_RESUMED`, are added as well.
- Added a new property `documentSettings` to struct `SimplifiedCaptureVisionSettings`. The corresponding struct `SimplifiedDocumentNormalizerSettings` is added to the `DynamsoftDocumentNormalizer` module to store the `documentSettings`.
- Added the following methods to the `CObservationParameters` class to specify the `input only` result unit.
  - `SetResultUnitTypesOnlyForInput`
  - `GetResultUnitTypesOnlyForInput`
  - `IsResultUnitTypeOnlyForInput`
- Added the following methods to the `CRegionObjectElement` class to support the intermediate result modification.
  - `SetLocation`
  - `Clone`
  - `Retain`
  - `Release`
- Added a new method `Replace` to the `CIntermediateResultUnit` class to support the replacement of intermediate result units.
- Added `SetImageData` methods to the following classes:
  - `CColourImageUnit`
  - `CScaledDownColourImageUnit`
  - `CGrayscaleImageUnit`
  - `CTransformedGrayscaleImageUnit`
  - `CEnhancedGrayscaleImageUnit`
  - `CBinaryImageUnit`
  - `CTextureRemovedGrayscaleImageUnit`
  - `CTextureRemovedBinaryImageUnit`
  - `CTextRemovedBinaryImageUnit`
- Added new methods to the `CPredetectedRegionsUnit` class to add, remove or set the predetected regions.
- Added new methods to the `CLineSegmentsUnit` class to add, remove or set the line segments.
- Added new methods to the `CTextZonesUnit` class to add, remove or set the text zones. Added a new class `CTextZone` to store the information of a single text zone.
- Added a new method `SetContours` to the `CContourUnit` class.
- Added new methods to the `CTextureDetectionResultUnit` class to set the X & Y spacing.
- Added a new intermediate result unit, `CShortLinesUnit`, to output the detected short lines. The corresponding enumeration member `IRUT_SHORT_LINES` is added to the `IntermediateResultUnitType`.
- Added the following methods to the `CCapturedResultItem` class
  - `GetTargetROIDefName`
  - `GetTaskName`
  - `Retain`
  - `Release`
- Added the following new error codes
  - `EC_IMAGE_SIZE_NOT_MATCH`
  - `EC_IMAGE_PIXEL_FORMAT_NOT_MATCH`
  - `EC_SECTION_LEVEL_RESULT_IRREPLACEABLE`
  - `EC_AXIS_DEFINITION_INCORRECT`
- Added the following methods to the `CCapturedResult` class.
  - A new override constructor.
  - `Retain`
  - `Release`
- Updated `CImageData` class
  - Change the return value of `GetBytesLength` from int to unsigned long long.
  - Added a new constructor.
- Added a new supported image pixel format, binary 8 inverted. The corresponding enumeration member is added to the `ImagePixelFormat`.
- Added return value for the `Retain` method of the `CIntermediateResultUnit` class. The method will return the pointer of the current `CIntermediateResultUnit`.
- Added a new method `CreatePredetectedRegionElement` to the `CImageProcessingModule` class to create the predetected region element.
- Add C interfaces and implementations, which are only used to encapsulate upper-level languages such as c# and python, etc.
- Added new methods to the `CCandidateBarcodeZonesUnit` class to add, remove or set the candidate barcode zones. `CCandidateBarcodeZone` class is added to store the information of a single candidate barcode zone.
- Added new methods to the `CLocalizedBarcodesUnit` class to add, remove or set the localized barcode elements.
- Added a new method `SetImageData` to the `CScaledUpBarcodeImageUnit` class.
- Added new methods to the `CDeformationResistedBarcodeImageUnit` class to add, remove or set the deformation-resisted barcode. `CDeformationResistedBarcode` class is added to store the deformation-resisted barcode information.
- Added a new method `SetLocation` to `CComplementedBarcodeImageUnit` class.
- Added new methods to the `CDecodedBarcodesUnit` class to set or remove the decoded barcode elements.
- Added the following methods to the `CDecodedBarcodesResult` class:
  - A new override constructor.
  - `Retain`
  - `Release`.
- Added the following methods to the `CBarcodeReaderModule` class to create the corresponding elements.
  - `CreateDecodedBarcodeElement`
  - `CreateLocalizedBarcodeElement`
- Added the following methods to the `CDecodeBarcodeElement` class to modify the basic information of the barcode:
  - `SetFormat`
  - `SetText`
  - `SetBytes`
  - `SetConfidence`
- Added a new method `SetPossibleFormats` to the `CLocalizedBarcodeElement`.

#### Fixed

- Fixed a crash bug that might happen when triggering the `SetNextImageToReturn` method of the `ImageSourceAdapter` class.

#### Breaking Changes

- Changed the logic of the `StopCapturing` method.
  - `CaptureResultReceiver` will not receive results after `StopCapturing` is triggered with `waitForRemainingTasks` false.
  - Support stop capturing after the `PauseCapturing` method is triggered.
- Changed the logic of the `capturedResultItemTypes` setting of `SimplifiedCaptureVisionSettings`:
  - If the result item types don't match the specified template, the method `UpdateSettings` will return the error code `EC_PARAMETER_VALUE_INVALID` with the message "The captured result item types do not match the task configurations in the template".
  - Based on the `capturedResultItemTypes` setting, the irrelevant tasks will be removed from the template.
  - The `capturedResultItemTypes` should include at least one of the `CRIT_BARCODE`, `CRIT_TEXT_LINE`, `CRIT_DETECTED_QUAD`, `CRIT_NORMALIZED_IMAGE`. Otherwise, the method `UpdateSettings` will return the error code `EC_PARAMETER_VALUE_INVALID` with the message "The captured result item types should contain at least one task result type".
- Refactored the `CContour` class. Please view API reference - `CContour` class for more information.
- The destructor functions of the following classes are changed to protected:
  - `CCapturedResult`
  - `CCapturedResultItem`
  - `CRegionObjectElement`
  - `CIntermediateResultUnit`
  - `CCandidateBarcodeZonesUnit`
  - `CLocalizedBarcodesUnit`
  - `CScaledUpBarcodeImageUnit`
  - `CDeformationResistedBarcodeImageUnit`
  - `CComplementedBarcodeImageUnit`
  - `CDecodedBarcodesUnit`
  - `CDecodedBarcodeElement`
  - `CLocalizedBarcodeElement`
  - `CDecodedBarcodesResult`
  - `CBarcodeResultItem`
- Change the compiler option of the runtime library of Windows DLLs from MD to MT.
- The `DeepNeuralNetwork` module is separated from the `DynamsoftImageProcessing` module.

## 10.0.20 (10/26/2023)

### New

- Added the following preset templates:
  - `PT_READ_BARCODES_SPEED_FIRST`
  - `PT_READ_BARCODES_READ_RATE_FIRST`
  - `PT_READ_SINGLE_BARCODE`
- Added a new parameter `Page` to `ImageSource` object.
- Added a new method `SetPages` to the class `CDirectoryFetcher` and class `CFileFetcher`.
- Added a new parameter `scaleDownThreshold` to the struct `SimplifiedBarcodeReaderSettings`.
- Added `CImageSourceErrorListener` to receive the errors from an image source. 
- Added a new method `SetErrorListener` to class `CImageSourceAdapter` to add the `CImageSourceErrorListener`.
- Added a new parameter `minImageCaptureInterval` which can be set via the struct `SimplifiedCaptureVisionSettings` or the `CaptureVisionTemplate` object of a JSON template file.
- Added "UNKNOWN" as a supported and default value of the `TextDetectionMode.Direction` parameter.
- Added the following error codes:
  - `EC_FILE_ALREADY_EXISTS`
  - `EC_CREATE_FILE_FAILED`
  - `EC_IMGAE_DATA_INVALID`

### Improved

- Added ability to output all templates via methods `OutputSettings` and `OutputSettingsToFile` by specifying "*" for the parameter `templateName`.
- The class `CDirectoryFetcher` and `CFileFetcher` will be able to return error codes via `CImageSourceErrorListener`.
- Updated the error codes of the method `SaveToFile` of the class `CImageManager`.
- Optimized the logic to support calling `CIntermediateResultManager.AddResultReceiver` and  `CIntermediateResultManager.RemoveResultReceiver` after StartCapturing.
- Optimized the error handling when `InitLicense` with offline license.

### Fixed

- Small fixes and tweaks.

### Changed

- Changed the upper limit to the `DuplicateForgetTime`, which is 3 minutes.
- Changed the timing of `OnOriginalImageResultReceived` so that it is triggered immediately after receiving the image.
- Changed the constructors of the following classes from public to protected.
  - `CImageTag`
  - `CCapturedResultReceiver`
  - `CCapturedResultFilter`
  - `CImageSourceAdapter`
  - `CProactiveImageSourceAdapter`
  - `CIntermediateResultUnit`
  - `CIntermediateResultReceiver`
- Removed `BF_PATCH_CODE` from the combined value of `BF_DEFAULT` as decoding `Patch Code` is not supported by default.
- Removed const modifiers of all callback methods of class `CCapturedResultReceiver` and class `CIntermediateResultReceiver`.

## 10.0.10 (08/08/2023)

### New

- Added a new class `CVector4` in the core module.
- Added new methods `SetTransformMatrix` and `GetTransformMatrix` to the class `CIntermediateResultUnit`. Enumeration `TransformMatrixType` is also added to support users specifying the type of the target matrix.
- Added `CRIT_NORMALIZED_IMAGE` to the available result types of result cross-verification.
- Added method `GetContours` to the class `CContourUnit` to get all the `CContour` objects contained in the unit and their hierarchies.

### Improved

- Improved the implementation of the StopCapturing method to prevent deadlock when invoked in the management thread.
  
### Fixed

- Fixed a bug where the local license is not successfully updated in some cases.
- Fixed crash bugs that happen in rare cases.
- Other small fixes and tweaks.

### Changed

- Renamed methods `GetCount` to `GetItemsCount`. This change applies to the following classes:
  - `CCapturedResult`
  - `CDecodedBarcodesResult`
- Renamed method `GetSourceImageHashId` to `GetOriginalImageHashId`. This change applies to the following classes:
  - `CIntermediateResultUnit`
  - `CCapturedResult`
  - `CDecodedBarcodesResult`
- Renamed method `GetSourceImageTag` to `GetOriginalImageTag`. This change applies to the following classes:
  - `CIntermediateResultUnit`
  - `CCapturedResult`
  - `CDecodedBarcodesResult`
- Renamed method `OnRawImageResultReceived` to `OnOriginalImageResultReceived`. This change applies to the following classes:
  - `CapturedResultReceiver`
  - `CapturedResultFilter`
- Renamed a method of `CIntermediateResultManager` from `GetRawImage` to `GetOriginalImage`.
- Renamed the class `CRawImageResultItem` to `COriginalImageResultItem`.
- Renamed an enumeration member of `CapturedResultItemType` from `CRIT_RAW_IMAGE` to `CRIT_ORIGINAL_IMAGE`.
- Renamed an enumeration member of `BufferOverflowProtectionMode` from `BOPM_APPEND` to `BOPM_UPDATE`.
- Renamed the following methods of class `CMultiFrameResultCrossFilter`:
  - from `EnableResultVerification` to `EnableResultCrossVerification`.
  - from `isResultVerificationEnable` to `isResultCrossVerificationEnabled`.
  - from `EnableDuplicateFilter` to `EnableResultDeduplication`.
  - from `isDuplicateFilterEnabled` to `isResultDeduplicationEnabled`.
- Renamed the enumeration `TargetType`  to `RasterDataSource`.

### Removed

- Removed methods `SetLocalToSourceImageTransformMatrix` and `GetLocalToSourceImageTransformMatrix` from class `CIntermediateResultUnit`.
- Removed methods `SetRotationTransformMatrix` and `GetRotationTransformMatrix` from class `CIntermediateResultUnit`.
- Removed methods `GetCount` and `GetContour` from class `CContourUnit`. Use the method `GetContours` instead.

## 10.0.0 (07/04/2023)

### Highlights

`DynamsoftBarcodeReader` SDK has been revamped to integrate with `DynamsoftCaptureVision (DCV)` architecture, which is newly established to aggregate the features of functional products powered by Dynamsoft. The features are designed to be pluggable, customizable and interactable. In addition, the functional products share the computation so that their processing speed is much higher than working individually.

* `DynamsoftCaptureVision` architecture consists of:
  * `ImageSourceAdapter(ISA)`, the standard input interface for you to convert image data from different sources into the standard input image data. In addition, `ISA` incorporates an image buffer management system that allows instant access to the buffered image data.
  * `CaptureVisionRouter (CVR)`, an engine for you to update templates, retrieve images from `ISA`, coordinate corresponding functional products and dispatch the results to the receivers.
  * Functional products that perform image processing, content understanding and semantic processing. The functional products are pluggable and passively called by CVR when they are required.
  * Result receiver interfaces. You can implement `CapturedResultReceiver (CRR)` to receive the `CapturedResults` that output when the processing on an image is finalized. You can also implement `IntermediateResultReceiver (IRR)` to get timely results from different stages of the workflow.
* The parameter template system has been comprehensively upgraded.
  * Multiple algorithm task settings are available. You can define barcode decoding, label recognizing, document scanning and semantic processing tasks in one template file.
  * Extended the feature of the ROI system. By configuring the `target ROI` parameters, you can not only specify an `ROI` on the original image but also define the dependencies of the algorithm tasks. This feature enables you to customize the workflow when processing complex scenarios.
  * The image processing parameters are separated from the task parameters so that the template settings become more clear and concise.
* The `intermediate result` system has been improved.
  * Achieved the `intermediate result` sharing between different functional products. The results that have the same image source and processing parameters are directly reused, which speeds up the image processing workflow. You don’t need to add any additional code to enable the `intermediate result` sharing. The library can recognize all the reusable results automatically based on the template file you uploaded.
  * The readability and interactivity of the `intermediate results` are enhanced. `IntermediateResultReceiver` allows you to receive up to 27 different types of `Intermediate results`. You can clearly read which stage of the algorithm each result is output from. In addition, `IntermediateResultManager` allows you to intervene in the workflows by modifying the `intermediate results`.