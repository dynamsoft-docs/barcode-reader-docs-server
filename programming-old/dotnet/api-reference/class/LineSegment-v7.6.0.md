---
layout: default-layout
title: LineSegment Class - Dynamsoft Barcode Reader SDK .NET Edition API Reference
description: This page shows the LineSegment Class of Dynamsoft Barcode Reader SDK .NET Edition.
keywords: LineSegment, class, api reference, .Net
needAutoGenerateSidebar: false
permalink: /programming/dotnet/api-reference/class/LineSegment-v7.6.0.html
---

# LineSegment
Stores line segment data.

```C#
public class LineSegment
```  

## Attributes
  
| Attribute | Type |
|---------- | ---- |
| [`StartPoint`](#startpoint) | *Point* |
| [`EndPoint`](#endpoint) | *Point* |
| [`LinesConfidenceCoefficients`](#linesconfidencecoefficients) | *byte[ ]* |

### StartPoint
The start point of the line segment.   

```C#
Point Dynamsoft.Barcode.LineSegment.StartPoint
```

### EndPoint
The end point of the line segment.

```C#
Point Dynamsoft.Barcode.LineSegment.EndPoint
```

### LinesConfidenceCoefficients
The confidence coefficients for lines. There are 4 coefficients in this set:  
1. linesConfidenceCoefficients\[0\] is average positive amplitude;   
2. linesConfidenceCoefficients\[1\] is max positive amplitude; 
3. linesConfidenceCoefficients\[2\] is average negative amplitude;   
4. linesConfidenceCoefficients\[3\] is max negative amplitude.

```C#
byte[] Dynamsoft.Barcode.LineSegment.LinesConfidenceCoefficients
```
