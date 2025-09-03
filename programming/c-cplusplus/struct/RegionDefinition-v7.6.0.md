---
layout: default-layout
title: RegionDefinition Struct - Dynamsoft Barcode Reader SDK C & C++ Edition
description: This page shows the RegionDefinition struct of Dynamsoft Barcode Reader SDK C & C++ Edition.
keywords: RegionDefinition, struct, c, c++
needAutoGenerateSidebar: false
permalink: /programming/c-cplusplus/struct/RegionDefinition-v7.6.0.html
---


# RegionDefinition
Stores the region information.  

## Typedefs

```cpp
typedef struct tagRegionDefinition  RegionDefinition
```  

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
```cpp
int tagRegionDefinition::regionTop
```
- **Value range**   
    regionMeasuredByPercentage = 0: [0, 0x7fffffff]  
    regionMeasuredByPercentage = 1: [0, 100]  
      
- **Default value**   
    0

### regionLeft
The left-most coordinate or percentage of the region.
```cpp
int tagRegionDefinition::regionLeft
```
- **Value range**   
    regionMeasuredByPercentage = 0: [0, 0x7fffffff]  
    regionMeasuredByPercentage = 1: [0, 100]  
      
- **Default value**   
    0

### regionRight
The right-most coordinate or percentage of the region.
```cpp
int tagRegionDefinition::regionRight
```
- **Value range**   
    regionMeasuredByPercentage = 0: [0, 0x7fffffff]  
    regionMeasuredByPercentage = 1: [0, 100]  
      
- **Default value**   
    0

### regionBottom
The bottom-most coordinate or percentage of the region.
```cpp
int tagRegionDefinition::regionBottom
```
- **Value range**   
    regionMeasuredByPercentage = 0: [0, 0x7fffffff]  
    regionMeasuredByPercentage = 1: [0, 100]  
      
- **Default value**   
    0
    
### regionMeasuredByPercentage
Sets whether or not to use percentage to measure the region size.
```cpp
int tagRegionDefinition::regionMeasuredByPercentage
```
- **Value range**   
    [0, 1]
      
- **Default value**   
    0
    
- **Remark**   
    When it's set to 1, the values of Top, Left, Right, Bottom indicate percentage (from 0 to 100); Otherwise, they indicate coordinates. 0: not by percentage 1: by percentage.
