---
layout: default-layout
title: ComplementedBarcodeImageUnit Class - Dynamsoft Barcode Reader Python Edition API Reference
description: This page shows ComplementedBarcodeImageUnit class definition of Dynamsoft Barcode Reader SDK Python Edition.
keywords: get_image_data, get_location, set_location, ComplementedBarcodeImageUnit, api reference
---
# ComplementedBarcodeImageUnit Class
The `ComplementedBarcodeImageUnit` class represents a unit that contains complemented barcode image data. It inherits from the `IntermediateResultUnit` class.

## Definition

*Module:* dynamsoft_barcode_readers

*Inheritance:* [IntermediateResultUnit]({{ site.dcvb_python_api }}core/intermediate-results/intermediate-result-unit.html) -> ComplementedBarcodeImageUnit

```python
class ComplementedBarcodeImageUnit(IntermediateResultUnit)
```

## Methods

| Method                            | Description |
|-----------------------------------|-------------|
| [`get_image_data`](#get_image_data) | Gets the complemented barcode image data.|
| [`get_location`](#get_location) | Gets the location of the complemented barcode in a quadrilateral.|
| [`set_location`](#set_location) | Sets the location of the complemented barcode in a quadrilateral.|

### get_image_data

Gets the complemented barcode image data.

```python
def get_image_data(self) -> ImageData:
```

**Return value**

Returns the complemented image of the barcode.

**See Also**

[ImageData]({{ site.dcvb_python_api }}core/basic-classes/image-data.html)

### get_location

Gets the location of the complemented barcode in a quadrilateral.

```python
def get_location(self) -> Quadrilateral:
```

**Return value**

Returns the location of the complemented barcode in a quadrilateral.

**See Also**

[Quadrilateral]({{ site.dcvb_python_api }}core/basic-classes/quadrilateral.html)

### set_location

Sets the location of the complemented barcode in a quadrilateral.

```python
def set_location(self, location: Quadrilateral, matrix_to_original_image: List[float] = IDENTITY_MATRIX) -> int:
```

**Parameters**

`location` The location of the complemented barcode.

`matrix_to_original_image` The matrix to original image.

**Return value**

Returns 0 if successful, otherwise returns a negative value.

**See Also**

[Quadrilateral]({{ site.dcvb_python_api }}core/basic-classes/quadrilateral.html)

