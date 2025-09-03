---
layout: default-layout
title: IntermediateResultArray Struct - Dynamsoft Barcode Reader SDK C & C++ Edition
description: This page shows the IntermediateResultArray struct of Dynamsoft Barcode Reader SDK C & C++ Edition.
keywords: IntermediateResultArray, struct, c, c++
needAutoGenerateSidebar: false
permalink: /programming/c-cplusplus/struct/IntermediateResultArray.html
---


# IntermediateResultArray
Stores the intermediate result array.

## Typedefs

```cpp
typedef struct tagIntermediateResultArray  IntermediateResultArray
```  

## Attributes
  
| Attribute | Type |
|---------- | ---- |
| [`resultsCount`](#resultscount) | *int* |
| [`results`](#results) | [`PIntermediateResult`](IntermediateResult.md)*  |


### resultsCount
The total count of intermediate result.
```cpp
int tagIntermediateResultArray::resultsCount
```

### results
The intermediate result array.
```cpp
PIntermediateResult* tagIntermediateResultArray::results
```


