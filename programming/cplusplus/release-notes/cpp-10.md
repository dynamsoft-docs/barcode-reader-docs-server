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

* Added a new class `CVector4` in the core module.
* Added new methods `SetTransformMatrix` and `GetTransformMatrix` to the class `CIntermediateResultUnit`. Enumeration `TransformMatrixType` is also added to support users specifying the type of the target matrix.
* Added `CRIT_NORMALIZED_IMAGE` to the available result types of result cross-verification.
* Added method `GetContours` to the class `CContourUnit` to get all the `CContour` objects contained in the unit and their hierarchies.

### Improved

* Improved the implementation of the StopCapturing method to prevent deadlock when invoked in the management thread.
  
### Fixed

* Fixed a bug where the local license is not successfully updated in some cases.
* Fixed crash bugs that happen in rare cases.
* Other small fixes and tweaks.

### Changed

* Renamed methods `GetCount` to `GetItemsCount`. This change applies to the following classes:
  * `CCapturedResult`
  * `CDecodedBarcodesResult`
* Renamed method `GetSourceImageHashId` to `GetOriginalImageHashId`. This change applies to the following classes:
  * `CIntermediateResultUnit`
  * `CCapturedResult`
  * `CDecodedBarcodesResult`
* Renamed method `GetSourceImageTag` to `GetOriginalImageTag`. This change applies to the following classes:
  * `CIntermediateResultUnit`
  * `CCapturedResult`
  * `CDecodedBarcodesResult`
* Renamed method `OnRawImageResultReceived` to `OnOriginalImageResultReceived`. This change applies to the following classes:
  * `CapturedResultReceiver`
  * `CapturedResultFilter`
* Renamed a method of `CIntermediateResultManager` from `GetRawImage` to `GetOriginalImage`.
* Renamed the class `CRawImageResultItem` to `COriginalImageResultItem`.
* Renamed an enumeration member of `CapturedResultItemType` from `CRIT_RAW_IMAGE` to `CRIT_ORIGINAL_IMAGE`.
* Renamed an enumeration member of `BufferOverflowProtectionMode` from `BOPM_APPEND` to `BOPM_UPDATE`.
* Renamed the following methods of class `CMultiFrameResultCrossFilter`:
  * from `EnableResultVerification` to `EnableResultCrossVerification`.
  * from `isResultVerificationEnable` to `isResultCrossVerificationEnabled`.
  * from `EnableDuplicateFilter ` to `EnableResultDeduplication`.
  * from `isDuplicateFilterEnabled` to `isResultDeduplicationEnabled`.
* Renamed the enumeration `TargetType`  to `RasterDataSource`.


### Removed

* Removed methods `SetLocalToSourceImageTransformMatrix` and `GetLocalToSourceImageTransformMatrix` from class `CIntermediateResultUnit`.
* Removed methods `SetRotationTransformMatrix` and `GetRotationTransformMatrix` from class `CIntermediateResultUnit`.
* Removed methods `GetCount` and `GetContour` from class `CContourUnit`. Use the method `GetContours` instead.

## 10.0.0 (07/04/2023)

### Highlights

{%- include release-notes/product-highlight-10.0.0.md -%}


