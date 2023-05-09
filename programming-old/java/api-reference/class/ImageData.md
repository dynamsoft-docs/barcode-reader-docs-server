---
layout: default-layout
title: ImageData Class - Dynamsoft Barcode Reader SDK Java Edition API Reference
description: This page shows the ImageData Class of Dynamsoft Barcode Reader SDK Java Edition API Reference.
keywords: ImageData, class, api reference, java
needAutoGenerateSidebar: false
permalink: /programming/java/api-reference/class/ImageData.html
---


# ImageData

Stores the image data.  

## Attributes

| Attribute | Type |
|---------- | ---- |
| [`bytes`](#bytes) | *byte\[\]* |
| [`width`](#width) | *int* |
| [`height`](#height) | *int* |
| [`stride`](#stride) | *int* |
| [`format`](#format) | *int* |
| [`orientation`](#orientation) | *int* |

### bytes

The image data content in a byte array.

```java
byte[] com.dynamsoft.dbr.ImageData.bytes
```

### width

The width of the image in pixels.

```java
int com.dynamsoft.dbr.ImageData.width
```

### height

The height of the image in pixels.

```java
int com.dynamsoft.dbr.ImageData.height
```

### stride

The stride (or scan width) of the image.

```java
int com.dynamsoft.dbr.ImageData.stride
```

### format

The image pixel format used in the image byte array.

```java
int com.dynamsoft.dbr.ImageData.format
```
  
### orientation

The orientation of the image data. The value is the angle that the image needs to be rotated clockwise so it shows correctly on the display in its natural orientation. It can be 0, 90, 180, or 270.

```java
int com.dynamsoft.dbr.ImageData.orientation
```
