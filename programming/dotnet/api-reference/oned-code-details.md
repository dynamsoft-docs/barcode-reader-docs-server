---
layout: default-layout
title: OneDCodeDetails Class - Dynamsoft Barcode Reader Module .NET Edition API Reference
description: Definition of OneDCodeDetails class in Dynamsoft Barcode Reader Module .NET Edition.
keywords: startchar, stopchars, OneDCodeDetails, api reference
---
# OneDCodeDetails

The `OneDCodeDetails` class represents detailed information about a one-dimensional barcode. It inherits from the `BarcodeDetails` class.

## Definition

*Namespace:* Dynamsoft.DBR

*Assembly:* Dynamsoft.BarcodeReader.dll

*Inheritance:* [BarcodeDetails]({{ site.dbr_dotnet_api }}barcode-details.html) -> OneDCodeDetails

```csharp
public class OneDCodeDetails : BarcodeDetails
```

## Attributes

| Attribute | Type |
|---------- | ---- |
| [`startCharsBytes`](#startcharsbytes) | *byte[]* |
| [`stopCharsBytes`](#stopcharsbytes) | *byte[]* |
| [`checkDigitBytes`](#checkdigitbytes) | *byte[]* |
| [`startPatternRange`](#startpatternrange) | *float[]* |
| [`middlePatternRange`](#middlepatternrange) | *float[]* |
| [`endPatternRange`](#endpatternrange) | *float[]* |

### startCharsBytes

The start chars of the one-dimensional barcode in a byte array.

```csharp
byte[] startCharsBytes;
```

### stopCharsBytes

The stop chars of the one-dimensional barcode in a byte array.

```csharp
byte[] stopCharsBytes;
```

### checkDigitBytes

The check digit chars of the one-dimensional barcode in a byte array.

```csharp
byte[] checkDigitBytes;
```

### startPatternRange

The position of the start pattern relative to the barcode location.

```csharp
float[] startPatternRange
```

**Remarks**

The property represents a float array of length 2:
- Index 0: X coordinate of the start position in percentage value.
- Index 1: X coordinate of the end position in percentage value.

### middlePatternRange

The position of the middle pattern relative to the barcode location.

```csharp
float[] middlePatternRange
```

**Remarks**

The property represents a float array of length 2:
- Index 0: X coordinate of the start position in percentage value.
- Index 1: X coordinate of the end position in percentage value.

### endPatternRange

The position of the end pattern relative to the barcode location.

```csharp
float[] endPatternRange
```

**Remarks**

The property represents a float array of length 2:
- Index 0: X coordinate of the start position in percentage value.
- Index 1: X coordinate of the end position in percentage value.
