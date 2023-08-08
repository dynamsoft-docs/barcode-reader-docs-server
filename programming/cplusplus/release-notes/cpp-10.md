---
layout: default-layout
title: Release Notes v10.x - Dynamsoft Barcode Reader SDK C++ Edition
description: This is the release notes page of Dynamsoft Barcode Reader SDK C++ Edition v10.x.
keywords: release notes, c++
needGenerateH3Content: false
permalink: /programming/cplusplus/release-notes/cpp-10.html
---

# Release Notes for C++ Edition - 10.x

## 10.0.10 (08/08/2023)

### New

* Added a new class CVector4 in the core module.
* Added new methods `SetTransformMatrix` and `GetTransformMatrix` to the class `CIntermediateResultUnit`. Enumeration `TransformMatrixType` is also added to support users specifying the type of the target matrix.
* Added enumeration `RasterDataSource` to specify the raster data source when reading PDF files. The previous enumeration `TargetType` is removed. The attribute `TargetType type` of Class `CPDFReadingParameter` is replaced by `RasterDataSource rasterDataSource`. 
* Added `CRIT_NORMALIZED_IMAGE` to the available result types of result cross-verification.
* Added method `GetContours` to the `CContourUnit` class to get all the `CContour` objects contained in the unit and their hierarchies.

### Improved

* Improved the implementation of the StopCapturing method to prevent deadlock when invoked in the management thread.
  
### Fixed

* Fixed a bug where the local license is not successfully updated when initialing the license again.
* Fixed crash bugs that happen in rare cases.
* Other small fixes and tweaks.

### Changed

* Renamed method `GetRawImage` to `GetOriginalImage`.
* Renamed method `GetSourceImageHashId` to `GetOriginalImageHashId`. This change is applied to the following classes:
  * `CIntermediateResultUnit`
  * `CCapturedResult`
  * `CDecodedBarcodesResult`
  * `CRecognizedTextLinesResult`
  * `CNormalizedImagesResult`
  * `CDetectedQuadsResult`
  * `CParsedResult`
* Renamed method `GetSourceImageTag` to `GetOriginalImageTag`. This change is applied to the following classes:
  * `CIntermediateResultUnit`
  * `CCapturedResult`
  * `CDecodedBarcodesResult`
  * `CRecognizedTextLinesResult`
  * `CNormalizedImagesResult`
  * `CDetectedQuadsResult`
  * `CParsedResult`
* Renamed methods `GetCount` to `GetItemsCount`. This change is applied to the following classes:
  * `CCapturedResult`
  * `CDecodedBarcodesResult`
  * `CRecognizedTextLinesResult`
  * `CNormalizedImagesResult`
  * `CDetectedQuadsResult`
  * `CParsedResult`	
* Renamed an enumeration member of `CapturedResultItemType` from `CRIT_RAW_IMAGE` to `CRIT_ORIGINAL_IMAGE`.
* Renamed a method of `CapturedResultReceiver` from `OnRawImageResultReceived` to `OnOriginalImageResultReceived`.
* Renamed a method of `CapturedResultFilter` from `OnRawImageResultReceived` to `OnOriginalImageResultReceived`.
* Renamed the class `CRawImageResultItem` to `COriginalImageResultItem`.
* Renamed an enumeration member of `BufferOverflowProtectionMode` from `BOPM_APPEND` to `BOPM_UPDATE`.
* The following methods are renamed:
  * Renamed `EnableResultVerification` to `EnableResultCrossVerification`.
  * Renamed `isResultVerificationEnable` to `isResultCrossVerificationEnabled`.
  * Renamed `EnableDuplicateFilter ` to `EnableResultDeduplication`.
  * Renamed `isDuplicateFilterEnabled` to `isResultDeduplicationEnabled`.
* Renamed parameter `CornerAngleRangeArray` to `CornerAngleRange`. The range of the subparameter `MinValue` is restricted to [0,90] and the range of `MaxValue` is restricted to [90,180].

### Removed

* Removed `Set/GetLocalToSourceImageTransformMatrix` methods from `CIntermediateResultUnit` class.
* Removed `Set/GetRotationTransformMatrix` methods from `CIntermediateResultUnit` class.
* Removed methods `GetCount` and `GetContour` from CContourUnit class. Use the method `GetContours` instead.

#### Deprecated

## 10.0.0 (07/04/2023)

### Highlights

{%- include release-notes/product-highlight-10.0.0.md -%}


