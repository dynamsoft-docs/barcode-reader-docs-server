---
layout: default-layout
title: Dynamsoft Barcode Reader C++ API Reference - Main Page
description: This is the main page of Dynamsoft Barcode Reader SDK API Reference for C++ Language.
keywords: api reference, C++
needAutoGenerateSidebar: false
---

# API Reference - C++


## DynamsoftCaptureVisionRouter

### [CCaptureVisionRouter]({{ site.dcvb_cpp_api }}capture-vision-router/capture-vision-router.html)

- [`Constructor and Destructor`]({{ site.dcvb_cpp_api }}capture-vision-router/instantiate.html)
- [`Single-File Processing`]({{ site.dcvb_cpp_api }}capture-vision-router/single-file-processing.html)
- [`Multiple-File Processing`]({{ site.dcvb_cpp_api }}capture-vision-router/multiple-file-processing.html)
- [`Settings`]({{ site.dcvb_cpp_api }}capture-vision-router/settings.html)
- [`Intermediate Result`]({{ site.dcvb_cpp_api }}capture-vision-router/intermediate-result.html)
- [`Auxiliary Methods`]({{ site.dcvb_cpp_api }}capture-vision-router/auxiliary-methods.html)

### Classes

- [`CCaptureStateListener`]({{ site.dcvb_cpp_api }}capture-vision-router/auxiliary-classes/capture-state-listener.html)
- [`CCaptureVisionRouterModule`]({{ site.dcvb_cpp_api }}capture-vision-router/auxiliary-classes/capture-vision-router-module.html)
- [`CCapturedResult`]({{ site.dcvb_cpp_api }}capture-vision-router/auxiliary-classes/captured-result.html)
- [`CCapturedResultFilter`]({{ site.dcvb_cpp_api }}capture-vision-router/auxiliary-classes/captured-result-filter.html)
- [`CCapturedResultReceiver`]({{ site.dcvb_cpp_api }}capture-vision-router/auxiliary-classes/captured-result-receiver.html)
- [`CImageSourceStateListener`]({{ site.dcvb_cpp_api }}capture-vision-router/auxiliary-classes/image-source-state-listener.html)
- [`CIntermediateResultManager`]({{ site.dcvb_cpp_api }}capture-vision-router/auxiliary-classes/intermediate-result-manager.html)
- [`CIntermediateResultReceiver`]({{ site.dcvb_cpp_api }}capture-vision-router/auxiliary-classes/intermediate-result-receiver.html)
- [`CPresetTemplate`]({{ site.dcvb_cpp_api }}capture-vision-router/auxiliary-classes/preset-template.html)

### Structs

- [`SimplifiedCaptureVisionSettings`]({{ site.dcvb_cpp_api }}capture-vision-router/structs/simplified-capture-vision-settings.html)

### Enums

- [`CaptureState`]({{ site.dcvb_enumerations }}capture-vision-router/capture-state.html?lang=cpp)
- [`ImageSourceState`]({{ site.dcvb_enumerations }}capture-vision-router/image-source-state.html?lang=cpp)

## DynamsoftBarcodeReader

### Classes

- [`CAztecDetails`]({{ site.dbr_cpp_api }}aztec-details.html)
- [`CBarcodeDetails`]({{ site.dbr_cpp_api }}barcode-details.html)
- [`CBarcodeReaderModule`]({{ site.dbr_cpp_api }}barcode-reader-module.html)
- [`CBarcodeResultItem`]({{ site.dbr_cpp_api }}barcode-result-item.html)
- [`CCandidateBarcodeZonesUnit`]({{ site.dbr_cpp_api }}candidate-barcode-zones-unit.html)
- [`CComplementedBarcodeImageUnit`]({{ site.dbr_cpp_api }}complemented-barcode-image-unit.html)
- [`CDataMatrixDetails`]({{ site.dbr_cpp_api }}datamatrix-details.html)
- [`CDecodedBarcodeElement`]({{ site.dbr_cpp_api }}decoded-barcode-element.html)
- [`CDecodedBarcodesResult`]({{ site.dbr_cpp_api }}decoded-barcodes-result.html)
- [`CDecodedBarcodesUnit`]({{ site.dbr_cpp_api }}decoded-barcodes-unit.html)
- [`CDeformationResistedBarcodeImageUnit`]({{ site.dbr_cpp_api }}deformation-resisted-barcode-image-unit.html)
- [`CExtendedBarcodeResult`]({{ site.dbr_cpp_api }}extended-barcode-result.html)
- [`CLocalizedBarcodeElement`]({{ site.dbr_cpp_api }}localized-barcode-element.html)
- [`CLocalizedBarcodesUnit`]({{ site.dbr_cpp_api }}localized-barcodes-unit.html)
- [`COneDCodeDetails`]({{ site.dbr_cpp_api }}oned-code-details.html)
- [`CPDF417Details`]({{ site.dbr_cpp_api }}pdf417-details.html)
- [`CQRCodeDetails`]({{ site.dbr_cpp_api }}qr-code-details.html)
- [`CScaledUpBarcodeImageUnit`]({{ site.dbr_cpp_api }}scaled-up-barcode-image-unit.html)

### Structs

- [`SimplifiedBarcodeReaderSettings`]({{ site.dbr_cpp_api }}simplified-barcode-reader-settings.html)

### Enums

- [`BarcodeFormat`]({{ site.dcvb_enumerations }}barcode-reader/barcode-format.html?lang=cpp)
- [`DeblurMode`]({{ site.dcvb_enumerations }}barcode-reader/deblur-mode.html?lang=cpp)
- [`ExtendedBarcodeResultType`]({{ site.dcvb_enumerations }}barcode-reader/extended-barcode-result-type.html?lang=cpp)
- [`LocalizationMode`]({{ site.dcvb_enumerations }}barcode-reader/localization-mode.html?lang=cpp)
- [`QRCodeErrorCorrectionLevel`]({{ site.dcvb_enumerations }}barcode-reader/qr-code-error-correction-level.html?lang=cpp)

## DynamsoftCore

### Classes

- [`CAbstractIntermediateResultReceiver`]({{ site.dcvb_cpp_api }}core/intermediate-results/abstract-intermediate-result-receiver.html)
- [`CBinaryImageUnit`]({{ site.dcvb_cpp_api }}core/intermediate-results/binary-image-unit.html)
- [`CCapturedResultItem`]({{ site.dcvb_cpp_api }}core/basic-structures/captured-result-item.html)
- [`CColourImageUnit`]({{ site.dcvb_cpp_api }}core/intermediate-results/colour-image-unit.html)
- [`CContoursUnit`]({{ site.dcvb_cpp_api }}core/intermediate-results/contours-unit.html)
- [`CContour`]({{ site.dcvb_cpp_api }}core/basic-structures/contour.html)
- [`CCoreModule`]({{ site.dcvb_cpp_api }}core/basic-structures/core-module.html)
- [`CCorner`]({{ site.dcvb_cpp_api }}core/basic-structures/corner.html)
- [`CEdge`]({{ site.dcvb_cpp_api }}core/basic-structures/edge.html)
- [`CEnhancedGrayscaleImageUnit`]({{ site.dcvb_cpp_api }}core/intermediate-results/enhanced-grayscale-image-unit.html)
- [`CFileImageTag`]({{ site.dcvb_cpp_api }}core/basic-structures/file-image-tag.html)
- [`CGrayscaleImageUnit`]({{ site.dcvb_cpp_api }}core/intermediate-results/grayscale-image-unit.html)
- [`CImageData`]({{ site.dcvb_cpp_api }}core/basic-structures/image-data.html)
- [`CImageSourceAdapter`]({{ site.dcvb_cpp_api }}core/basic-structures/image-source-adapter.html)
- [`CImageSourceErrorListener`]({{ site.dcvb_cpp_api }}core/basic-structures/image-source-error-listener.html)
- [`CImageTag`]({{ site.dcvb_cpp_api }}core/basic-structures/image-tag.html)
- [`CIntermediateResultUnit`]({{ site.dcvb_cpp_api }}core/intermediate-results/intermediate-result-unit.html)
- [`CIntermediateResult`]({{ site.dcvb_cpp_api }}core/intermediate-results/intermediate-result.html)
- [`CLineSegmentsUnit`]({{ site.dcvb_cpp_api }}core/intermediate-results/line-segments-unit.html)
- [`CLineSegment`]({{ site.dcvb_cpp_api }}core/basic-structures/line-segment.html)
- [`CObservationParameters`]({{ site.dcvb_cpp_api }}core/intermediate-results/observed-parameters.html)
- [`COriginalImageResultItem`]({{ site.dcvb_cpp_api }}core/basic-structures/original-image-result-item.html)
- [`CPDFReadingParameter`]({{ site.dcvb_cpp_api }}core/basic-structures/pdf-reading-parameter.html)
- [`CPoint`]({{ site.dcvb_cpp_api }}core/basic-structures/point.html)
- [`CPredetectedRegionElement`]({{ site.dcvb_cpp_api }}core/intermediate-results/predetected-region-element.html)
- [`CPredetectedRegionsUnit`]({{ site.dcvb_cpp_api }}core/intermediate-results/predetected-regions-unit.html)
- [`CQuadrilateral`]({{ site.dcvb_cpp_api }}core/basic-structures/quadrilateral.html)
- [`CRect`]({{ site.dcvb_cpp_api }}core/basic-structures/rect.html)
- [`CRegionObjectElement`]({{ site.dcvb_cpp_api }}core/intermediate-results/region-object-element.html)
- [`CScaledDownColourImageUnit`]({{ site.dcvb_cpp_api }}core/intermediate-results/scaled-down-colour-image-unit.html)
- [`CShortLinesUnit`]({{ site.dcvb_cpp_api }}core/intermediate-results/short-lines-unit.html)
- [`CTextRemovedBinaryImageUnit`]({{ site.dcvb_cpp_api }}core/intermediate-results/text-removed-binary-image-unit.html)
- [`CTextZone`]({{ site.dcvb_cpp_api }}core/intermediate-results/text-zone.html)
- [`CTextZonesUnit`]({{ site.dcvb_cpp_api }}core/intermediate-results/text-zones-unit.html)
- [`CTextureDetectionResultUnit`]({{ site.dcvb_cpp_api }}core/intermediate-results/texture-detection-result-unit.html)
- [`CTextureRemovedBinaryImageUnit`]({{ site.dcvb_cpp_api }}core/intermediate-results/texture-removed-binary-image-unit.html)
- [`CTextureRemovedGrayscaleImageUnit`]({{ site.dcvb_cpp_api }}core/intermediate-results/texture-removed-grayscale-image-unit.html)
- [`CTransformedGrayscaleImageUnit`]({{ site.dcvb_cpp_api }}core/intermediate-results/transformed-grayscale-image-unit.html)
- [`CVector4`]({{ site.dcvb_cpp_api }}core/basic-structures/vector4.html)
- [`CVideoFrameTag`]({{ site.dcvb_cpp_api }}core/basic-structures/video-frame-tag.html)

### Structs

- [`IntermediateResultExtraInfo`]({{ site.dcvb_cpp_api }}core/structs/intermediate-result-extra-info.html)

### Enums

- [`BufferOverflowProtectionMode`]({{ site.dcvb_enumerations }}core/buffer-overflow-protection-mode.html?lang=cpp)
- [`CapturedResultItemType`]({{ site.dcvb_enumerations }}core/captured-result-item-type.html?lang=cpp)
- [`ColourChannelUsageType`]({{ site.dcvb_enumerations }}core/colour-channel-usage-type.html?lang=cpp)
- [`CornerType`]({{ site.dcvb_enumerations }}core/corner-type.html?lang=cpp)
- [`ErrorCode`]({{ site.dcvb_enumerations }}core/error-code.html?lang=cpp)
- [`GrayscaleEnhancementMode`]({{ site.dcvb_enumerations }}core/grayscale-enhancement-mode.html?lang=cpp)
- [`GrayscaleTransformationMode`]({{ site.dcvb_enumerations }}core/grayscale-transformation-mode.html?lang=cpp)
- [`ImageCaptureDistanceMode`]({{ site.dcvb_enumerations }}core/image-capture-distance-mode.html?lang=cpp)
- [`ImagePixelFormat`]({{ site.dcvb_enumerations }}core/image-pixel-format.html?lang=cpp)
- [`ImageTagType`]({{ site.dcvb_enumerations }}core/image-tag-type.html?lang=cpp)
- [`IntermediateResultUnitType`]({{ site.dcvb_enumerations }}core/intermediate-result-unit-type.html?lang=cpp)
- [`PDFReadingMode`]({{ site.dcvb_enumerations }}core/pdf-reading-mode.html?lang=cpp)                
- [`RasterDataSource`]({{ site.dcvb_enumerations }}core/raster-data-source.html?lang=cpp)
- [`RegionObjectElementType`]({{ site.dcvb_enumerations }}core/region-object-element-type.html?lang=cpp)
- [`SectionType`]({{ site.dcvb_enumerations }}core/section-type.html?lang=cpp)
- [`TargetType`]({{ site.dcvb_enumerations }}core/target-type.html?lang=cpp)
- [`VideoFrameQuality`]({{ site.dcvb_enumerations }}core/video-frame-quality.html?lang=cpp)

## DynamsoftUtility

- [`CDirectoryFetcher`]({{ site.dcvb_cpp_api }}utility/directory-fetcher.html)
- [`CFileFetcher`]({{ site.dcvb_cpp_api }}utility/file-fetcher.html)
- [`CImageManager`]({{ site.dcvb_cpp_api }}utility/image-manager.html)
- [`CMultiFrameResultCrossFilter`]({{ site.dcvb_cpp_api }}utility/multi-frame-result-cross-filter.html)
- [`CProactiveImageSourceAdapter`]({{ site.dcvb_cpp_api }}utility/proactive-image-source-adapter.html)
- [`CUtilityModule`]({{ site.dcvb_cpp_api }}utility/utility-module.html)

## DynamsoftLicense

- [`CLicenseManager`]({{ site.dcvb_cpp_api }}license/license-manager.html)
- [`CLicenseModule`]({{ site.dcvb_cpp_api }}license/license-module.html)


## DynamsoftImageProcessing

- [`CImageProcessingModule`]({{ site.dcvb_cpp_api }}image-processing/image-processing-module.html)

