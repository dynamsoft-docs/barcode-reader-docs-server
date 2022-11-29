---
layout: default-layout
title: Dynamsoft Barcode Reader Python API Reference - ImageData Class
description: This page shows the ImageData Class of Dynamsoft Barcode Reader for Python SDK.
keywords: ImageData, class, api reference, python
needAutoGenerateSidebar: false
---


# ImageData
Stores the image data.  

```python
class ImageData
```

## Attributes
    
| Attribute | Type |
|---------- | ---- |
| [`bytes`](#bytes) | *bytearray* |
| [`width`](#width) | *int* |
| [`height`](#height) | *int* |
| [`stride`](#stride) | *int* |
| [`image_pixel_format`](#image_pixel_format) | [`ImagePixelFormat`]({{ site.python_enumerations }}other-enums.html#imagepixelformat) |
| [`orientation`](#orientation) | *int* |

### bytes

The image data content in a byte array.

```python
ImageData.bytes
```

### width

The width of the image in pixels.  

```python
ImageData.width
```

### height

The height of the image in pixels.  

```python
ImageData.height
```

### stride

The stride (or scan width) of the image.

```python
ImageData.stride
```

### image_pixel_format

The image pixel format used in the image byte array.

```python
ImageData.image_pixel_format
```
  
### orientation

The orientation of the image data. The value is the angle that the image needs to be rotated clockwise so it shows correctly on the display in its natural orientation. It can be 0, 90, 180, or 270.

```python
ImageData.orientation
```
