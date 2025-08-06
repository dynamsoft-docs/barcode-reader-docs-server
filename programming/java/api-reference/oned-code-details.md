---
layout: default-layout
title: OneDCodeDetails Class - Dynamsoft Barcode Reader Java Edition API Reference
description: Definition of OneDCodeDetails class in Dynamsoft Barcode Reader Java Edition.
keywords: startCharsBytes, stopCharsBytes, OneDCodeDetails, api reference
---
# OneDCodeDetails

The `OneDCodeDetails` class represents detailed information about a one-dimensional barcode. It inherits from the `BarcodeDetails` class.

## Definition

*Package:* com.dynamsoft.dbr

*Inheritance:* [BarcodeDetails]({{ site.dbr_java_api }}barcode-details.html) -> OneDCodeDetails

```java
public class OneDCodeDetails extends BarcodeDetails
```

## Attributes

| Attribute | Type | Description |
|---------- | ---- | ----------- |
| [`startCharsBytes`](#startcharsbytes) | *byte[]* | The start chars of the one-dimensional barcode in a byte array. |
| [`stopCharsBytes`](#stopcharsbytes) | *byte[]* | The stop chars of the one-dimensional barcode in a byte array. |
| [`checkDigitBytes`](#checkdigitbytes) | *byte[]* | The check digit chars of the one-dimensional barcode in a byte array. |
| [`startPatternRange`](#startpatternrange) | *float[]* | The position of the start pattern relative to the barcode location. |
| [`middlePatternRange`](#middlepatternrange) | *float[]* | The position of the middle pattern relative to the barcode location. |
| [`endPatternRange`](#endpatternrange) | *float[]* | The position of the end pattern relative to the barcode location. |

## Constructors

| Constructor | Description |
|------------ | ----------- |
| [`OneDCodeDetails()`](#onedcodedetails) | Default constructor. |

## Attribute Details

### startCharsBytes

The start chars of the one-dimensional barcode in a byte array.

```java
public byte[] startCharsBytes
```

### stopCharsBytes

The stop chars of the one-dimensional barcode in a byte array.

```java
public byte[] stopCharsBytes
```

### checkDigitBytes

The check digit chars of the one-dimensional barcode in a byte array.

```java
public byte[] checkDigitBytes
```

### startPatternRange

The position of the start pattern relative to the barcode location.

```java
public float[] startPatternRange
```

**Remarks**

The array represents a float array of length 2:
- Index 0: X coordinate of the start position in percentage value.
- Index 1: X coordinate of the end position in percentage value.

### middlePatternRange

The position of the middle pattern relative to the barcode location.

```java
public float[] middlePatternRange
```

**Remarks**

The array represents a float array of length 2:
- Index 0: X coordinate of the start position in percentage value.
- Index 1: X coordinate of the end position in percentage value.

### endPatternRange

The position of the end pattern relative to the barcode location.

```java
public float[] endPatternRange
```

**Remarks**

The array represents a float array of length 2:
- Index 0: X coordinate of the start position in percentage value.
- Index 1: X coordinate of the end position in percentage value.

## Constructor Details

### OneDCodeDetails()

Default constructor. Initializes a new instance of the OneDCodeDetails class.

```java
public OneDCodeDetails()
```
