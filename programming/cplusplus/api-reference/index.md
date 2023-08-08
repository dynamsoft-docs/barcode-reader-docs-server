---
layout: default-layout
title: Dynamsoft Barcode Reader C++ API Reference - Main Page
description: This is the main page of Dynamsoft Barcode Reader SDK API Reference for C++ Language.
keywords: CBarcodeReader, api reference, C++
permalink: /programming/cplusplus/api-reference/index.html
---

# API Reference - C++


## Primary Class

- [`CCaptureVisionRouter`]({{ site.dcv_cpp_api }}capture-vision-router/capture-vision-router.html)

## Input

- [`CDirectoryFetcher`]({{ site.dcv_cpp_api }}utility/directory-fetcher.html)
- [`CFileFetcher`]({{ site.dcv_cpp_api }}utility/file-fetcher.html)
- [`CImageSourceAdapter`]({{ site.dcv_cpp_api }}core/basic-structures/image-source-adapter.html)
- [`CProactiveImageSourceAdapter`]({{ site.dcv_cpp_api }}utility/proactive-image-source-adapter.html)

## Final Results

- [`CBarcodeResultItem`]({{ site.cpp_api }}barcode-result-item.html)
- [`CCapturedResultReceiver`]({{ site.dcv_cpp_api }}core/basic-structures/captured-result-receiver.html)
- [`CCapturedResult`]({{ site.dcv_cpp_api }}core/basic-structures/captured-result.html)
- [`CCapturedResultItem`]({{ site.dcv_cpp_api }}core/basic-structures/captured-result-item.html)
- [`CDecodedBarcodesResult`]({{ site.cpp_api }}decoded-barcodes-result.html)
- [`CRawImageResultItem`]({{ site.dcv_cpp_api }}core/basic-structures/raw-image-result-item.html)

## Final Results Filters

- [`CCapturedResultFilter`]({{ site.dcv_cpp_api }}core/basic-structures/captured-result-filter.html)
- [`CMultiFrameResultCrossFilter`]({{ site.dcv_cpp_api }}utility/multi-frame-result-cross-filter.html)

## Detailed Barcode Results

- [`CAztecDetails`]({{ site.cpp_api }}aztec-details.html)
- [`CBarcodeDetails`]({{ site.cpp_api }}barcode-details.html)
- [`CDataMatrixDetails`]({{ site.cpp_api }}datamatrix-details.html)
- [`COneDCodeDetails`]({{ site.cpp_api }}oned-code-details.html)
- [`CPDF417Details`]({{ site.cpp_api }}pdf417-details.html)
- [`CQRCodeDetails`]({{ site.cpp_api }}qr-code-details.html)

## Intermediate Results

- [`CIntermediateResultManager`]({{ site.dcv_cpp_api }}core/intermediate-results/intermediate-result-manager.html)
- [`CIntermediateResultReceiver`]({{ site.dcv_cpp_api }}core/intermediate-results/intermediate-result-receiver.html)
- [`CObservationParameters`]({{ site.dcv_cpp_api }}core/intermediate-results/observed-parameters.html)
- [`IntermediateResultExtraInfo`]({{ site.dcv_cpp_api }}core/structs/intermediate-result-extra-info.html)
- [`CBinaryImageUnit`]({{ site.dcv_cpp_api }}core/intermediate-results/binary-image-unit.html)
- [`CColourImageUnit`]({{ site.dcv_cpp_api }}core/intermediate-results/colour-image-unit.html)
- [`CContoursUnit`]({{ site.dcv_cpp_api }}core/intermediate-results/contours-unit.html)
- [`CEnhancedGrayscaleImageUnit`]({{ site.dcv_cpp_api }}core/intermediate-results/enhanced-grayscale-image-unit.html)
- [`CGrayscaleImageUnit`]({{ site.dcv_cpp_api }}core/intermediate-results/grayscale-image-unit.html)
- [`CIntermediateResult`]({{ site.dcv_cpp_api }}core/intermediate-results/intermediate-result.html)
- [`CIntermediateResultUnit`]({{ site.dcv_cpp_api }}core/intermediate-results/intermediate-result-unit.html)
- [`CLineSegmentsUnit`]({{ site.dcv_cpp_api }}core/intermediate-results/line-segments-unit.html)
- [`CPredetectedRegionElement`]({{ site.dcv_cpp_api }}core/intermediate-results/predetected-region-element.html)
- [`CPredetectedRegionsUnit`]({{ site.dcv_cpp_api }}core/intermediate-results/predetected-regions-unit.html)
- [`CRegionObjectElement`]({{ site.dcv_cpp_api }}core/intermediate-results/region-object-element.html)
- [`CScaledDownColourImageUnit`]({{ site.dcv_cpp_api }}core/intermediate-results/scaled-down-colour-image-unit.html)
- [`CTextRemovedBinaryImageUnit`]({{ site.dcv_cpp_api }}core/intermediate-results/text-removed-binary-image-unit.html)
- [`CTextZonesUnit`]({{ site.dcv_cpp_api }}core/intermediate-results/text-zones-unit.html)
- [`CTextureDetectionResultUnit`]({{ site.dcv_cpp_api }}core/intermediate-results/texture-detection-result-unit.html)
- [`CTextureRemovedBinaryImageUnit`]({{ site.dcv_cpp_api }}core/intermediate-results/texture-removed-binary-image-unit.html)
- [`CTextureRemovedGrayscaleImageUnit`]({{ site.dcv_cpp_api }}core/intermediate-results/texture-removed-grayscale-image-unit.html)
- [`CTransformedGrayscaleImageUnit`]({{ site.dcv_cpp_api }}core/intermediate-results/transformed-grayscale-image-unit.html)
- [`CScaledUpBarcodeImageUnit`]({{ site.cpp_api }}scaled-up-barcode-image-unit.html)
- [`CCandidateBarcodeZonesUnit`]({{ site.cpp_api }}candidate-barcode-zones-unit.html)
- [`CComplementedBarcodeImageUnit`]({{ site.cpp_api }}complemented-barcode-image-unit.html)
- [`CDeformationResistedBarcodeImageUnit`]({{ site.cpp_api }}deformation-resisted-barcode-image-unit.html)
- [`CLocalizedBarcodesUnit`]({{ site.cpp_api }}localized-barcodes-unit.html)
- [`CLocalizedBarcodeElement`]({{ site.cpp_api }}localized-barcode-element.html)
- [`CDecodedBarcodesUnit`]({{ site.cpp_api }}decoded-barcodes-unit.html)
- [`CDecodedBarcodeElement`]({{ site.cpp_api }}decoded-barcode-element.html)
- [`CExtendedBarcodeResult`]({{ site.cpp_api }}extended-barcode-result.html)

## Settings

- [`SimplifiedCaptureVisionSettings`]({{ site.dcv_cpp_api }}capture-vision-router/structs/simplified-capture-vision-settings.html)
- [`SimplifiedBarcodeReaderSettings`]({{ site.cpp_api }}simplified-barcode-reader-settings.html)
- [`CPresetTemplate`]({{ site.dcv_cpp_api }}capture-vision-router/auxiliary-classes/preset-template.html)

## State Listener

- [`CCaptureStateListener`]({{ site.dcv_cpp_api }}capture-vision-router/auxiliary-classes/capture-state-listener.html)
- [`CImageSourceStateListener`]({{ site.dcv_cpp_api }}capture-vision-router/auxiliary-classes/image-source-state-listener.html)

## License

- [`CLicenseManager`]({{ site.dcv_cpp_api }}license/license-manager.html)

## Basic Structure

- [`CContour`]({{ site.dcv_cpp_api }}core/basic-structures/contour.html)
- [`CCorner`]({{ site.dcv_cpp_api }}core/basic-structures/corner.html)
- [`CEdge`]({{ site.dcv_cpp_api }}core/basic-structures/edge.html)
- [`CFileImageTag`]({{ site.dcv_cpp_api }}core/basic-structures/file-image-tag.html)
- [`CImageData`]({{ site.dcv_cpp_api }}core/basic-structures/image-data.html)
- [`CImageTag`]({{ site.dcv_cpp_api }}core/basic-structures/image-tag.html)
- [`CLineSegment`]({{ site.dcv_cpp_api }}core/basic-structures/line-segment.html)
- [`CPDFReadingParameter`]({{ site.dcv_cpp_api }}core/basic-structures/pdf-reading-parameter.html)
- [`CPoint`]({{ site.dcv_cpp_api }}core/basic-structures/point.html)
- [`CQuadrilateral`]({{ site.dcv_cpp_api }}core/basic-structures/quadrilateral.html)
- [`CRect`]({{ site.dcv_cpp_api }}core/basic-structures/rect.html)
- [`CVideoFrameTag`]({{ site.dcv_cpp_api }}core/basic-structures/video-frame-tag.html)

## Enumerations

- [`BarcodeFormat`]({{ site.dcv_enumerations }}barcode-reader/barcode-format.html?src=cpp&&lang=cpp)
- [`BufferOverflowProtectionMode`]({{ site.dcv_enumerations }}core/buffer-overflow-protection-mode.html?src=cpp&&lang=cpp)
- [`CapturedResultItemType`]({{ site.dcv_enumerations }}core/captured-result-item-type.html?src=cpp&&lang=cpp)
- [`CaptureState`]({{ site.dcv_enumerations }}capture-vision-router/capture-state.html?src=cpp&&lang=cpp)
- [`CornerType`]({{ site.dcv_enumerations }}core/corner-type.html?src=cpp&&lang=cpp)
- [`DeblurMode`]({{ site.dcv_enumerations }}barcode-reader/deblur-mode.html?src=cpp&&lang=cpp)
- [`ErrorCode`]({{ site.dcv_enumerations }}core/error-code.html?src=cpp&&lang=cpp)
- [`ExtendedBarcodeResultType`]({{ site.dcv_enumerations }}barcode-reader/extended-barcode-result-type.html?src=cpp&&lang=cpp)
- [`GrayscaleEnhancementMode`]({{ site.dcv_enumerations }}core/grayscale-enhancement-mode.html?src=cpp&&lang=cpp)
- [`GrayscaleTransformationMode`]({{ site.dcv_enumerations }}core/grayscale-transformation-mode.html?src=cpp&&lang=cpp)
- [`ImageCaptureDistanceMode`]({{ site.dcv_enumerations }}core/image-capture-distance-mode.html?src=cpp&&lang=cpp)
- [`ImagePixelFormat`]({{ site.dcv_enumerations }}core/image-pixel-format.html?src=cpp&&lang=cpp)
- [`ImageSourceState`]({{ site.dcv_enumerations }}core/image-source-state.html?src=cpp&&lang=cpp)
- [`ImageTagType`]({{ site.dcv_enumerations }}core/image-tag-type.html?src=cpp&&lang=cpp)
- [`IntermediateResultUnitType`]({{ site.dcv_enumerations }}core/intermediate-result-unit-type.html?src=cpp&&lang=cpp)
- [`LocalizationMode`]({{ site.dcv_enumerations }}barcode-reader/localization-mode.html?src=cpp&&lang=cpp)
- [`PDFReadingMode`]({{ site.dcv_enumerations }}core/pdf-reading-mode.html?src=cpp&&lang=cpp)
- [`QRCodeErrorCorrectionLevel`]({{ site.dcv_enumerations }}barcode-reader/qr-code-error-correction-level.html?src=cpp&&lang=cpp)
- [`RasterDataSource`]({{ site.dcv_enumerations }}core/raster-data-source.html?src=cpp&&lang=cpp)
- [`RegionObjectElementType`]({{ site.dcv_enumerations }}core/region-object-element-type.html?src=cpp&&lang=cpp)
- [`SectionType`]({{ site.dcv_enumerations }}core/section-type.html?src=cpp&&lang=cpp)
- [`TransformMatrixType`]({{ site.dcv_enumerations }}core/transform-matrix-type.html?src=cpp&&lang=cpp)
- [`VideoFrameQuality`]({{ site.dcv_enumerations }}core/video-frame-quality.html?src=cpp&&lang=cpp)
