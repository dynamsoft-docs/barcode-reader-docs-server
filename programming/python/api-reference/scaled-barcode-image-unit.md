---
layout: default-layout
title: ScaledBarcodeImageUnit Class - Dynamsoft Barcode Reader Python Edition API Reference
description: This page shows ScaledBarcodeImageUnit class definition of Dynamsoft Barcode Reader SDK Python Edition.
keywords: get_image_data, set_image_data, ScaledBarcodeImageUnit, api reference
---
# ScaledBarcodeImageUnit Class

The `ScaledBarcodeImageUnit` class represents a unit that contains scaled up barcode image. It inherits from the `IntermediateResultUnit` class.

## Definition

*Module:* dbr

*Inheritance:* [IntermediateResultUnit]({{ site.dcvb_python_api }}core/intermediate-results/intermediate-result-unit.html) -> ScaledBarcodeImageUnit

```python
class ScaledBarcodeImageUnit(IntermediateResultUnit)
```

## Methods

| Method                            | Description |
|-----------------------------------|-------------|
| [`get_image_data`](#get_image_data)           | Gets the scaled up barcode image data.|
| [`set_image_data`](#set_image_data)           | Sets the scaled up image data.|

### get_image_data

Gets the scaled up barcode image data.

```python
def get_image_data(self) -> ImageData:
```

**Return value**

Returns the scaled up image of the barcode.

**See Also**

[ImageData]({{ site.dcvb_python_api }}core/basic-classes/image-data.html)

### set_image_data

Sets the scaled up image data.

```python
def set_image_data(self, image_data: ImageData) -> int:
```

**Parameters**

`image_data` The scaled up image data.

**Return value**

Returns 0 if successful, otherwise returns a negative value.

**See Also**

[ImageData]({{ site.dcvb_python_api }}core/basic-classes/image-data.html)
