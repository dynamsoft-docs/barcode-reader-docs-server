---
layout: default-layout
title: Dynamsoft Barcode Reader Python Edition API Reference - Main Page
description: This is the main page of Dynamsoft Barcode Reader SDK API Reference for Python Edition.
keywords: api reference, python
needAutoGenerateSidebar: false
---

# API Reference - Python

## DynamsoftCaptureVisionRouter

### [CaptureVisionRouter]({{ site.dcvb_python_api }}capture-vision-router/capture-vision-router.html)

- [`Constructor`]({{ site.dcvb_python_api }}capture-vision-router/instantiate.html)
- [`Single-File Processing`]({{ site.dcvb_python_api }}capture-vision-router/single-file-processing.html)
- [`Multiple-File Processing`]({{ site.dcvb_python_api }}capture-vision-router/multiple-file-processing.html)
- [`Settings`]({{ site.dcvb_python_api }}capture-vision-router/settings.html)
- [`Buffered Items`]({{ site.dcvb_python_api }}capture-vision-router/buffered-items.html)
- [`Intermediate Result`]({{ site.dcvb_python_api }}capture-vision-router/intermediate-result.html)

### Classes

- [`BufferedItemsManager`]({{ site.dcvb_python_api }}capture-vision-router/auxiliary-classes/buffered-items-manager.html)
- [`CapturedResult`]({{ site.dcvb_python_api }}capture-vision-router/auxiliary-classes/captured-result.html)
- [`CapturedResultFilter`]({{ site.dcvb_python_api }}capture-vision-router/auxiliary-classes/captured-result-filter.html)
- [`CapturedResultReceiver`]({{ site.dcvb_python_api }}capture-vision-router/auxiliary-classes/captured-result-receiver.html)
- [`CaptureStateListener`]({{ site.dcvb_python_api }}capture-vision-router/auxiliary-classes/capture-state-listener.html)
- [`CaptureVisionRouterModule`]({{ site.dcvb_python_api }}capture-vision-router/auxiliary-classes/capture-vision-router-module.html)
- [`ImageSourceStateListener`]({{ site.dcvb_python_api }}capture-vision-router/auxiliary-classes/image-source-state-listener.html)
- [`IntermediateResultManager`]({{ site.dcvb_python_api }}capture-vision-router/auxiliary-classes/intermediate-result-manager.html)
- [`IntermediateResultReceiver`]({{ site.dcvb_python_api }}capture-vision-router/auxiliary-classes/intermediate-result-receiver.html)
- [`SimplifiedCaptureVisionSettings`]({{ site.dcvb_python_api }}capture-vision-router/auxiliary-classes/simplified-capture-vision-settings.html)

### Enums

- [`EnumCaptureState`]({{ site.dcvb_python_api }}capture-vision-router/enum-capture-state.html)
- [`EnumImageSourceState`]({{ site.dcvb_python_api }}capture-vision-router/enum-image-source-state.html)
- [`EnumPresetTemplate`]({{ site.dcvb_python_api }}capture-vision-router/enum-preset-template.html)

## DynamsoftBarcodeReader

### Classes

- [`AztecDetails`]({{ site.dbr_python_api }}aztec-details.html)
- [`BarcodeDetails`]({{ site.dbr_python_api }}barcode-details.html)
- [`BarcodeReaderModule`]({{ site.dbr_python_api }}barcode-reader-module.html)
- [`BarcodeResultItem`]({{ site.dbr_python_api }}barcode-result-item.html)
- [`CandidateBarcodeZone`]({{ site.dbr_python_api }}candidate-barcode-zone.html)
- [`CandidateBarcodeZonesUnit`]({{ site.dbr_python_api }}candidate-barcode-zones-unit.html)
- [`ComplementedBarcodeImageUnit`]({{ site.dbr_python_api }}complemented-barcode-image-unit.html)
- [`DataMatrixDetails`]({{ site.dbr_python_api }}datamatrix-details.html)
- [`DecodedBarcodeElement`]({{ site.dbr_python_api }}decoded-barcode-element.html)
- [`DecodedBarcodesResult`]({{ site.dbr_python_api }}decoded-barcodes-result.html)
- [`DecodedBarcodesUnit`]({{ site.dbr_python_api }}decoded-barcodes-unit.html)
- [`DeformationResistedBarcodeImageUnit`]({{ site.dbr_python_api }}deformation-resisted-barcode-image-unit.html)
- [`DeformationResistedBarcode`]({{ site.dbr_python_api }}deformation-resisted-barcode.html)
- [`ECISegment`]({{ site.dbr_python_api }}eci-segment.html)
- [`ExtendedBarcodeResult`]({{ site.dbr_python_api }}extended-barcode-result.html)
- [`LocalizedBarcodeElement`]({{ site.dbr_python_api }}localized-barcode-element.html)
- [`LocalizedBarcodesUnit`]({{ site.dbr_python_api }}localized-barcodes-unit.html)
- [`OneDCodeDetails`]({{ site.dbr_python_api }}oned-code-details.html)
- [`PDF417Details`]({{ site.dbr_python_api }}pdf417-details.html)
- [`QRCodeDetails`]({{ site.dbr_python_api }}qr-code-details.html)
- [`ScaledBarcodeImageUnit`]({{ site.dbr_python_api }}scaled-barcode-image-unit.html)
- [`SimplifiedBarcodeReaderSettings`]({{ site.dbr_python_api }}simplified-barcode-reader-settings.html)

### Enums

- [`EnumBarcodeFormat`]({{ site.dbr_python_api }}enum-barcode-format.html)
- [`EnumDeblurMode`]({{ site.dbr_python_api }}enum-deblur-mode.html)
- [`EnumExtendedBarcodeResultType`]({{ site.dbr_python_api }}enum-extended-barcode-result-type.html)
- [`EnumLocalizationMode`]({{ site.dbr_python_api }}enum-localization-mode.html)
- [`EnumQRCodeErrorCorrectionLevel`]({{ site.dbr_python_api }}enum-qr-code-error-correction-level.html)

## DynamsoftCore

### Classes

- [`AbstractIntermediateResultReceiver`]({{ site.dcvb_python_api }}core/intermediate-results/abstract-intermediate-result-receiver.html)
- [`BinaryImageUnit`]({{ site.dcvb_python_api }}core/intermediate-results/binary-image-unit.html)
- [`CapturedResultBase`]({{ site.dcvb_python_api }}core/basic-classes/captured-result-base.html)
- [`CapturedResultItem`]({{ site.dcvb_python_api }}core/basic-classes/captured-result-item.html)
- [`ColourImageUnit`]({{ site.dcvb_python_api }}core/intermediate-results/colour-image-unit.html)
- [`ContoursUnit`]({{ site.dcvb_python_api }}core/intermediate-results/contours-unit.html)
- [`Contour`]({{ site.dcvb_python_api }}core/basic-classes/contour.html)
- [`CoreModule`]({{ site.dcvb_python_api }}core/basic-classes/core-module.html)
- [`Corner`]({{ site.dcvb_python_api }}core/basic-classes/corner.html)
- [`Edge`]({{ site.dcvb_python_api }}core/basic-classes/edge.html)
- [`EnhancedGrayscaleImageUnit`]({{ site.dcvb_python_api }}core/intermediate-results/enhanced-grayscale-image-unit.html)
- [`FileImageTag`]({{ site.dcvb_python_api }}core/basic-classes/file-image-tag.html)
- [`GrayscaleImageUnit`]({{ site.dcvb_python_api }}core/intermediate-results/grayscale-image-unit.html)
- [`ImageData`]({{ site.dcvb_python_api }}core/basic-classes/image-data.html)
- [`ImageSourceAdapter`]({{ site.dcvb_python_api }}core/basic-classes/image-source-adapter.html)
- [`ImageSourceErrorListener`]({{ site.dcvb_python_api }}core/basic-classes/image-source-error-listener.html)
- [`ImageTag`]({{ site.dcvb_python_api }}core/basic-classes/image-tag.html)
- [`IntermediateResultExtraInfo`]({{ site.dcvb_python_api }}core/intermediate-results/intermediate-result-extra-info.html)
- [`IntermediateResultUnit`]({{ site.dcvb_python_api }}core/intermediate-results/intermediate-result-unit.html)
- [`IntermediateResult`]({{ site.dcvb_python_api }}core/intermediate-results/intermediate-result.html)
- [`LineSegmentsUnit`]({{ site.dcvb_python_api }}core/intermediate-results/line-segments-unit.html)
- [`LineSegment`]({{ site.dcvb_python_api }}core/basic-classes/line-segment.html)
- [`ObservationParameters`]({{ site.dcvb_python_api }}core/intermediate-results/observed-parameters.html)
- [`OriginalImageResultItem`]({{ site.dcvb_python_api }}core/basic-classes/original-image-result-item.html)
- [`PDFReadingParameter`]({{ site.dcvb_python_api }}core/basic-classes/pdf-reading-parameter.html)
- [`Point`]({{ site.dcvb_python_api }}core/basic-classes/point.html)
- [`PredetectedRegionElement`]({{ site.dcvb_python_api }}core/intermediate-results/predetected-region-element.html)
- [`PredetectedRegionsUnit`]({{ site.dcvb_python_api }}core/intermediate-results/predetected-regions-unit.html)
- [`Quadrilateral`]({{ site.dcvb_python_api }}core/basic-classes/quadrilateral.html)
- [`Rect`]({{ site.dcvb_python_api }}core/basic-classes/rect.html)
- [`RegionObjectElement`]({{ site.dcvb_python_api }}core/intermediate-results/region-object-element.html)
- [`ScaledColourImageUnit`]({{ site.dcvb_python_api }}core/intermediate-results/scaled-colour-image-unit.html)
- [`ShortLinesUnit`]({{ site.dcvb_python_api }}core/intermediate-results/short-lines-unit.html)
- [`TextRemovedBinaryImageUnit`]({{ site.dcvb_python_api }}core/intermediate-results/text-removed-binary-image-unit.html)
- [`TextZone`]({{ site.dcvb_python_api }}core/intermediate-results/text-zone.html)
- [`TextZonesUnit`]({{ site.dcvb_python_api }}core/intermediate-results/text-zones-unit.html)
- [`TextureDetectionResultUnit`]({{ site.dcvb_python_api }}core/intermediate-results/texture-detection-result-unit.html)
- [`TextureRemovedBinaryImageUnit`]({{ site.dcvb_python_api }}core/intermediate-results/texture-removed-binary-image-unit.html)
- [`TextureRemovedGrayscaleImageUnit`]({{ site.dcvb_python_api }}core/intermediate-results/texture-removed-grayscale-image-unit.html)
- [`TransformedGrayscaleImageUnit`]({{ site.dcvb_python_api }}core/intermediate-results/transformed-grayscale-image-unit.html)
- [`Vector4`]({{ site.dcvb_python_api }}core/basic-classes/vector4.html)
- [`VideoFrameTag`]({{ site.dcvb_python_api }}core/basic-classes/video-frame-tag.html)

### Enums

- [`EnumBufferOverflowProtectionMode`]({{ site.dcvb_python_api }}core/enum-buffer-overflow-protection-mode.html)
- [`EnumCapturedResultItemType`]({{ site.dcvb_python_api }}core/enum-captured-result-item-type.html)
- [`EnumColourChannelUsageType`]({{ site.dcvb_python_api }}core/enum-colour-channel-usage-type.html)
- [`EnumCornerType`]({{ site.dcvb_python_api }}core/enum-corner-type.html)
- [`EnumCrossVerificationStatus`]({{ site.dcvb_python_api }}core/enum-cross-verification-status.html)
- [`EnumErrorCode`]({{ site.dcvb_python_api }}core/enum-error-code.html)
- [`EnumGrayscaleEnhancementMode`]({{ site.dcvb_python_api }}core/enum-grayscale-enhancement-mode.html)
- [`EnumGrayscaleTransformationMode`]({{ site.dcvb_python_api }}core/enum-grayscale-transformation-mode.html)
- [`EnumImageCaptureDistanceMode`]({{ site.dcvb_python_api }}core/enum-image-capture-distance-mode.html)
- [`EnumImageFileFormat`]({{ site.dcvb_python_api }}core/enum-image-file-format.html)
- [`EnumImagePixelFormat`]({{ site.dcvb_python_api }}core/enum-image-pixel-format.html)
- [`EnumImageTagType`]({{ site.dcvb_python_api }}core/enum-image-tag-type.html)
- [`IntermediateResultUnitType`]({{ site.dcvb_python_api }}core/enum-intermediate-result-unit-type.html)
- [`EnumPDFReadingMode`]({{ site.dcvb_python_api }}core/enum-pdf-reading-mode.html)                
- [`EnumRasterDataSource`]({{ site.dcvb_python_api }}core/enum-raster-data-source.html)
- [`EnumRegionObjectElementType`]({{ site.dcvb_python_api }}core/enum-region-object-element-type.html)
- [`EnumSectionType`]({{ site.dcvb_python_api }}core/enum-section-type.html)
- [`EnumTransformMatrixType`]({{ site.dcvb_python_api }}core/enum-transform-matrix-type.html)
- [`EnumVideoFrameQuality`]({{ site.dcvb_python_api }}core/enum-video-frame-quality.html)

## DynamsoftUtility

### Classes

- [`DirectoryFetcher`]({{ site.dcvb_python_api }}utility/directory-fetcher.html)
- [`FileFetcher`]({{ site.dcvb_python_api }}utility/file-fetcher.html)
- [`ImageIO`]({{ site.dcvb_python_api }}utility/image-io.html)
- [`ImageProcessor`]({{ site.dcvb_python_api }}utility/image-processor.html)
- [`ImageDrawer`]({{ site.dcvb_python_api }}utility/image-drawer.html)
- [`MultiFrameResultCrossFilter`]({{ site.dcvb_python_api }}utility/multi-frame-result-cross-filter.html)
- [`ProactiveImageSourceAdapter`]({{ site.dcvb_python_api }}utility/proactive-image-source-adapter.html)
- [`UtilityModule`]({{ site.dcvb_python_api }}utility/utility-module.html)

### Enums

- [`FilterType`]({{ site.dcvb_python_api }}utility/enum-filter-type.html)

## DynamsoftLicense

- [`LicenseManager`]({{ site.dcvb_python_api }}license/license-manager.html)
- [`LicenseModule`]({{ site.dcvb_python_api }}license/license-module.html)


## DynamsoftImageProcessing

- [`ImageProcessingModule`]({{ site.dcvb_python_api }}image-processing/image-processing-module.html)

