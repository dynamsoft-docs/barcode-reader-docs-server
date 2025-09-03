---
layout: default-layout
title: BarcodeReader LiceGeneralnse Methods - Dynamsoft Barcode Reader SDK Python Edition API Reference
description: This page shows BarcodeReader General Methods of Dynamsoft Barcode Reader Python Edition.
keywords: transform_coordinates, BarcodeReader, api reference, python
needAutoGenerateSidebar: true
permalink: /programming/python/api-reference/BarcodeReader/general.html
---


# BarcodeReader General Methods

  | Method               | Description |
  |----------------------|-------------|
  | [`transform_coordinates`](#transform_coordinates) | Transform the coordinates of a point based on the given transformation matrix.  |
  
## transform_coordinates

Transform the coordinates of a point based on the given transformation matrix.

```python
BarcodeReader.transform_coordinates(original_point, transformation_matrix)
```

**Parameters**  

`[in] original_point` <*class Point*>: The original point that needs to be transformed.  

`[in] transformation_matrix` <*list\<double\>*>: The 3x3 matrix used for coordinate transformation.

**Return Value**  

`target_point` <*point*> : The point after transformation.

**Code Snippet**  

```python
#get original_point and transformation_matrix from LocalizationResult
target_point = BarcodeReader.transform_coordinates(original_point, transformation_matrix)
```
