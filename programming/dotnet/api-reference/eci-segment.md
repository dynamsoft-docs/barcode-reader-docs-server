---
layout: default-layout
title: ECISegment Class - Dynamsoft Barcode Reader Module .NET Edition API Reference
description: This page shows ECISegment class definition of Dynamsoft Barcode Reader Module .NET Edition.
keywords: ECISegment, ECI, Extended Channel Interpretation, api reference
---

# ECISegment Class

The `ECISegment` class represents the Extended Channel Interpretation (ECI) information within a barcode. Each ECI segment specifies the character encoding used for a portion of the decoded bytes. The charset names follow the IANA character set registry (e.g. "UTF-8", "ISO-8859-1").

**Remarks**

Introduced in Dynamsoft Barcode Reader SDK version 11.4.1000 and Dynamsoft Capture Vision version 3.4.1000.

## Definition

*Namespace:* Dynamsoft.DBR

```csharp
public class ECISegment
```

## Attributes

| Attribute | Type | Description |
| --------- | ---- | ----------- |
| [`eciValue`](#ecivalue) | *int* | ECI assignment number as defined by ISO/IEC 15424. |
| [`charsetEncoding`](#charsetencoding) | *string* | Charset encoding name defined by IANA. |
| [`startIndex`](#startindex) | *int* | Start index of this ECI segment in the decoded barcode bytes. |
| [`length`](#length) | *int* | Length (in bytes) of this segment within the decoded barcode bytes. |

### eciValue

ECI assignment number as defined by ISO/IEC 15424.

```csharp
public int eciValue
```

### charsetEncoding

Charset encoding name defined by IANA (e.g. "UTF-8", "ISO-8859-1").

```csharp
public string charsetEncoding
```

### startIndex

Start index of this ECI segment in the decoded barcode bytes.

```csharp
public int startIndex
```

### length

Length (in bytes) of this segment within the decoded barcode bytes.

```csharp
public int length
```

## See Also

- [`BarcodeResultItem`]({{ site.dbr_dotnet_api }}barcode-result-item.html)
- [`DecodedBarcodeElement`]({{ site.dbr_dotnet_api }}decoded-barcode-element.html)
