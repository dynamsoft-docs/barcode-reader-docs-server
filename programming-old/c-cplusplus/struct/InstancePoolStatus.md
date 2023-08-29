---
layout: default-layout
title: InstancePoolStatus Struct - Dynamsoft Barcode Reader SDK C & C++ Edition
description: This page shows the InstancePoolStatus struct of Dynamsoft Barcode Reader SDK C & C++ Edition.
keywords: InstancePoolStatus, struct, c, c++
needAutoGenerateSidebar: false
permalink: /programming/c-cplusplus/struct/InstancePoolStatus.html
---


# InstancePoolStatus

Struct to represent the status of an instance pool.

## Typedefs

```cpp
typedef struct tagInstancePoolStatus InstancePoolStatus
```  

## Attributes
  
| Attribute | Type |
|---------- | ---- |
| [`authorizedInstancesCount`](#authorizedinstancescount) | *int* |
| [`remainingInstancesCount`](#remaininginstancescount) | *int* |
| [`waitingCreationInstances`](#waitingcreationinstances) | *int* |
| [`totalWaitOccurrences`](#totalwaitoccurrences) | *int* |

### authorizedInstancesCount

The number of authorized instances, which represents the maximum available instances.

```cpp
int tagInstancePoolStatus::authorizedInstancesCount
```

### remainingInstancesCount

The count of available instances that are currently not in use.

```cpp
int tagInstancePoolStatus::remainingInstancesCount
```

### waitingCreationInstances

The number of 'GetInstance' requests that are currently waiting because there are no available instances in the pool.

```cpp
int tagInstancePoolStatus::waitingCreationInstances
```

### totalWaitOccurrences

The total count of times that any operation(InitLicense, GetInstance, or Decode functions) has encountered a wait state.

```cpp
int tagInstancePoolStatus::totalWaitOccurrences
```
