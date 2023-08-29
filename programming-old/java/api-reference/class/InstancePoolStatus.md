---
layout: default-layout
title: InstancePoolStatus Class - Dynamsoft Barcode Reader SDK Java Edition API Reference
description: This page shows the InstancePoolStatus Class of Dynamsoft Barcode Reader SDK Java Edition.
keywords: InstancePoolStatus, class, api reference, Java
needAutoGenerateSidebar: false
permalink: /programming/java/api-reference/class/InstancePoolStatus.html
---


# InstancePoolStatus

Represents the status of an instance pool.


## Attributes
  
| Attribute | Type |
|---------- | ---- |
| [`authorizedInstancesCount`](#authorizedinstancescount) | *int* |
| [`remainingInstancesCount`](#remaininginstancescount) | *int* |
| [`waitingCreationInstances`](#waitingcreationinstances) | *int* |
| [`totalWaitOccurrences`](#totalwaitoccurrences) | *int* |

### authorizedInstancesCount

The number of authorized instances, which represents the maximum available instances.

```java
int com.dynamsoft.dbr.InstancePoolStatus.authorizedInstancesCount
```

### remainingInstancesCount

The count of available instances that are currently not in use.

```java
int com.dynamsoft.dbr.InstancePoolStatus.remainingInstancesCount
```

### waitingCreationInstances

The number of 'GetInstance' requests that are currently waiting because there are no available instances in the pool.

```java
int com.dynamsoft.dbr.InstancePoolStatus.waitingCreationInstances
```

### totalWaitOccurrences

The total count of times that any operation(InitLicense, GetInstance, or Decode functions) has encountered a wait state.

```java
int com.dynamsoft.dbr.InstancePoolStatus.totalWaitOccurrences
```
