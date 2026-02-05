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

- [`CaptureState`]({{ site.dcvb_cpp_api }}capture-vision-router/enum-capture-state.html?lang=cpp)
- [`ImageSourceState`]({{ site.dcvb_cpp_api }}capture-vision-router/enum-image-source-state.html?lang=cpp)

## DynamsoftBarcodeReader

### Classes

- [`CAztecDetails`]({{ site.dbr_cpp_api }}aztec-details.html)
- [`CBarcodeDetails`]({{ site.dbr_cpp_api }}barcode-details.html)
- [`CBarcodeReaderModule`]({{ site.dbr_cpp_api }}barcode-reader-module.html)
- [`CBarcodeResultItem`]({{ site.dbr_cpp_api }}barcode-result-item.html)
- [`CCandidateBarcodeZone`]({{ site.dbr_cpp_api }}candidate-barcode-zone.html)
- [`CCandidateBarcodeZonesUnit`]({{ site.dbr_cpp_api }}candidate-barcode-zones-unit.html)
- [`CComplementedBarcodeImageUnit`]({{ site.dbr_cpp_api }}complemented-barcode-image-unit.html)
- [`CDataMatrixDetails`]({{ site.dbr_cpp_api }}datamatrix-details.html)
- [`CDecodedBarcodeElement`]({{ site.dbr_cpp_api }}decoded-barcode-element.html)
- [`CDecodedBarcodesResult`]({{ site.dbr_cpp_api }}decoded-barcodes-result.html)
- [`CDecodedBarcodesUnit`]({{ site.dbr_cpp_api }}decoded-barcodes-unit.html)
- [`CDeformationResistedBarcode`]({{ site.dbr_cpp_api }}deformation-resisted-barcode.html)
- [`CDeformationResistedBarcodeImageUnit`]({{ site.dbr_cpp_api }}deformation-resisted-barcode-image-unit.html)
- [`CECISegment`]({{ site.dbr_cpp_api }}eci-segment.html)
- [`CExtendedBarcodeResult`]({{ site.dbr_cpp_api }}extended-barcode-result.html)
- [`CLocalizedBarcodeElement`]({{ site.dbr_cpp_api }}localized-barcode-element.html)
- [`CLocalizedBarcodesUnit`]({{ site.dbr_cpp_api }}localized-barcodes-unit.html)
- [`COneDCodeDetails`]({{ site.dbr_cpp_api }}oned-code-details.html)
- [`CPDF417Details`]({{ site.dbr_cpp_api }}pdf417-details.html)
- [`CQRCodeDetails`]({{ site.dbr_cpp_api }}qr-code-details.html)
- [`CScaledBarcodeImageUnit`]({{ site.dbr_cpp_api }}scaled-barcode-image-unit.html)

### Structs

- [`SimplifiedBarcodeReaderSettings`]({{ site.dbr_cpp_api }}simplified-barcode-reader-settings.html)

### Enums

- [`BarcodeFormat`]({{ site.dbr_cpp_api }}enum-barcode-format.html?lang=cpp)
- [`DeblurMode`]({{ site.dbr_cpp_api }}enum-deblur-mode.html?lang=cpp)
- [`ExtendedBarcodeResultType`]({{ site.dbr_cpp_api }}enum-extended-barcode-result-type.html?lang=cpp)
- [`LocalizationMode`]({{ site.dbr_cpp_api }}enum-localization-mode.html?lang=cpp)
- [`QRCodeErrorCorrectionLevel`]({{ site.dbr_cpp_api }}enum-qr-code-error-correction-level.html?lang=cpp)

## DynamsoftCore

### Classes

- [`CAbstractIntermediateResultReceiver`]({{ site.dcvb_cpp_api }}core/intermediate-results/abstract-intermediate-result-receiver.html)
- [`CBinaryImageUnit`]({{ site.dcvb_cpp_api }}core/intermediate-results/binary-image-unit.html)
- [`CCapturedResultBase`]({{ site.dcvb_cpp_api }}core/basic-structures/captured-result-base.html)
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
- [`CScaledColourImageUnit`]({{ site.dcvb_cpp_api }}core/intermediate-results/scaled-colour-image-unit.html)
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

- [`BufferOverflowProtectionMode`]({{ site.dcvb_cpp_api }}core/enum-buffer-overflow-protection-mode.html?lang=cpp)
- [`CapturedResultItemType`]({{ site.dcvb_cpp_api }}core/enum-captured-result-item-type.html?lang=cpp)
- [`ColourChannelUsageType`]({{ site.dcvb_cpp_api }}core/enum-colour-channel-usage-type.html?lang=cpp)
- [`CornerType`]({{ site.dcvb_cpp_api }}core/enum-corner-type.html?lang=cpp)
- [`CrossVerificationStatus`]({{ site.dcvb_cpp_api }}core/enum-cross-verification-status.html?lang=cpp)
- [`ErrorCode`]({{ site.dcvb_cpp_api }}core/enum-error-code.html?lang=cpp)
- [`GrayscaleEnhancementMode`]({{ site.dcvb_cpp_api }}core/enum-grayscale-enhancement-mode.html?lang=cpp)
- [`GrayscaleTransformationMode`]({{ site.dcvb_cpp_api }}core/enum-grayscale-transformation-mode.html?lang=cpp)
- [`ImageCaptureDistanceMode`]({{ site.dcvb_cpp_api }}core/enum-image-capture-distance-mode.html?lang=cpp)
- [`ImageFileFormat`]({{ site.dcvb_cpp_api }}core/enum-image-file-format.html?lang=cpp)
- [`ImagePixelFormat`]({{ site.dcvb_cpp_api }}core/enum-image-pixel-format.html?lang=cpp)
- [`ImageTagType`]({{ site.dcvb_cpp_api }}core/enum-image-tag-type.html?lang=cpp)
- [`IntermediateResultUnitType`]({{ site.dcvb_cpp_api }}core/enum-intermediate-result-unit-type.html?lang=cpp)
- [`PDFReadingMode`]({{ site.dcvb_cpp_api }}core/enum-pdf-reading-mode.html?lang=cpp)
- [`RasterDataSource`]({{ site.dcvb_cpp_api }}core/enum-raster-data-source.html?lang=cpp)
- [`RegionObjectElementType`]({{ site.dcvb_cpp_api }}core/enum-region-object-element-type.html?lang=cpp)
- [`SectionType`]({{ site.dcvb_cpp_api }}core/enum-section-type.html?lang=cpp)
- [`TransformMatrixType`]({{ site.dcvb_cpp_api }}core/enum-transform-matrix-type.html?lang=cpp)
- [`VideoFrameQuality`]({{ site.dcvb_cpp_api }}core/enum-video-frame-quality.html?lang=cpp)

## DynamsoftUtility

- [`CDirectoryFetcher`]({{ site.dcvb_cpp_api }}utility/directory-fetcher.html)
- [`CFileFetcher`]({{ site.dcvb_cpp_api }}utility/file-fetcher.html)
- [`CImageDrawer`]({{ site.dcvb_cpp_api }}utility/image-drawer.html)
- [`CImageIO`]({{ site.dcvb_cpp_api }}utility/image-io.html)
- [`CImageProcessor`]({{ site.dcvb_cpp_api }}utility/image-processor.html)
- [`CMultiFrameResultCrossFilter`]({{ site.dcvb_cpp_api }}utility/multi-frame-result-cross-filter.html)
- [`CProactiveImageSourceAdapter`]({{ site.dcvb_cpp_api }}utility/proactive-image-source-adapter.html)
- [`CUtilityModule`]({{ site.dcvb_cpp_api }}utility/utility-module.html)

## DynamsoftLicense

- [`CLicenseManager`]({{ site.dcvb_cpp_api }}license/license-manager.html)
- [`CLicenseModule`]({{ site.dcvb_cpp_api }}license/license-module.html)


## DynamsoftImageProcessing

- [`CImageProcessingModule`]({{ site.dcvb_cpp_api }}image-processing/image-processing-module.html)

