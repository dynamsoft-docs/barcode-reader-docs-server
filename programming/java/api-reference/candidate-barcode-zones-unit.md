---
layout: default-layout
title: CandidateBarcodeZonesUnit Class - Dynamsoft Barcode Reader Java Edition API Reference
description: This page shows CandidateBarcodeZonesUnit class definition of Dynamsoft Barcode Reader SDK Java Edition.
keywords: getCount, getCandidateBarcodeZone, addCandidateBarcodeZone, removeAllCandidateBarcodeZones, removeCandidateBarcodeZone, CandidateBarcodeZonesUnit, api reference
---
# CandidateBarcodeZonesUnit Class

The `CandidateBarcodeZonesUnit` class represents a unit that contains candidate barcode zones unit. It inherits from the `IntermediateResultUnit` class.

## Definition

*Package:* com.dynamsoft.dbr.intermediate_results

*Inheritance:* [IntermediateResultUnit]({{ site.dcvb_java_api }}core/intermediate-results/intermediate-result-unit.html) -> CandidateBarcodeZonesUnit

```java
public class CandidateBarcodeZonesUnit extends IntermediateResultUnit
```

## Methods

| Method                            | Description |
|-----------------------------------|-------------|
| [`getCount`](#getcount)           | Gets the number of candidate barcode zones in the unit.|
| [`getCandidateBarcodeZone`](#getcandidatebarccodezone)           | Gets a candidate barcode zone.|
| [`getCandidateBarcodeZones`](#getcandidatebarccodezones)           | Gets all candidate barcode zones.|
| [`addCandidateBarcodeZone`](#addcandidatebarccodezone)           | Adds a candidate barcode zone.|
| [`removeAllCandidateBarcodeZones`](#removeallcandidatebarccodezones)           | Removes all the candidate barcode zones.|
| [`removeCandidateBarcodeZone`](#removecandidatebarccodezone)           | Removes a candidate barcode zone at the specified index.|

## Method Details

### getCount

Gets the number of candidate barcode zones in the unit.

```java
public int getCount()
```

**Return Value**

Returns the number of candidate barcode zones in the unit.

### getCandidateBarcodeZone

Gets a candidate barcode zone at the specified index.

```java
public CandidateBarcodeZone getCandidateBarcodeZone(int index) throws BarcodeReaderException
```

**Parameters**

`index`: The index of the candidate barcode zone.

**Return Value**

Returns the candidate barcode zone at the specified index.

**Exceptions**

`BarcodeReaderException`: Thrown when an error occurs during the operation.

**See Also**

[BarcodeReaderException]({{ site.dbr_java_api }}barcode-reader-exception.html)

### getCandidateBarcodeZones

Gets all candidate barcode zones.

```java
public CandidateBarcodeZone[] getCandidateBarcodeZones()
```

**Return Value**

Returns an array of all candidate barcode zones.

### addCandidateBarcodeZone

Adds a candidate barcode zone.

```java
public void addCandidateBarcodeZone(CandidateBarcodeZone candidateBarcodeZone) throws BarcodeReaderException
```

**Parameters**

`candidateBarcodeZone`: The candidate barcode zone to add.

**Exceptions**

`BarcodeReaderException`: Thrown when an error occurs during the operation.

**See Also**

[BarcodeReaderException]({{ site.dbr_java_api }}barcode-reader-exception.html)

### removeAllCandidateBarcodeZones

Removes all the candidate barcode zones.

```java
public void removeAllCandidateBarcodeZones()
```

### removeCandidateBarcodeZone

Removes a candidate barcode zone at the specified index.

```java
public void removeCandidateBarcodeZone(int index) throws BarcodeReaderException
```

**Parameters**

`index`: The index of the candidate barcode zone to remove.

**Exceptions**

`BarcodeReaderException`: Thrown when an error occurs during the operation.

**See Also**

[BarcodeReaderException]({{ site.dbr_java_api }}barcode-reader-exception.html)

