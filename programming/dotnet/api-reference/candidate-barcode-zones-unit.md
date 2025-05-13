---
layout: default-layout
title: CandidateBarcodeZonesUnit Class - Dynamsoft Barcode Reader .NET Edition API Reference
description: This page shows CandidateBarcodeZonesUnit class definition of Dynamsoft Barcode Reader SDK .NET Edition.
keywords: GetCount, GetCandidateBarcodeZone, AddCandidateBarcodeZone, RemoveAllCandidateBarcodeZones, RemoveCandidateBarcodeZone, SetCandidateBarcodeZone, CandidateBarcodeZonesUnit, api reference
---
# CandidateBarcodeZonesUnit Class

The `CandidateBarcodeZonesUnit` class represents a unit that contains candidate barcode zones unit. It inherits from the `IntermediateResultUnit` class.

## Definition

*Namespace:* Dynamsoft.DBR.intermediate_results


*Inheritance:* [IntermediateResultUnit]({{ site.dcvb_dotnet_api }}core/intermediate-results/intermediate-result-unit.html) -> CandidateBarcodeZonesUnit

```csharp
class CandidateBarcodeZonesUnit : IntermediateResultUnit
```

## Methods

| Method                            | Description |
|-----------------------------------|-------------|
| [`AddCandidateBarcodeZone`](#addcandidatebarcodezone)           | Adds a candidate barcode zone.|
| [`GetCandidateBarcodeZone`](#getcandidatebarcodezone)           | Gets a specific candidate barcode zone.|
| [`GetCandidateBarcodeZones`](#getcandidatebarcodezones)           | Gets all candidate barcode zones.|
| [`GetCount`](#getcount)           | Gets the number of candidate barcode zones in the unit.|
| [`RemoveAllCandidateBarcodeZones`](#removeallcandidatebarcodezones)           | Removes all the candidate barcode zones.|
| [`RemoveCandidateBarcodeZone`](#removecandidatebarcodezone)           | Removes a candidate barcode zone at the specified index.|
| [`SetCandidateBarcodeZone`](#setcandidatebarcodezone)           | Sets a candidate barcode zone at the specified index.|

### Inherited Methods

Checkout inherited methods from [IntermediateResultUnit]({{ site.dcvb_dotnet_api }}core/intermediate-results/intermediate-result-unit.html) for more details.

### AddCandidateBarcodeZone

Adds a candidate barcode zone.

```csharp
int AddCandidateBarcodeZone(CandidateBarcodeZone barcodeZone, double[] matrixToOriginalImage = null)
```

**Parameters**

`barcodeZone` The candidate barcode zone.

`matrixToOriginalImage` The matrix to original image.

**Return value**

Returns 0 if successful, otherwise returns a negative value.

### GetCandidateBarcodeZone

Gets a candidate barcode zone specified by index.

```csharp
int GetCandidateBarcodeZone(int index, out CandidateBarcodeZone barcodeZone)
```

**Parameters**

`[in] index` The index of the candidate barcode zone.

`[out] barcodeZone` The candidate barcode zone.

**Return value**

Returns 0 if successful, otherwise returns a negative value.

**See Also**

[CandidateBarcodeZone]({{ site.dbr_dotnet_api }}candidate-barcode-zone.html)

### GetCandidateBarcodeZones

Gets all candidate barcode zones.

```csharp
int GetCandidateBarcodeZones(out CandidateBarcodeZone[] barcodeZones)
```

**Parameters**

`[out] barcodeZones` The all candidate barcode zones.

**Return value**

Returns 0 if successful, otherwise returns a negative value.

**See Also**

[CandidateBarcodeZone]({{ site.dbr_dotnet_api }}candidate-barcode-zone.html)

### GetCount

Gets the number of localized barcodes in the unit.

```csharp
int GetCount()
```

**Return value**

Returns the number of candidate barcode zones in the unit.

### RemoveAllCandidateBarcodeZones

Removes all the candidate barcode zones

```csharp
void RemoveAllCandidateBarcodeZones()
```

### RemoveCandidateBarcodeZone

Removes a candidate barcode zone at the specified index

```csharp
int RemoveCandidateBarcodeZone(int index)
```

**Parameters**

`index` The index of the candidate barcode zone.

**Return value**

Returns 0 if successful, otherwise returns a negative value.

### SetCandidateBarcodeZone

Sets a candidate barcode zone at the specified index.

```csharp
int SetCandidateBarcodeZone(int index, CandidateBarcodeZone barcodeZone, double[] matrixToOriginalImage = null)
```

**Parameters**

`index` The index of the candidate barcode zone.

`barcodeZone` The candidate barcode zone.

`matrixToOriginalImage` The matrix to original image.

**Return value**

Returns 0 if successful, otherwise returns a negative value.

**See Also**

[CandidateBarcodeZone]({{ site.dbr_dotnet_api }}candidate-barcode-zone.html)
