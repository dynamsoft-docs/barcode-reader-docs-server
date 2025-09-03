---
layout: default-layout
title: ImageData Class - Dynamsoft Barcode Reader SDK .NET Edition API Reference
description: This page shows the ImageData Class of Dynamsoft Barcode Reader SDK .NET Edition.
keywords: ImageData, class, api reference, .Net
needAutoGenerateSidebar: false
permalink: /programming/dotnet/api-reference/class/ImageData-v7.6.0.html
---


# ImageData
Stores the image data.  

```csharp
public class ImageData
```

---

## Attributes
    
| Attribute | Type |
|---------- | ---- |
| [`Bytes`](#bytes) | *byte[ ]* |
| [`Width`](#width) | *int* |
| [`Height`](#height) | *int* |
| [`Stride`](#stride) | *int* |
| [`Format`](#format) | [`EnumImagePixelFormat`]({{ site.dbr_dotnet_enumerations }}other-enums.html#imagepixelformat) |


### Bytes
The image data content in a byte array. 

```csharp
byte[] Dynamsoft.Barcode.ImageData.Bytes
```

### Width
The width of the image in pixels.  

```csharp
int Dynamsoft.Barcode.ImageData.Width
```

### Height
The height of the image in pixels.  

```csharp
int Dynamsoft.Barcode.ImageData.Height
```

### Stride
The stride (or scan width) of the image. 

```csharp
int Dynamsoft.Barcode.ImageData.Stride
```

### Format
The image pixel format used in the image byte array. 

```csharp
EnumImagePixelFormat Dynamsoft.Barcode.ImageData.Format
```
  

