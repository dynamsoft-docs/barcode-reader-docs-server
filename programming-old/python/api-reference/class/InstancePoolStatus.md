---
layout: default-layout
title: InstancePoolStatus Class - Dynamsoft Barcode Reader SDK Python Edition API Reference
description: This page shows the InstancePoolStatus Class of Dynamsoft Barcode Reader SDK Python Edition.
keywords: InstancePoolStatus, class, api reference, Python
needAutoGenerateSidebar: false
permalink: /programming/python/api-reference/class/InstancePoolStatus.html
---


# InstancePoolStatus

Represents the status of an instance pool.

```python
class InstancePoolStatus
```  

## Attributes
  
| Attribute | Type |
|---------- | ---- |
| [`authorized_instances_count`](#authorized_instances_count) | *int* |
| [`remaining_instances_count`](#remaining_instances_count) | *int* |
| [`waiting_creation_instances`](#waiting_creation_instances) | *int* |
| [`total_wait_occurrences`](#total_wait_occurrences) | *int* |

### authorized_instances_count

The number of authorized instances, which represents the maximum available instances.

```python
InstancePoolStatus.authorized_instances_count
```

### remaining_instances_count

The count of available instances that are currently not in use.

```python
InstancePoolStatus.remaining_instances_count
```

### waiting_creation_instances

The number of 'GetInstance' requests that are currently waiting because there are no available instances in the pool.

```python
InstancePoolStatus.waiting_creation_instances
```

### total_wait_occurrences

The total count of times that any operation(InitLicense, GetInstance, or Decode functions) has encountered a wait state.

```python
InstancePoolStatus.total_wait_occurrences
```
