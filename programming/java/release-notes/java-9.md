---
layout: default-layout
title: Release Notes v9.x - Dynamsoft Barcode Reader SDK Java Edition
description: This is the release notes page of Dynamsoft Barcode Reader SDK Java Edition v9.x.
keywords: release notes, java
needGenerateH3Content: false
---

# Release Notes for Java Edition - 9.x

## 9.6.10 (01/10/2023)

### New

- Added support for Python 3.11.
- Added a new method [`setLicenseCachePath`]({{site.java_methods}}license.html#setlicensecachepath) in the `BarcodeReader` class to support customizing the license cache saving path.
- Add a new method [`getDeviceUUID`]({{site.java_methods}}license.html#getdeviceuuid) in the `BarcodeReader` class to support getting device UUID for license activating.
- Added error code `DMERR_LICENSE_BUFFER_FAILED` to the potential error list of the license activation methods and decode methods. The error code is returned when the directory of the license cache is inaccessible.

### Improved

- Improved the performance of Direct Part Marking (DPM) barcode decoding.
- Improved the performance of GS1 Databar barcode decoding.

### Fixed

- Fixed a crash bug when using a online license key on ARM64 environment.
- Fixed a crash bug when using a online license key on the AWS lambda environment.
- Fixed a bug that some OneD barcodes without start & stop characters are not decoded when parameter [`RequireStartStopChars`]({{site.parameters_reference}}require-start-stop-chars.html) is set to 0.
- Other small fixes and tweaks.

## 9.6.0 (11/29/2022)

<div class="fold-panel-prefix"></div>

### Version Highlights <i class="fa fa-caret-down"></i>

<div class="fold-panel-start"></div>

{%- include release-notes/product-highlight-9.6.0.md -%}

<div class="fold-panel-end"></div>

### Edition Highlights

- Added duplicate barcode filter feature in video mode. You can implement duplicate filter to ignore duplicate barcodes for a period.

### Changelog

#### New

- Added a property [`orientation`]({{ site.java_class }}FrameDecodingParameters.html#orientation) to class `FrameDecodingParameters` to set the orientation information of the video frame.
- Added [`orientation`]({{ site.java_class }}ImageData.html#orientation) to class ImageData to set the orientation information.
- Enabled decoding methods `decodeFile()`, `decodeFileinMemory()` and `decodeBase64String()` to read EXIF data of the given image so that the library can obtain the orientation information of the image file.
- Added a override method [`decodeBuffer()`]({{site.java_methods}}decode.html#decodebuffer) with a new parameter `orientation` to set the orientation information of the image data.
- Added a property [`transformationMatrix`]({{ site.java_class }}LocalizationResult.html##transformationmatrix) to class `LocalizationResult` so that the library can output a transformation matrix for transforming the localization coordinates to image's natural orientation.
- Added a method [`transformCoordinates()`]({{site.java_methods}}general.html#transformcoordinates) to support transforming the coordinates of a point based on a given transformation matrix.
- Added a property [`duplicateForgetTime`]({{ site.java_class }}FrameDecodingParameters.html#duplicateforgettime) to class `FrameDecodingParameters` to set the time period used to filter out duplicate results found in frames.
- Added a callback method [`uniqueBarcodeCallback()`]({{site.java_api}}interface.html#uniqueBarcodeCallback) to interface `TextResultCallback` which will be triggered when the library finishes decoding a frame and finds unique barcodes.
- Added properties [`hasLeftRowIndicator`]({{ site.java_class }}PDF417Details.html#hasleftrowindicator) and [`hasRightRowIndicator`]({{ site.java_class }}PDF417Details.html#hasrightrowindicator) to class `PDF417Details` to return whether the left and right row indicator of the PDF417 barcode is detected.
- Added a member `BF2_ALL` to enumeration [`BarcodeFormatIds_2`]({{ site.java_enumerations }}format-enums.html#barcodeformat_2) to support setting all barcode formats in BarcodeFormat group 2 with one enumeration.
- Extended the features of parameter `DeformationResistingModes`:
  - Extended the valid mode arguments of `DRM_BROAD_WARP`, `DRM_LOCAL_REFERENCE` and `DRM_DEWRINKLE` with two new arguments: [`GrayscaleEnhancementMode`]({{site.parameters_reference}}deformation-resisting-modes.html#grayscaleenhancementmode) and [`BinarizationMode`]({{site.parameters_reference}}deformation-resisting-modes.html#binarizationmode).
  - Supported mode [`DRM_AUTO`]({{site.parameters_reference}}deformation-resisting-modes.html#drm_auto).

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

{%- include release-notes/product-highlight-9.4.0.md -%}

### Changelog

#### New

- Added an argument [`IsOneDStacked`]({{site.parameters_reference}}localization-modes.html#isonedstacked) to `LM_SCAN_DIRECTLY` to process stacked OneD barcodes.
- Added a parameter [`PatchCodeSearchingMargins`]({{site.parameters_reference}}patchcode-searching-margins.html) to specify the searching area of PatchCode.
- Added the supported data format of [`FormatSpecification.PartitionModes`]({{site.parameters_reference}}partition-modes.html) to enhance the readability of the parameters. Users can use a list of enumeration names to specify the `PartitionModes`.

#### Improved

- Improved the localization mode `LM_LINES` to better support skewed and perspective OneD barcodes.
- Enhanced tamper resistance of the license keys so that any change to the license string makes it invalid.

#### Deprecated

- Deprecated the attribute `barcodeFormatString_2` of [`TextResult`]({{site.java_class}}TextResult.html#barcodeformatstring_2), [`ExtendedResult`]({{site.java_class}}ExtendedResult.html#barcodeformatstring_2) and [`LocalizationResult`]({{site.java_class}}LocalizationResult.html#barcodeformatstring_2). All the barcode format strings will be returned by the attribute `barcodeFormatString`.

## 9.2.0 (06/07/2022)

<div class="fold-panel-prefix"></div>

### Version Highlights <i class="fa fa-caret-down"></i>

<div class="fold-panel-start"></div>

{%- include release-notes/product-highlight-9.2.0.md -%}

<div class="fold-panel-end"></div>

### Edition Highlights

- Added macOS ARM64 support to the Java edition of the SDK.

### Changelog

#### New

- Added a new method [`setDeviceFriendlyName`]({{site.java_methods}}license.html#setdevicefriendlyname) to set a human-readable name that identifies the device.

## 9.0.0 (03/15/2022)

<div class="fold-panel-prefix"></div>

### Version Highlights <i class="fa fa-caret-down"></i>

<div class="fold-panel-start"></div>

{%- include release-notes/product-highlight-9.0.0.md -%}

<div class="fold-panel-end"></div>

### Edition Highlights

- Added ARM64 Linux support to the Java edition of the SDK. In previous versions, Java Edition supported Windows x32/x64, macOS x64, and Linux x64.

### Changelog

#### New

- Added `BF_CODE_11` under Enumeration [`EnumBarcodeFormat`]({{ site.java_enumerations }}format-enums.html#barcodeformat) to specify newly supported barcode format, Code 11. 
- Added `BF2_PHARMACODE_ONE_TRACK`, `BF2_PHARMACODE_TWO_TRACK` and `BF2_PHARMACODE` under Enumeration [`EnumBarcodeFormat_2`]({{ site.java_enumerations }}format-enums.html#barcodeformat_2) to specify newly supported barcode format, Pharmacode. 
- Added a new error code [`DBRERR_PHARMACODE_LICENSE_INVALID`]({{ site.java_enumerations }}error-code.html#error-code--10062) which will be returned when the license of Pharmacode is invalid.
- Added `DRM_BROAD_WARP`, `DRM_LOCAL_REFERENCE` and `DRM_DEWRINKLE` under Enumeration [`EnumDeformationResistingMode`]({{ site.java_enumerations }}parameter-mode-enums.html#deformationresistingmode) to apply new deformation resisting modes.
- Added a parameter [`FormatSpecification.PartitionModes`]({{ site.parameters_reference }}partition-modes.html)
- Added a parameter [`FormatSpecification.VerifyCheckDigit`]({{ site.parameters_reference }}verify-check-digit.html)
- Added an Argument [`ConfidenceThreshold`]({{ site.parameters_reference }}localization-modes.html#confidencethreshold) to the `LocalizationModes` mode arguments.

#### Changed

- Changed method [`InitLicense`]({{ site.java_methods }}license.html#initlicense) to a static method.
- Changed value of BF_ONED under Enumeration [`EnumBarcodeFormat`]({{ site.java_enumerations }}format-enums.html#barcodeformat) to 0x003007FF to have BF_CODE_11 combined.
- Changed value of BF_ALL under Enumeration [`EnumBarcodeFormat`]({{ site.java_enumerations }}format-enums.html#barcodeformat) to 0xFE3FFFFF to have BF_CODE_11 combined.
- Changed the behaviour of [`DeformationResistingMode`]({{ site.java_enumerations }}parameter-mode-enums.html#deformationresistingmode) DRM_GENERAL which now only applies basic process to resist deformation.
- Changed the return value of the method [getIdleInstancesCount]({{ site.java_methods }}license.html#getidleinstancescount) from 0 to -1 when the available count needs to be updated from server by calling initLicense.


#### Fixed
- Fixed a bug that might cause a crash when using multiple threads for barcode decoding.
- Fixed a bug that throws exceptions when using method [getIdleInstancesCount]({{ site.java_methods }}license.html#getidleinstancescount).
- Fixed a bug that Function Code 1 (FNC1) character would not return if it was in the first position of GS1-128 codes.
- Other small fixes and tweaks.


#### Deprecated

The following items are now deprecated. They still work in this version but could be removed in the near future.
- Method [`initLicenseFromServer`]({{ site.java_methods }}license.html#initlicensefromserver)
- Method [`initLicenseFromLicenseContent`]({{ site.java_methods }}license.html#initlicensefromlicensecontent)
- Method [`outputLicenseToString`]({{ site.java_methods }}license.html#outputlicensetostring)
- Method [`initDLSConnectionParameters`]({{ site.java_methods }}license.html#initdlsconnectionparameters)
- Method [`initLicenseFromDLS`]({{ site.java_methods }}license.html#initlicensefromdls)
- Enumeration [`EnumDMChargeWay`]({{ site.java_enumerations }}other-enums.html#dm_chargeway)
- Enumeration [`EnumDMDeploymentType`]({{ site.java_enumerations }}other-enums.html#dm_deploymenttype)
- Enumeration [`EnumDMLicenseModule`]({{ site.java_enumerations }}other-enums.html#dm_licensemodule)
- Enumeration [`EnumDMUUIDGenerationMethod`]({{ site.java_enumerations }}other-enums.html#dm_uuidgenerationmethod)
- Enumeration [`EnumProduct`]({{ site.java_enumerations }}other-enums.html#product)


