---
layout: default-layout
title: BarcodeResultItem Class - Dynamsoft Barcode Reader Module Python Edition API Reference
description: Definition of BarcodeResultItem class in Dynamsoft Barcode Reader Module Python Edition.
keywords: get_format, get_text, get_location, get_confidence, get_module_size, BarcodeResultItem, api reference
---

# BarcodeResultItem Class

The `BarcodeResultItem` class represents a barcode result item decoded by barcode reader engine. It is derived from `CapturedResultItem`.

## Definition

*Module:* dbr

*Inheritance:* [CapturedResultItem]({{ site.dcvb_python_api }}core/basic-classes/captured-result-item.html) -> BarcodeResultItem

```python
class BarcodeResultItem(dynamsoft_core.CapturedResultItem)
```

## Methods

| Method               | Description |
|----------------------|-------------|
| [`get_format`](#get_format) | Gets the format of the decoded barcode result. |
| [`get_format_string`](#get_format_string) | Gets the format string of the decoded barcode result. |
| [`get_text`](#get_text) | Gets the text result of the decoded barcode. |
| [`get_bytes`](#get_bytes) | Gets the text bytes of the decoded barcode result. |
| [`get_location`](#get_location) | Gets the location of the decoded barcode in a quadrilateral. |
| [`get_confidence`](#get_confidence) | Gets the confidence of the decoded barcode result. |
| [`get_angle`](#get_angle) | Gets the angle of the decoded barcode result. |
| [`get_module_size`](#get_module_size) | Gets the module size of the decoded barcode result. |
| [`get_details`](#get_details) | Gets the details of the decoded barcode result. |
| [`is_dpm`](#is_dpm) | Gets whether the decoded barcode is a DPM code. |
| [`is_mirrored`](#is_mirrored) | Gets whether the decoded barcode is a mirrored barcode. |
| [`get_eci_segments`](#get_eci_segments) | Gets all the ECI segments in the barcode. |

### get_format

Gets the format of the decoded barcode result.

```python
def get_format(self) -> int:
```

**Return Value**

Returns the format of the decoded barcode result which is a value of the `EnumBarcodeFormat` enumeration.

**See Also**

[EnumBarcodeFormat]({{ site.dbr_python_api }}enum-barcode-format.html)

### get_format_string

Gets the format string of the decoded barcode result.

```python
def get_format_string(self) -> str:
```

**Return Value**

Returns the format string of the decoded barcode result.

### get_text

Gets the text result of the decoded barcode.

```python
def get_text(self) -> str:
```

**Return Value**

Returns the text result of the decoded barcode.

### get_bytes

Gets the text bytes of the decoded barcode result.

```python
def get_bytes(self) -> bytes:
```

**Return Value**

Returns the text bytes of the decoded barcode result.

### get_location

Gets the location of the decoded barcode in a quadrilateral.

```python
def get_location(self) -> Quadrilateral:
```

**Return Value**

Returns the location of the decoded barcode in a quadrilateral.

**See Also**

[Quadrilateral]({{ site.dcvb_python_api }}core/basic-classes/quadrilateral.html)

### get_confidence

Gets the confidence of the decoded barcode result.

```python
def get_confidence(self) -> int:
```

**Return Value**

Returns the confidence of the decoded barcode result.

### get_angle

Gets the angle of the decoded barcode result.

```python
def get_angle(self) -> int:
```

**Return Value**

Returns the angle of the decoded barcode result.

**See Also**

[How the angle is calculated for different barcode types]({{site.features}}get-confidence-rotation.html?lang=python#barcode-rotation-angle)

### get_module_size

Gets the module size of the decoded barcode result.

```python
def get_module_size(self) -> int:
```

**Return Value**

Returns the module size of the decoded barcode result.

### get_details

Gets the details of the decoded barcode result.

```python
def get_details(self) -> BarcodeDetails:
```

**Return Value**

Returns the details of the decoded barcode result.

**See Also**

- [AztecDetails]({{ site.dbr_python_api }}aztec-details.html)
- [BarcodeDetails]({{ site.dbr_python_api }}barcode-details.html)
- [DataMatrixDetails]({{ site.dbr_python_api }}datamatrix-details.html)
- [OneDCodeDetails]({{ site.dbr_python_api }}oned-code-details.html)
- [PDF417Details]({{ site.dbr_python_api }}pdf417-details.html)
- [QRCodeDetails]({{ site.dbr_python_api }}qr-code-details.html)

### is_dpm

Gets whether the decoded barcode is a DPM code.

```python
def is_dpm(self) -> bool:
```

**Return Value**

Returns whether the decoded barcode is a DPM code.

### is_mirrored

Gets whether the decoded barcode is mirrored.

```python
def is_mirrored(self) -> bool:
```

**Return Value**

Returns whether the decoded barcode is mirrored.

### get_eci_segments

Gets all the ECI segments in the barcode.

```python
def get_eci_segments(self) -> List[ECISegment]:
```

**Return Value**

Returns a list of [`ECISegment`]({{ site.dbr_python_api }}eci-segment.html) objects. Returns an empty list if no ECI information is present.

**See Also**

[ECISegment]({{ site.dbr_python_api }}eci-segment.html)

**Remarks**

Introduced in Dynamsoft Barcode Reader SDK version 11.4.1000 and Dynamsoft Capture Vision version 3.4.1000.

