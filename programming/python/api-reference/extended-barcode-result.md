---
layout: default-layout
title: ExtendedBarcodeResult Class - Dynamsoft Barcode Reader C++ Edition API Reference
description: API reference for the ExtendedBarcodeResult class in Dynamsoft Barcode Reader Python Edition, providing additional decode details such as result type, deformation level, clarity score, and a sampling image.
keywords: get_deformation, get_clarity, get_sampling_image, get_extended_barcode_result_type, ExtendedBarcodeResult, api reference
---
# ExtendedBarcodeResult Class

The `ExtendedBarcodeResult` class represents an extended barcode result in a decoded barcode element. It contains information such as the type of extended barcode, deformation, clarity, and a sampling image of the barcode.

## Definition

*Module:* dbr

*Inheritance:* [DecodedBarcodeElement]({{ site.dbr_python_api }}decoded-barcode-element.html) -> ExtendedBarcodeResult

```python
class ExtendedBarcodeResult(DecodedBarcodeElement)
```

## Methods

| Method | Description |
|--------|-------------|
| [`get_extended_barcode_result_type`](#get_extended_barcode_result_type) | Gets the type of extended barcode result. |
| [`get_deformation`](#get_deformation) | Gets the deformation of the barcode. |
| [`get_clarity`](#get_clarity) | Gets the clarity of the barcode. |
| [`get_sampling_image`](#get_sampling_image) | Gets the sampling image of the barcode. |

### get_extended_barcode_result_type

Gets the type of extended barcode result.

```python
def get_extended_barcode_result_type(self) -> int:
```

**Return value**

Returns the type of the extended barcode result. This is one of the values of the `EnumExtendedBarcodeResultType` enumeration.

**See Also**

[EnumExtendedBarcodeResultType]({{ site.dbr_python_api }}enum-extended-barcode-result-type.html)

### get_deformation

Gets the deformation of the barcode.

```python
def get_deformation(self) -> int:
```

**Return value**

Returns the deformation of the barcode.

### get_clarity

Gets the clarity of the barcode.

```python
def get_clarity(self) -> int:
```

**Return value**

Returns the clarity of the barcode.

### get_sampling_image

Gets the sampling image of the barcode.

```python
def get_sampling_image(self) -> ImageData:
```

**Return value**

Returns an `ImageData` object representing the sampling image of the barcode.

**See Also**

[ImageData]({{ site.dcvb_python_api }}core/basic-classes/image-data.html)
