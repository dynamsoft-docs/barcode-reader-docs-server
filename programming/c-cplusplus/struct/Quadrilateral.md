---
layout: default-layout
title: Quadrilateral Struct - Dynamsoft Barcode Reader SDK C & C++ Edition
description: This page shows the Quadrilateral struct of Dynamsoft Barcode Reader SDK C & C++ Edition.
keywords: Quadrilateral, struct, c, c++
needAutoGenerateSidebar: false
permalink: /programming/c-cplusplus/struct/Quadrilateral.html
---


# Quadrilateral
Stores the quadrilateral.  

## Typedefs

```cpp
typedef struct tagQuadrilateral  Quadrilateral 
```  

## Attributes
  
| Attribute | Type |
|---------- | ---- |
| [`points`](#points) | [`DBRPoint`](DBRPoint.md)[4] |


### points
Four vertexes in a clockwise direction of a quadrilateral. Index 0 represents the left-most vertex. 
```cpp
DBRPoint tagQuadrilateral::points[4]
```



