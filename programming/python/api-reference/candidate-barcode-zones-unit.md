---
layout: default-layout
title: CandidateBarcodeZonesUnit Class - Dynamsoft Barcode Reader Python Edition API Reference
description: This page shows CandidateBarcodeZonesUnit class definition of Dynamsoft Barcode Reader SDK Python Edition.
keywords: get_count, get_candidate_barcode_zone, add_candidate_barcode_zone, remove_all_candidate_barcode_zones, remove_candidate_barcode_zone, set_candidate_barcode_zone, CandidateBarcodeZonesUnit, api reference
---
# CandidateBarcodeZonesUnit Class

The `CandidateBarcodeZonesUnit` class represents a unit that contains candidate barcode zones unit. It inherits from the `IntermediateResultUnit` class.

## Definition

*Module:* dbr

*Inheritance:* [IntermediateResultUnit]({{ site.dcvb_python_api }}core/intermediate-results/intermediate-result-unit.html) -> CandidateBarcodeZonesUnit

```python
class CandidateBarcodeZonesUnit(IntermediateResultUnit)
```

## Methods

| Method                            | Description |
|-----------------------------------|-------------|
| [`add_candidate_barcode_zone`](#add_candidate_barcode_zone)           | Adds a candidate barcode zone.|
| [`get_candidate_barcode_zone`](#get_candidate_barcode_zone)           | Gets a candidate barcode zone.|
| [`get_count`](#get_count)           | Gets the number of candidate barcode zones in the unit.|
| [`remove_all_candidate_barcode_zones`](#remove_all_candidate_barcode_zones)           | Removes all the candidate barcode zones.|
| [`remove_candidate_barcode_zone`](#remove_candidate_barcode_zone)           | Removes a candidate barcode zone at the specified index.|
| [`set_candidate_barcode_zone`](#set_candidate_barcode_zone)           | Sets a candidate barcode zone at the specified index.|

### add_candidate_barcode_zone

Adds a candidate barcode zone.

```python
def add_candidate_barcode_zone(self, barcode_zone: CandidateBarcodeZone, matrix_to_original_image: List[float] = IDENTITY_MATRIX) -> int:
```

**Parameters**

`barcode_zone` The candidate barcode zone.

`matrix_to_original_image` The matrix to original image.

**Return value**

Returns 0 if successful, otherwise returns a negative value.

### get_candidate_barcode_zone

Gets a candidate barcode zone specified by index.

```python
def get_candidate_barcode_zone(self, index: int) -> Tuple[int, CandidateBarcodeZone]:
```

**Parameters**

`index` The index of the candidate barcode zone.

**Return value**

Returns a tuple containing following elements:
- `error_code` <*int*>: The error code indicating the status of the operation.
- `candidate_barcode_zone` <*CandidateBarcodeZone*>: The candidate barcode zone.

**See Also**

[CandidateBarcodeZone]({{ site.dbr_python_api }}candidate-barcode-zone.html)

### get_count

Gets the number of localized barcodes in the unit.

```python
def get_count(self) -> int:
```

**Return value**

Returns the number of candidate barcode zones in the unit.


### remove_all_candidate_barcode_zones

Removes all the candidate barcode zones

```python
def remove_all_candidate_barcode_zones(self) -> None:
```

### remove_candidate_barcode_zone

Removes a candidate barcode zone at the specified index

```python
def remove_candidate_barcode_zone(self, index: int) -> int:
```

**Parameters**

`index` The index of the candidate barcode zone.

**Return value**

Returns 0 if successful, otherwise returns a negative value.

### set_candidate_barcode_zone

Sets a candidate barcode zone at the specified index.

```python
def set_candidate_barcode_zone(self, index: int, barcode_zone: CandidateBarcodeZone, matrix_to_original_image: List[float] = IDENTITY_MATRIX) -> int:
```

**Parameters**

`index` The index of the candidate barcode zone.

`barcode_zone` The candidate barcode zone.

`matrix_to_original_image` The matrix to original image.

**Return value**

Returns 0 if successful, otherwise returns a negative value.
