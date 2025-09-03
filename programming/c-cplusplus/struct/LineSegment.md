---
layout: default-layout
title: LineSegment Struct - Dynamsoft Barcode Reader SDK C & C++ Edition
description: This page shows the LineSegment struct of Dynamsoft Barcode Reader SDK C & C++ Edition.
keywords: LineSegment, struct, c, c++
needAutoGenerateSidebar: false
permalink: /programming/c-cplusplus/struct/LineSegment.html
---


# LineSegment
Stores line segment data.

## Typedefs

```cpp
typedef struct tagLineSegment  LineSegment
```  

## Attributes
  
| Attribute | Type |
|---------- | ---- |
| [`startPoint`](#startpoint) | [`DBRPoint`](DBRPoint.md) |
| [`endPoint`](#endpoint) | [`DBRPoint`](DBRPoint.md) |
| [`linesConfidenceCoefficients`](#linesconfidencecoefficients) | *unsigned char \** |

### startPoint
The start point of the line segment.   
```cpp
DBRPoint tagLineSegment::startPoint
```

### endPoint
The end point of the line segment.
```cpp
DBRPoint tagLineSegment::endPoint
```

### linesConfidenceCoefficients
The confidence coefficients for lines. There are 4 coefficients in this set:  
1. linesConfidenceCoefficients\[0\] is average positive amplitude;   
2. linesConfidenceCoefficients\[1\] is max positive amplitude; 
3. linesConfidenceCoefficients\[2\] is average negative amplitude;   
4. linesConfidenceCoefficients\[3\] is max negative amplitude.
```cpp
unsigned char* tagLineSegment::linesConfidenceCoefficients
```
