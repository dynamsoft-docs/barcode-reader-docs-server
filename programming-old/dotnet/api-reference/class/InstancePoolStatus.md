---
layout: default-layout
title: InstancePoolStatus Class - Dynamsoft Barcode Reader SDK .NET Edition API Reference
description: This page shows the InstancePoolStatus Class of Dynamsoft Barcode Reader SDK .NET Edition.
keywords: InstancePoolStatus, class, api reference, .Net
needAutoGenerateSidebar: false
permalink: /programming/dotnet/api-reference/class/InstancePoolStatus.html
---


# InstancePoolStatus

Represents the status of an instance pool.

```csharp
public class InstancePoolStatus
```  

## Attributes
  
| Attribute | Type |
|---------- | ---- |
| [`AuthorizedInstancesCount`](#authorizedinstancescount) | *int* |
| [`RemainingInstancesCount`](#remaininginstancescount) | *int* |
| [`WaitingCreationInstances`](#waitingcreationinstances) | *int* |
| [`TotalWaitOccurrences`](#totalwaitoccurrences) | *int* |

### AuthorizedInstancesCount

The number of authorized instances, which represents the maximum available instances.

```csharp
int Dynamsoft.DBR.InstancePoolStatus.AuthorizedInstancesCount
```

### RemainingInstancesCount

The count of available instances that are currently not in use.

```csharp
int Dynamsoft.DBR.InstancePoolStatus.RemainingInstancesCount
```

### WaitingCreationInstances

The number of 'GetInstance' requests that are currently waiting because there are no available instances in the pool.

```csharp
int Dynamsoft.DBR.InstancePoolStatus.WaitingCreationInstances
```

### TotalWaitOccurrences

The total count of times that any operation(InitLicense, GetInstance, or Decode functions) has encountered a wait state.

```csharp
int Dynamsoft.DBR.InstancePoolStatus.TotalWaitOccurrences
```
