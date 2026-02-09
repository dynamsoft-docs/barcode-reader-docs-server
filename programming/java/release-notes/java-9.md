---
layout: default-layout
title: Release Notes v9.x - Dynamsoft Barcode Reader SDK Java Edition
description: This is the release notes page of Dynamsoft Barcode Reader SDK Java Edition v9.x.
keywords: release notes, java
needGenerateH3Content: false
---

# Release Notes for Java Edition - 9.x

## 9.6.60 (12/23/2025)

### Security Updates

- Updated third-party libraries to incorporate the latest security fixes.

## 9.6.40 (03/14/2024)

### Improved

- Updated the security of the DynamsoftBarcodeReader library and other corresponding dependent libraries.
- Improved the multi-thread processing logic of concurrent instance licenses.
- Improved the barcode decoding performance:
  - Improved the accuracy when decoding OneD & PDF417 barcodes.
  - Improved the readability of dense DataMatrix codes.

### Fixed

- Fixed crash bugs in the barcode decoding algorithm.
- Fixed a bug where the location of the barcode result(s) might be incorrect.

### Changed

- Changed the error message of error `DBR_PDF_DLL_MISSING` from "The PDF DLL is missing" to "The PDF library could not be loaded".
- Added a new error code `DM_LICENSE_CACHE_USED`, which is returned when failing to connect to the license server but a valid license cache is available. Error codes  `DM_FAILED_TO_REACH_DLS` and `DM_LICENSE_SYNC_FAILED` are no longer returned on this scenario.

## 9.6.30 (08/29/2023)

### New

- Added a new method `getInstancePoolStatus` and class `InstancePoolStatus` to provide a real-time view of how the concurrent instance licenses are being utilized. This applies only if you are using a concurrent instance license.

### Improved

- Optimized the concurrent instance management and license usage statistics when using a concurrent instance license.
- Extended the availability of methods `GetInstance` and `Recycle`, making them accessible to all licensing modes.
- Implemented additional checkpoints to ensure timely timeout and termination.

### Fixed

- Fixed a bug where barcode results varied depending on the operating system being used.
- Fixed a crash bug when initializing a license with a segmented license string.
- Fixed some bugs related to the barcode format settings when they are defined in the `RegionDefinition` object of the template.

## 9.6.20 (03/16/2023)

### Fixed

- Fixed a bug where the methods initLicense and gGetInstance may not work as expected when using concurrent instance license.
- Fixed a bug where license authorization may fail when the main license server is not available.
- Other small fixes and tweaks.

## 9.6.10 (01/10/2023)

### New

- Added a new method `setLicenseCachePath` in the `BarcodeReader` class to support customizing the license cache saving path.
- Add a new method `getDeviceUUID` in the `BarcodeReader` class to support getting device UUID for license activating.
- Added error code `DM_LICENSE_BUFFER_FAILED` to the potential error list of the license activation methods and decode methods. The error code is returned when the directory of the license cache is inaccessible.

### Improved

- Improved the performance of Direct Part Marking (DPM) barcode decoding.
- Improved the performance of GS1 Databar barcode decoding.

### Fixed

- Fixed a crash bug when using a online license key on ARM64 environment.
- Fixed a crash bug when using a online license key on the AWS lambda environment.
- Fixed a bug that some OneD barcodes without start & stop characters are not decoded when parameter `RequireStartStopChars` is set to 0.
- Other small fixes and tweaks.

## 9.6.0 (11/29/2022)

### Version Highlights

- **Image orientation** handling is supported by a new feature. With the new feature, you can:
  - Get a **TranformationMatrix** along with the barcode location result.
  - Implement coordinates transformation on the barcode location result with the **TransformationMatrix**.
- **DotCode** decoding is improved by optimizing the localization of DotCodes that are close to one another.
- **EAN8 barcode** decoding is improved by honing the accuracy of localization algorithms.
- **QR code** localizing is improved by reducing the mis-assemble rate of the finder patterns when using the localization mode LM_CONNECTED_BLOCK or LM_SCAN_DIRECTLY, which are designed for speed. The mis-assembling only occurs when there exist dense QR codes on the same image.
- **Mirrored rectangular DataMatrix barcode** is supported by implementing `MirrorMode` when localizing the barcodes.
- Deformed barcode decoding is improved by extending the supported modes and mode arguments of `DeformationResistingModes`.

### Edition Highlights

- Added duplicate barcode filter feature in video mode. You can implement duplicate filter to ignore duplicate barcodes for a period.

### Changelog

#### New

- Added a property `orientation` to class `FrameDecodingParameters` to set the orientation information of the video frame.
- Added `orientation` to class ImageData to set the orientation information.
- Enabled decoding methods `decodeFile()`, `decodeFileinMemory()` and `decodeBase64String()` to read EXIF data of the given image so that the library can obtain the orientation information of the image file.
- Overloaded method `decodeBuffer()` with a new parameter `orientation` to set the orientation information of the image data.
- Added a property `transformationMatrix` to class `LocalizationResult` so that the library can output a transformation matrix for transforming the localization coordinates to image's natural orientation.
- Added a method `transformCoordinates()` to support transforming the coordinates of a point based on a given transformation matrix.
- Added a property `duplicateForgetTime` to class `FrameDecodingParameters` to set the time period used to filter out duplicate results found in frames.
- Added a callback method `uniqueBarcodeCallback()` to interface `TextResultCallback` which will be triggered when the library finishes decoding a frame and finds unique barcodes.
- Added properties `hasLeftRowIndicator` and `hasRightRowIndicator` to class `PDF417Details` to return whether the left and right row indicator of the PDF417 barcode is detected.
- Added a member `BF2_ALL` to enumeration `BarcodeFormatIds_2` to support setting all barcode formats in BarcodeFormat group 2 with one enumeration.
- Extended the features of parameter `DeformationResistingModes`:
  - Extended the valid mode arguments of `DRM_BROAD_WARP`, `DRM_LOCAL_REFERENCE` and `DRM_DEWRINKLE` with two new arguments: `GrayscaleEnhancementMode` and `BinarizationMode`.
  - Supported mode `DRM_AUTO`.

#### Improved

- Improved the accuracy when processing multiple QR codes.
- Improved the processing speed by excluding incorrectly located barcode zones before decoding.
- Improved the creation, destruction and acquisition logic of concurrent instances.
- Improved the accuracy of EAN8 localization result(s).
- Improved the localization of mirrored DataMatrix barcode by implementing `MirrorMode`.

#### Fixed

- Fixed a bug that DotCodes might not be decoded when they are densely arranged.
- Fixed a crash bug when trying to output a template which included `BarcodeTextRegExPattern`.
- Other small fixes and tweaks.

## 9.4.0 (08/30/2022)

### Highlights

- **DotCode** decoding has been improved by optimizing the localization and decoding algorithm.
- **Stacked**, **skewed** or **perspective distorted OneD barcode** decoding has been improved.

### Changelog

#### New

- Added an argument `IsOneDStacked` to `LM_SCAN_DIRECTLY` to process stacked OneD barcodes.
- Added a parameter `PatchCodeSearchingMargins` to specify the searching area of PatchCode.
- Added the supported data format of `FormatSpecification.PartitionModes` to enhance the readability of the parameters. Users can use a list of enumeration names to specify the `PartitionModes`.

#### Improved

- Improved the localization mode `LM_LINES` to better support skewed and perspective OneD barcodes.
- Enhanced tamper resistance of the license keys so that any change to the license string makes it invalid.

#### Deprecated

- Deprecated the attribute `barcodeFormatString_2` of `TextResult`, `ExtendedResult` and `LocalizationResult`. All the barcode format strings will be returned by the attribute `barcodeFormatString`.

## 9.2.0 (06/07/2022)

### Version Highlights

- Barcode boundary-seeking algorithm is refactored to improve stability.
- Pharmacode decoding is optimized to improve accuracy.
- The function of device-alias is added to allow users to give each device a readable name. For end-users and administrators, this makes it more friendly to distinguish between devices about license usage statistics.

### Edition Highlights

- Added macOS ARM64 support to the Java edition of the SDK.

### Changelog

#### New

- Added a new method `setDeviceFriendlyName` to set a human-readable name that identifies the device.

## 9.0.0 (03/15/2022)

### Version Highlights

- Simplified the license activation steps. Different license activation APIs are integrated into `initLicense` method.
- Added support for **Pharmacode**.
- Added support for **Code 11**, a 1D format.
- Deformation resisting modes `DRM_BROAD_WARP`, `DRM_LOCAL_REFERENCE` and `DRM_DEWRINKLE` are optimized and detached from `DRM_GENERAL`. Users can specify a more effective deformation resisting mode when processing **QRCode** and **DataMatrix codes**.
- Optimized the confidence scoring system for **PDF417 codes**.

### Edition Highlights

- Added ARM64 Linux support to the Java edition of the SDK. In previous versions, Java Edition supported Windows x32/x64, macOS x64, and Linux x64.

### Changelog

#### New

- Added `BF_CODE_11` under Enumeration `EnumBarcodeFormat` to specify newly supported barcode format, Code 11. 
- Added `BF2_PHARMACODE_ONE_TRACK`, `BF2_PHARMACODE_TWO_TRACK` and `BF2_PHARMACODE` under Enumeration `EnumBarcodeFormat_2` to specify newly supported barcode format, Pharmacode. 
- Added a new error code `DBR_PHARMACODE_LICENSE_INVALID` which will be returned when the license of Pharmacode is invalid.
- Added `DRM_BROAD_WARP`, `DRM_LOCAL_REFERENCE` and `DRM_DEWRINKLE` under Enumeration `EnumDeformationResistingMode` to apply new deformation resisting modes.
- Added a parameter `FormatSpecification.PartitionModes`
- Added a parameter `FormatSpecification.VerifyCheckDigit`
- Added an Argument `ConfidenceThreshold` to the `LocalizationModes` mode arguments.

#### Changed

- Changed method `InitLicense` to a static method.
- Changed value of BF_ONED under Enumeration `EnumBarcodeFormat` to 0x003007FF to have BF_CODE_11 combined.
- Changed value of BF_ALL under Enumeration `EnumBarcodeFormat` to 0xFE3FFFFF to have BF_CODE_11 combined.
- Changed the behaviour of `DeformationResistingMode` DRM_GENERAL which now only applies basic process to resist deformation.
- Changed the return value of the method `getIdleInstancesCount` from 0 to -1 when the available count needs to be updated from server by calling initLicense.


#### Fixed
- Fixed a bug that might cause a crash when using multiple threads for barcode decoding.
- Fixed a bug that throws exceptions when using method `getIdleInstancesCount`.
- Fixed a bug that Function Code 1 (FNC1) character would not return if it was in the first position of GS1-128 codes.
- Other small fixes and tweaks.


#### Deprecated

The following items are now deprecated. They still work in this version but could be removed in the near future.
- Method `initLicenseFromServer`
- Method `initLicenseFromLicenseContent`
- Method `outputLicenseToString`
- Method `initDLSConnectionParameters`
- Method `initLicenseFromDLS`
- Enumeration `EnumDMChargeWay`
- Enumeration `EnumDMDeploymentType`
- Enumeration `EnumDMLicenseModule`
- Enumeration `EnumDMUUIDGenerationMethod`
- Enumeration `EnumProduct`