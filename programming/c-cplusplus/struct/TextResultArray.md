---
layout: default-layout
title: TextResultArray Struct - Dynamsoft Barcode Reader SDK C & C++ Edition
description: This page shows the TextResultArray struct of Dynamsoft Barcode Reader SDK C & C++ Edition.
keywords: TextResultArray, struct, c, c++
needAutoGenerateSidebar: false
permalink: /programming/c-cplusplus/struct/TextResultArray.html
---

# TextResultArray
Stores the text result array.  

## Typedefs

```cpp
typedef struct tagTextResultArray  TextResultArray
typedef struct tagTextResultArray*  PTextResultArray
```  

## Attributes
  
| Attribute | Type |
|---------- | ---- |
| [`resultsCount`](#resultscount) | *int* |
| [`results`](#results) | [`PTextResult`](TextResult.md)\* |


### resultsCount
The total count of text result.
```cpp
int tagTextResultArray::resultsCount
```

### results
The text result array.
```cpp
PTextResult* tagTextResultArray::results
```

