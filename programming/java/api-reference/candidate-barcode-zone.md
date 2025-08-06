---
layout: default-layout
title: CandidateBarcodeZone Class - Dynamsoft Barcode Reader Java Edition API Reference
description: This page shows CandidateBarcodeZone class definition of Dynamsoft Barcode Reader SDK Java Edition.
keywords: getLocation, setLocation, getPossibleFormats, setPossibleFormats, CandidateBarcodeZone, api reference
---
# CandidateBarcodeZone Class

The `CandidateBarcodeZone` class represents a candidate zone for barcode detection.

## Definition

*Package:* com.dynamsoft.dbr.intermediate_results

```java
public class CandidateBarcodeZone
```

## Constructors

| Constructor | Description |
|-------------|-------------|
| [`CandidateBarcodeZone()`](#candidatebarccodezone) | Initializes a new instance of the `CandidateBarcodeZone` class. |

## Methods

| Method                            | Description |
|-----------------------------------|-------------|
| [`getLocation`](#getlocation)           | Gets the location of the candidate barcode.|
| [`setLocation`](#setlocation)           | Sets the location of the candidate barcode.|
| [`getPossibleFormats`](#getpossibleformats)           | Gets the possible formats of the candidate barcode. |
| [`setPossibleFormats`](#setpossibleformats)           | Sets the possible formats of the candidate barcode. |

## Constructor Details

### CandidateBarcodeZone

Initializes a new instance of the `CandidateBarcodeZone` class.

```java
public CandidateBarcodeZone()
```

## Method Details

### getLocation

Gets the location of the candidate barcode.

```java
public Quadrilateral getLocation()
```

**Return Value**

Returns the location of the candidate barcode.

**See Also**

[Quadrilateral]({{ site.dcvb_java_api }}core/basic-classes/quadrilateral.html)

### setLocation

Sets the location of the candidate barcode.

```java
public void setLocation(Quadrilateral location)
```

**Parameters**

`location`: The location of the candidate barcode. 

**See Also**

[Quadrilateral]({{ site.dcvb_java_api }}core/basic-classes/quadrilateral.html)

### getPossibleFormats

Gets the possible formats of the candidate barcode.

```java
public long getPossibleFormats()
```

**Return Value**

Returns the possible formats of the candidate barcode.

**See Also**

[EnumBarcodeFormat]({{ site.dbr_java_api }}enum-barcode-format.html)

### setPossibleFormats

Sets the possible formats of the candidate barcode.

```java
public void setPossibleFormats(long possibleFormats)
```

**Parameters**

`possibleFormats`: The possible formats of the candidate barcode.

**See Also**

[EnumBarcodeFormat]({{ site.dbr_java_api }}enum-barcode-format.html)