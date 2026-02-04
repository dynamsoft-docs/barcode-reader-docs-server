---
layout: default-layout
title: Dynamsoft Barcode Reader .NET API Reference - Main Page
description: This is the main page of Dynamsoft Barcode Reader SDK API Reference for .NET Language.
keywords: api reference, .NET
needAutoGenerateSidebar: false
---

# API Reference - .NET

## DynamsoftCaptureVisionRouter

### [CaptureVisionRouter]({{ site.dcvb_dotnet_api }}capture-vision-router/capture-vision-router.html)

- [`Constructor and Destructor`]({{ site.dcvb_dotnet_api }}capture-vision-router/instantiate.html)
- [`Single-File Processing`]({{ site.dcvb_dotnet_api }}capture-vision-router/single-file-processing.html)
- [`Multiple-File Processing`]({{ site.dcvb_dotnet_api }}capture-vision-router/multiple-file-processing.html)
- [`Settings`]({{ site.dcvb_dotnet_api }}capture-vision-router/settings.html)
- [`Auxiliary Methods`]({{ site.dcvb_dotnet_api }}capture-vision-router/auxiliary-methods.html)

### Classes

- [`BufferedItemsManager`]({{ site.dcvb_dotnet_api }}capture-vision-router/auxiliary-classes/buffered-items-manager.html)
- [`CaptureVisionRouterModule`]({{ site.dcvb_dotnet_api }}capture-vision-router/auxiliary-classes/capture-vision-router-module.html)
- [`CapturedResultFilter`]({{ site.dcvb_dotnet_api }}capture-vision-router/auxiliary-classes/captured-result-filter.html)
- [`CapturedResultReceiver`]({{ site.dcvb_dotnet_api }}capture-vision-router/auxiliary-classes/captured-result-receiver.html)
- [`CapturedResult`]({{ site.dcvb_dotnet_api }}capture-vision-router/auxiliary-classes/captured-result.html)
- [`IntermediateResultManager`]({{ site.dcvb_dotnet_api }}capture-vision-router/auxiliary-classes/intermediate-result-manager.html)
- [`IntermediateResultReceiver`]({{ site.dcvb_dotnet_api }}capture-vision-router/auxiliary-classes/intermediate-result-receiver.html)
- [`PresetTemplate`]({{ site.dcvb_dotnet_api }}capture-vision-router/auxiliary-classes/preset-template.html)
- [`SimplifiedCaptureVisionSettings`]({{ site.dcvb_dotnet_api }}capture-vision-router/auxiliary-classes/simplified-capture-vision-settings.html)

### Interfaces

- [`ICaptureStateListener`]({{ site.dcvb_dotnet_api }}capture-vision-router/auxiliary-classes/capture-state-listener.html)
- [`IImageSourceStateListener`]({{ site.dcvb_dotnet_api }}capture-vision-router/auxiliary-classes/image-source-state-listener.html)

### Enums

- [`EnumCaptureState`]({{ site.dcvb_dotnet_api }}capture-vision-router/enum-capture-state.html)
- [`EnumImageSourceState`]({{ site.dcvb_dotnet_api }}capture-vision-router/enum-image-source-state.html)

## DynamsoftBarcodeReader

### Classes

- [`AztecDetails`]({{ site.dbr_dotnet_api }}aztec-details.html)
- [`BarcodeDetails`]({{ site.dbr_dotnet_api }}barcode-details.html)
- [`BarcodeReaderModule`]({{ site.dbr_dotnet_api }}barcode-reader-module.html)
- [`BarcodeResultItem`]({{ site.dbr_dotnet_api }}barcode-result-item.html)
- [`CandidateBarcodeZone`]({{ site.dbr_dotnet_api }}candidate-barcode-zone.html)
- [`CandidateBarcodeZonesUnit`]({{ site.dbr_dotnet_api }}candidate-barcode-zones-unit.html)
- [`ComplementedBarcodeImageUnit`]({{ site.dbr_dotnet_api }}complemented-barcode-image-unit.html)
- [`DataMatrixDetails`]({{ site.dbr_dotnet_api }}datamatrix-details.html)
- [`DecodedBarcodeElement`]({{ site.dbr_dotnet_api }}decoded-barcode-element.html)
- [`DecodedBarcodesResult`]({{ site.dbr_dotnet_api }}decoded-barcodes-result.html)
- [`DecodedBarcodesUnit`]({{ site.dbr_dotnet_api }}decoded-barcodes-unit.html)
- [`DeformationResistedBarcodeImageUnit`]({{ site.dbr_dotnet_api }}deformation-resisted-barcode-image-unit.html)
- [`DeformationResistedBarcode`]({{ site.dbr_dotnet_api }}deformation-resisted-barcode.html)
- [`ECISegment`]({{ site.dbr_dotnet_api }}eci-segment.html)
- [`ExtendedBarcodeResult`]({{ site.dbr_dotnet_api }}extended-barcode-result.html)
- [`LocalizedBarcodeElement`]({{ site.dbr_dotnet_api }}localized-barcode-element.html)
- [`LocalizedBarcodesUnit`]({{ site.dbr_dotnet_api }}localized-barcodes-unit.html)
- [`OneDCodeDetails`]({{ site.dbr_dotnet_api }}oned-code-details.html)
- [`PDF417Details`]({{ site.dbr_dotnet_api }}pdf417-details.html)
- [`QRCodeDetails`]({{ site.dbr_dotnet_api }}qr-code-details.html)
- [`ScaledBarcodeImageUnit`]({{ site.dbr_dotnet_api }}scaled-barcode-image-unit.html)
- [`SimplifiedBarcodeReaderSettings`]({{ site.dbr_dotnet_api }}simplified-barcode-reader-settings.html)

### Enums

- [`EnumBarcodeFormat`]({{ site.dbr_dotnet_api }}enum-barcode-format.html)
- [`EnumDeblurMode`]({{ site.dbr_dotnet_api }}enum-deblur-mode.html)
- [`EnumExtendedBarcodeResultType`]({{ site.dbr_dotnet_api }}enum-extended-barcode-result-type.html)
- [`EnumLocalizationMode`]({{ site.dbr_dotnet_api }}enum-localization-mode.html)
- [`EnumQRCodeErrorCorrectionLevel`]({{ site.dbr_dotnet_api }}enum-qr-code-error-correction-level.html)

## DynamsoftCore

### Classes

- [`AbstractIntermediateResultReceiver`]({{ site.dcvb_dotnet_api }}core/intermediate-results/abstract-intermediate-result-receiver.html)
- [`BinaryImageUnit`]({{ site.dcvb_dotnet_api }}core/intermediate-results/binary-image-unit.html)
- [`CapturedResultBase`]({{ site.dcvb_dotnet_api }}core/basic-classes/captured-result-base.html)
- [`CapturedResultItem`]({{ site.dcvb_dotnet_api }}core/basic-classes/captured-result-item.html)
- [`ColourImageUnit`]({{ site.dcvb_dotnet_api }}core/intermediate-results/colour-image-unit.html)
- [`ContoursUnit`]({{ site.dcvb_dotnet_api }}core/intermediate-results/contours-unit.html)
- [`Contour`]({{ site.dcvb_dotnet_api }}core/basic-classes/contour.html)
- [`CoreModule`]({{ site.dcvb_dotnet_api }}core/basic-classes/core-module.html)
- [`Corner`]({{ site.dcvb_dotnet_api }}core/basic-classes/corner.html)
- [`Edge`]({{ site.dcvb_dotnet_api }}core/basic-classes/edge.html)
- [`EnhancedGrayscaleImageUnit`]({{ site.dcvb_dotnet_api }}core/intermediate-results/enhanced-grayscale-image-unit.html)
- [`FileImageTag`]({{ site.dcvb_dotnet_api }}core/basic-classes/file-image-tag.html)
- [`GrayscaleImageUnit`]({{ site.dcvb_dotnet_api }}core/intermediate-results/grayscale-image-unit.html)
- [`ImageData`]({{ site.dcvb_dotnet_api }}core/basic-classes/image-data.html)
- [`ImageSourceAdapter`]({{ site.dcvb_dotnet_api }}core/basic-classes/image-source-adapter.html)
- [`ImageTag`]({{ site.dcvb_dotnet_api }}core/basic-classes/image-tag.html)
- [`IntermediateResultExtraInfo`]({{ site.dcvb_dotnet_api }}core/intermediate-results/intermediate-result-extra-info.html)
- [`IntermediateResultUnit`]({{ site.dcvb_dotnet_api }}core/intermediate-results/intermediate-result-unit.html)
- [`IntermediateResult`]({{ site.dcvb_dotnet_api }}core/intermediate-results/intermediate-result.html)
- [`LineSegmentsUnit`]({{ site.dcvb_dotnet_api }}core/intermediate-results/line-segments-unit.html)
- [`LineSegment`]({{ site.dcvb_dotnet_api }}core/basic-classes/line-segment.html)
- [`ObservationParameters`]({{ site.dcvb_dotnet_api }}core/intermediate-results/observed-parameters.html)
- [`OriginalImageResultItem`]({{ site.dcvb_dotnet_api }}core/basic-classes/original-image-result-item.html)
- [`PDFReadingParameter`]({{ site.dcvb_dotnet_api }}core/basic-classes/pdf-reading-parameter.html)
- [`Point`]({{ site.dcvb_dotnet_api }}core/basic-classes/point.html)
- [`PredetectedRegionElement`]({{ site.dcvb_dotnet_api }}core/intermediate-results/predetected-region-element.html)
- [`PredetectedRegionsUnit`]({{ site.dcvb_dotnet_api }}core/intermediate-results/predetected-regions-unit.html)
- [`Quadrilateral`]({{ site.dcvb_dotnet_api }}core/basic-classes/quadrilateral.html)
- [`Rect`]({{ site.dcvb_dotnet_api }}core/basic-classes/rect.html)
- [`RegionObjectElement`]({{ site.dcvb_dotnet_api }}core/intermediate-results/region-object-element.html)
- [`ScaledColourImageUnit`]({{ site.dcvb_dotnet_api }}core/intermediate-results/scaled-colour-image-unit.html)
- [`ShortLinesUnit`]({{ site.dcvb_dotnet_api }}core/intermediate-results/short-lines-unit.html)
- [`TextRemovedBinaryImageUnit`]({{ site.dcvb_dotnet_api }}core/intermediate-results/text-removed-binary-image-unit.html)
- [`TextZone`]({{ site.dcvb_dotnet_api }}core/intermediate-results/text-zone.html)
- [`TextZonesUnit`]({{ site.dcvb_dotnet_api }}core/intermediate-results/text-zones-unit.html)
- [`TextureDetectionResultUnit`]({{ site.dcvb_dotnet_api }}core/intermediate-results/texture-detection-result-unit.html)
- [`TextureRemovedBinaryImageUnit`]({{ site.dcvb_dotnet_api }}core/intermediate-results/texture-removed-binary-image-unit.html)
- [`TextureRemovedGrayscaleImageUnit`]({{ site.dcvb_dotnet_api }}core/intermediate-results/texture-removed-grayscale-image-unit.html)
- [`TransformedGrayscaleImageUnit`]({{ site.dcvb_dotnet_api }}core/intermediate-results/transformed-grayscale-image-unit.html)
- [`Vector4`]({{ site.dcvb_dotnet_api }}core/basic-classes/vector4.html)
- [`VideoFrameTag`]({{ site.dcvb_dotnet_api }}core/basic-classes/video-frame-tag.html)

### Interface

- [`IImageSourceErrorListener`]({{ site.dcvb_dotnet_api }}core/basic-classes/image-source-error-listener.html)

### Enums

- [`EnumBufferOverflowProtectionMode`]({{ site.dcvb_dotnet_api }}core/enum-buffer-overflow-protection-mode.html)
- [`EnumCapturedResultItemType`]({{ site.dcvb_dotnet_api }}core/enum-captured-result-item-type.html)
- [`EnumColourChannelUsageType`]({{ site.dcvb_dotnet_api }}core/enum-colour-channel-usage-type.html)
- [`EnumCornerType`]({{ site.dcvb_dotnet_api }}core/enum-corner-type.html)
- [`EnumCrossVerificationStatus`]({{ site.dcvb_dotnet_api }}core/enum-cross-verification-status.html)
- [`EnumErrorCode`]({{ site.dcvb_dotnet_api }}core/enum-error-code.html)
- [`EnumGrayscaleEnhancementMode`]({{ site.dcvb_dotnet_api }}core/enum-grayscale-enhancement-mode.html)
- [`EnumGrayscaleTransformationMode`]({{ site.dcvb_dotnet_api }}core/enum-grayscale-transformation-mode.html)
- [`EnumImageCaptureDistanceMode`]({{ site.dcvb_dotnet_api }}core/enum-image-capture-distance-mode.html)
- [`EnumImageFileFormat`]({{ site.dcvb_dotnet_api }}core/enum-image-file-format.html)
- [`EnumImagePixelFormat`]({{ site.dcvb_dotnet_api }}core/enum-image-pixel-format.html)
- [`EnumImageTagType`]({{ site.dcvb_dotnet_api }}core/enum-image-tag-type.html)
- [`EnumIntermediateResultUnitType`]({{ site.dcvb_dotnet_api }}core/enum-intermediate-result-unit-type.html)
- [`EnumPDFReadingMode`]({{ site.dcvb_dotnet_api }}core/enum-pdf-reading-mode.html)                
- [`EnumRasterDataSource`]({{ site.dcvb_dotnet_api }}core/enum-raster-data-source.html)
- [`EnumRegionObjectElementType`]({{ site.dcvb_dotnet_api }}core/enum-region-object-element-type.html)
- [`EnumSectionType`]({{ site.dcvb_dotnet_api }}core/enum-section-type.html)
- [`EnumTransformMatrixType`]({{ site.dcvb_dotnet_api }}core/enum-transform-matrix-type.html)
- [`EnumVideoFrameQuality`]({{ site.dcvb_dotnet_api }}core/enum-video-frame-quality.html)

## DynamsoftUtility

- [`DirectoryFetcher`]({{ site.dcvb_dotnet_api }}utility/directory-fetcher.html)
- [`FileFetcher`]({{ site.dcvb_dotnet_api }}utility/file-fetcher.html)
- [`ImageIO`]({{ site.dcvb_dotnet_api }}utility/image-io.html)
- [`ImageProcessor`]({{ site.dcvb_dotnet_api }}utility/image-processor.html)
- [`ImageDrawer`]({{ site.dcvb_dotnet_api }}utility/image-drawer.html)
- [`MultiFrameResultCrossFilter`]({{ site.dcvb_dotnet_api }}utility/multi-frame-result-cross-filter.html)
- [`ProactiveImageSourceAdapter`]({{ site.dcvb_dotnet_api }}utility/proactive-image-source-adapter.html)
- [`UtilityModule`]({{ site.dcvb_dotnet_api }}utility/utility-module.html)

### Enums

- [`EnumFilterType`]({{ site.dcvb_dotnet_api }}utility/enum-filter-type.html)

## DynamsoftLicense

- [`LicenseManager`]({{ site.dcvb_dotnet_api }}license/license-manager.html)
- [`LicenseModule`]({{ site.dcvb_dotnet_api }}license/license-module.html)


## DynamsoftImageProcessing

- [`ImageProcessingModule`]({{ site.dcvb_dotnet_api }}image-processing/image-processing-module.html)

