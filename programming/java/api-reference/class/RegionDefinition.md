---
layout: default-layout
title: RegionDefinition Class - Dynamsoft Barcode Reader SDK Java Edition API Reference
description: This page shows the RegionDefinition Class of Dynamsoft Barcode Reader SDK Java Edition API Reference.
keywords: RegionDefinition, class, api reference, java
needAutoGenerateSidebar: false
permalink: /programming/java/api-reference/class/RegionDefinition.html
---


# RegionDefinition
Stores the region information. 
  

## Attributes
  
| Attribute | Type |
|---------- | ---- |
| [`regionTop`](#regiontop) | *int* |
| [`regionLeft`](#regionleft) | *int* |
| [`regionRight`](#regionright) | *int* |
| [`regionBottom`](#regionbottom) | *int* |
| [`regionMeasuredByPercentage`](#regionmeasuredbypercentage) | *int* |


### regionTop
The top-most coordinate or percentage of the region.
```java
int com.dynamsoft.dbr.RegionDefinition.regionTop
```
**Value Range**     
    regionMeasuredByPercentage = 0: [0, 0x7fffffff]  
    regionMeasuredByPercentage = 1: [0, 100]  
      
**Default Value**     
    0

### regionLeft
The left-most coordinate or percentage of the region.
```java
int com.dynamsoft.dbr.RegionDefinition.regionLeft
```
**Value Range**     
    regionMeasuredByPercentage = 0: [0, 0x7fffffff]  
    regionMeasuredByPercentage = 1: [0, 100]  
      
**Default Value**     
    0

### regionRight
The right-most coordinate or percentage of the region.
```java
int com.dynamsoft.dbr.RegionDefinition.regionRight
```
**Value Range**     
    regionMeasuredByPercentage = 0: [0, 0x7fffffff]  
    regionMeasuredByPercentage = 1: [0, 100]  
      
**Default Value**     
    0

### regionBottom
The bottom-most coordinate or percentage of the region.
```java
int com.dynamsoft.dbr.RegionDefinition.regionBottom
```
**Value Range**     
    regionMeasuredByPercentage = 0: [0, 0x7fffffff]  
    regionMeasuredByPercentage = 1: [0, 100]  
      
**Default Value**     
    0
    
### regionMeasuredByPercentage
Sets whether or not to use percentage to measure the region size.
```java
int com.dynamsoft.dbr.RegionDefinition.regionMeasuredByPercentage
```
**Value Range**     
    [0, 1]
      
**Default Value**     
    0
    
**Remarks**       
    When it's set to 1, the values of Top, Left, Right, Bottom indicate percentage (from 0 to 100); Otherwise, they indicate coordinates. 0: not by percentage 1: by percentage.
