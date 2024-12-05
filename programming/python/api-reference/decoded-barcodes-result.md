---
layout: default-layout
title: DecodedBarcodesResult Class - Dynamsoft Barcode Reader Module Python Edition API Reference
description: Definition of DecodedBarcodesResult class in Dynamsoft Barcode Reader Module Python Edition.
keywords: get_original_image_hash_id, get_items, get_error_code, DecodedBarcodesResult, api reference
---
# DecodedBarcodesResult Class

The `DecodedBarcodesResult` class represents the result of a barcode reading process. It provides access to information about the decoded barcodes, the source image, and any errors that occurred during the barcode reading process.

## Definition

*Module:* dynamsoft_barcode_reader

```python
class DecodedBarcodesResult
```

## Methods

| Method               | Description |
|----------------------|-------------|
| [`get_error_code`](#get_error_code) | Gets the error code of the barcode reading result, if an error occurred. |
| [`get_error_string`](#get_error_string) | Gets the error message of the barcode reading result, if an error occurred. |
| [`get_items`](#get_items) | Gets all the barcode result items. |
| [`get_original_image_hash_id`](#get_original_image_hash_id) | Gets the hash ID of the source image. |
| [`get_original_image_tag`](#get_original_image_tag) | Gets the tag of the source image. |
| [`get_rotation_transform_matrix`](#get_rotation_transform_matrix) | Gets the 3x3 rotation transformation matrix of the original image relative to the rotated image.|

### get_error_code

Gets the error code of the barcode reading result, if an error occurred.

```python
def get_error_code(self) -> int:
```

**Return Value**

Returns the error code of the barcode reading result, or 0 if no error occurred.

**See Also**

[EnumErrorCode]({{ site.dcvb_enumerations }}core/error-code.html?lang=python)

### get_error_string

Gets the error message of the barcode reading result, if an error occurred.

```python
def get_error_string(self) -> str:
```

**Return Value**

Returns a string containing the error message of the barcode reading result, or an empty string if no error occurred.

### get_items

Gets all the decoded barcode result items.

```python
def get_items(self) -> List[BarcodeResultItem]:
```

**Return Value**

Returns a `BarcodeResultItem` list.

**See Also**

[BarcodeResultItem]({{ site.dbr_python_api }}barcode-result-item.html)

### get_original_image_hash_id

Gets the hash ID of the source image.

```python
def get_original_image_hash_id(self) -> str:
```

**Return Value**

Returns a string containing the hash ID of the source image.

### get_original_image_tag

Gets the tag of the source image.

```python
def get_original_image_tag(self) -> ImageTag:
```

**Return Value**

Returns an `ImageTag` object representing the tag of the source image.

**See Also**

[ImageTag]({{ site.dcvb_python_api }}core/basic-classes/image-tag.html)

### get_rotation_transform_matrix

Gets the 3x3 rotation transformation matrix of the original image relative to the rotated image.

```python
def get_rotation_transform_matrix(self) -> List[float]:
```

**Return Value**

Returns a float list of length 9 which represents a 3x3 rotation matrix.
