---
layout: default-layout
title: Contour Struct - Dynamsoft Barcode Reader SDK C & C++ Edition
description: This page shows the Contour struct of Dynamsoft Barcode Reader SDK C & C++ Edition.
keywords: Contour, struct, c, c++
needAutoGenerateSidebar: false
permalink: /programming/c-cplusplus/struct/Contour.html
---


# Contour
Stores the contour information.

## Typedefs

```cpp
typedef struct tagContour  Contour
```  

---

## Attributes
  
| Attribute | Type |
|---------- | ---- |
| [`pointsCount`](#pointscount) |  *int* |
| [`points`](#points) | [DBRPoint](DBRPoint.md) \* |


### pointsCount
The total points count of the contour.
```cpp
int tagContour::pointsCount
```  
  
### points
The points array.
```cpp
DBRPoint* tagContour::points
```  
