---
layout: default-layout
title: DeformationResistedBarcode Class - Dynamsoft Barcode Reader Python Edition API Reference
description: This page shows DeformationResistedBarcode class definition of Dynamsoft Barcode Reader SDK Python Edition.
keywords: get_location, set_location, get_format, set_format, get_image_data, set_image_data, DeformationResistedBarcode, api reference
---
# DeformationResistedBarcode Class

The `DeformationResistedBarcode` class represents a deformation resisted barcode.

## Definition

*Module:* dynamsoft_barcode_readers

```python
class DeformationResistedBarcode
```

## Methods

| Method                            | Description |
|-----------------------------------|-------------|
| [`__init__`](#__init__) | Initializes a new instance of the `DeformationResistedBarcode` class. |
| [`get_format`](#get_format)           | Gets the format of the deformation resisted barcode. |
| [`set_format`](#set_format)           | Sets the format of the deformation resisted barcode. |
| [`get_image_data`](#get_image_data)           | Gets the deformation resisted barcode image. |
| [`set_image_data`](#set_image_data)           | Sets the deformation resisted barcode image. |
| [`get_location`](#get_location)           | Gets the location of the deformation resisted barcode.|
| [`set_location`](#set_location)           | Sets the location of the deformation resisted barcode.|


### \_\_init\_\_

Initializes a new instance of the `DeformationResistedBarcode` class.

```python
def __init__(self, *args):
```

**Parameters**

`args` <*optional*>: A variable-length argument list. Can be either empty or contain exactly three parameters in the following specified order:

- `img` <*ImageData*>, `location` <*Quadrilateral*>, `format` <*int*>: Specifies the barcode image, location and format of the deformation resisted barcode.

**See Also**

[ImageData]({{ site.dcvb_python_api }}core/basic-classes/image-data.html)

[Quadrilateral]({{ site.dcvb_python_api }}core/basic-classes/quadrilateral.html)

[EnumBarcodeFormat]({{ site.dcvb_enumerations }}barcode-reader/barcode-format.html?lang=python)

### get_format

Gets the format of the deformation resisted barcode.

```python
def get_format(self) -> int:
```

**Return value**

Returns the format of the deformation resisted barcode.

**See Also**

[EnumBarcodeFormat]({{ site.dcvb_enumerations }}barcode-reader/barcode-format.html?lang=python)

### set_format

Sets the format of the deformation resisted barcode.

```python
def set_format(self, format: int) -> None:
```

**Parameters**

`format` The format of the deformation resisted barcode.

**See Also**

[EnumBarcodeFormat]({{ site.dcvb_enumerations }}barcode-reader/barcode-format.html?lang=python)

### get_image_data

Gets the deformation resisted barcode image.

```python
def get_image_data(self) -> ImageData:
```

**Return value**

Returns the deformation resisted barcode image.

**See Also**

[ImageData]({{ site.dcvb_python_api }}core/basic-classes/image-data.html)

### set_image_data

Sets the deformation resisted barcode image.

```python
def set_image_data(self, img: ImageData) -> None:
```

**Parameters**

`img` The deformation resisted barcode image.

**See Also**

[ImageData]({{ site.dcvb_python_api }}core/basic-classes/image-data.html)

### get_location

Gets the location of the deformation resisted barcode.

```python
def get_location(self) -> Quadrilateral:
```

**Return value**

Returns the location of the deformation resisted barcode.

**See Also**

[Quadrilateral]({{ site.dcvb_python_api }}core/basic-classes/quadrilateral.html)

### set_location

Sets the location of the deformation resisted barcode.

```python
def set_location(self, loc: Quadrilateral) -> None:
```

**Parameters**

`loc` The location of the deformation resisted barcode. 

**See Also**

[Quadrilateral]({{ site.dcvb_python_api }}core/basic-classes/quadrilateral.html)

