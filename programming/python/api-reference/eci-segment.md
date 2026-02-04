---
layout: default-layout
title: ECISegment Class - Dynamsoft Barcode Reader Module Python Edition API Reference
description: This page shows ECISegment class definition of Dynamsoft Barcode Reader Module Python Edition.
keywords: ECISegment, ECI, Extended Channel Interpretation, api reference
---

# ECISegment Class

The `ECISegment` class represents the Extended Channel Interpretation (ECI) information within a barcode. Each ECI segment specifies the character encoding used for a portion of the decoded bytes. The charset names follow the IANA character set registry (e.g. "UTF-8", "ISO-8859-1").

**Remarks**

Introduced in Dynamsoft Barcode Reader SDK version 11.4.1000 and Dynamsoft Capture Vision version 3.4.1000.

## Definition

*Module:* dbr

```python
class ECISegment()
```

## Properties

| Property | Type | Description |
| --------- | ---- | ----------- |
| [`eci_value`](#eci_value) | *int* | ECI assignment number as defined by ISO/IEC 15424. |
| [`charset_encoding`](#charset_encoding) | *str* | Charset encoding name defined by IANA. |
| [`start_index`](#start_index) | *int* | Start index of this ECI segment in the decoded barcode bytes. |
| [`length`](#length) | *int* | Length (in bytes) of this segment within the decoded barcode bytes. |

### eci_value

ECI assignment number as defined by ISO/IEC 15424.

```python
eci_value: int
```

### charset_encoding

Charset encoding name defined by IANA (e.g. "UTF-8", "ISO-8859-1").

```python
charset_encoding: str
```

### start_index

Start index of this ECI segment in the decoded barcode bytes.

```python
start_index: int
```

### length

Length (in bytes) of this segment within the decoded barcode bytes.

```python
length: int
```

## See Also

- [`BarcodeResultItem`]({{ site.dbr_python_api }}barcode-result-item.html)
- [`DecodedBarcodeElement`]({{ site.dbr_python_api }}decoded-barcode-element.html)
