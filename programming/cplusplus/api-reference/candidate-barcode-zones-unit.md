---
layout: default-layout
title: CCandidateBarcodeZonesUnit Class - Dynamsoft Barcode Reader C++ Edition API Reference
description: This page shows CCandidateBarcodeZonesUnit class definition of Dynamsoft Barcode Reader SDK C++ Edition.
keywords: GetCount, GetCandidateBarcodeZone, AddCandidateBarcodeZone, RemoveAllCandidateBarcodeZones, RemoveCandidateBarcodeZone, SetCandidateBarcodeZone, CCandidateBarcodeZonesUnit, api reference
---
# CCandidateBarcodeZonesUnit Class

The `CCandidateBarcodeZonesUnit` class represents a unit that contains candidate barcode zones unit. It inherits from the `CIntermediateResultUnit` class.

## Definition

*Namespace:* dynamsoft::dbr::intermediate_results

*Assembly:* DynamsoftBarcodeReader

*Inheritance:* [CIntermediateResultUnit]({{ site.dcv_cpp_api }}core/intermediate-results/intermediate-result-unit.html) -> CCandidateBarcodeZonesUnit

```cpp
class CCandidateBarcodeZonesUnit: public CIntermediateResultUnit
```

## Methods

| Method                            | Description |
|-----------------------------------|-------------|
| [`AddCandidateBarcodeZone`](#addcandidatebarcodezone)           | Adds a candidate barcode zone.|
| [`GetCandidateBarcodeZone`](#getcandidatebarcodezone)           | Gets a pointer to a specific candidate barcode zone.|
| [`GetCount`](#getcount)           | Gets the number of candidate barcode zones in the unit.|
| [`RemoveAllCandidateBarcodeZones`](#removeallcandidatebarcodezones)           | Removes all the candidate barcode zones.|
| [`RemoveCandidateBarcodeZone`](#removecandidatebarcodezone)           | Removes a candidate barcode zone at the specified index.|
| [`SetCandidateBarcodeZone`](#setcandidatebarcodezone)           | Sets a candidate barcode zone at the specified index.|

### Inherited Methods

{%- include inherited-methods/intermediate-result-unit.md -%}

### AddCandidateBarcodeZone

Adds a candidate barcode zone.

```cpp
virtual int AddCandidateBarcodeZone(const CCandidateBarcodeZone& barcodeZone, const double matrixToOriginalImage[9] = IDENTITY_MATRIX) = 0;
```

**Parameters**

`barcodeZone` The candidate barcode zone.

`matrixToOriginalImage` The matrix to original image.

**Return value**

Returns 0 if successful, otherwise returns a negative value.

### GetCandidateBarcodeZone

Gets a pointer to a candidate barcode zone specified by index.

```cpp
virtual int GetCandidateBarcodeZone(int index, CCandidateBarcodeZone* barcodeZone) const = 0;
```

**Parameters**

`[in] index` The index of the candidate barcode zone.

`[out] quad` The pointer to the candidate barcode zone.

**Return value**

Returns 0 if successful, otherwise returns a negative value.

**See Also**

[CCandidateBarcodeZone]({{ site.cpp_api }}candidate-barcode-zone.html)

### GetCount

Gets the number of localized barcodes in the unit.

```cpp
virtual int GetCount() const = 0;
```

**Return value**

Returns the number of candidate barcode zones in the unit.



### RemoveAllCandidateBarcodeZones

Removes all the candidate barcode zones

```cpp
virtual void RemoveAllCandidateBarcodeZones() = 0;
```

### RemoveCandidateBarcodeZone

Removes a candidate barcode zone at the specified index

```cpp
virtual int RemoveCandidateBarcodeZone(int index) = 0;
```

**Parameters**

`index` The index of the candidate barcode zone.

**Return value**

Returns 0 if successful, otherwise returns a negative value.

### SetCandidateBarcodeZone

Sets a candidate barcode zone at the specified index.

```cpp
virtual int SetCandidateBarcodeZone(int index, const CCandidateBarcodeZone& barcodeZone, const double matrixToOriginalImage[9] = IDENTITY_MATRIX) = 0;
```

**Parameters**

`index` The index of the candidate barcode zone.

`barcodeZone` The candidate barcode zone.

`matrixToOriginalImage` The matrix to original image.

**Return value**

Returns 0 if successful, otherwise returns a negative value.
