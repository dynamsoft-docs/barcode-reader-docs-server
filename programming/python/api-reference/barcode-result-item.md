---
layout: default-layout
title: BarcodeResultItem Class - Dynamsoft Barcode Reader Module Python Edition API Reference
description: Definition of BarcodeResultItem class in Dynamsoft Barcode Reader Module Python Edition.
keywords: get_format, get_text, get_location, get_confidence, get_module_size, BarcodeResultItem, api reference
---

# BarcodeResultItem Class

The `BarcodeResultItem` class represents a barcode result item decoded by barcode reader engine. It is derived from `CapturedResultItem`.

## Definition

*Module:* dynamsoft_barcode_reader

*Inheritance:* [CapturedResultItem]({{ site.dcv_python_api }}core/basic-classes/captured-result-item.html) -> BarcodeResultItem

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

### get_format

Gets the format of the decoded barcode result.

```python
def get_format(self) -> int:
```

**Return Value**

Returns the format of the decoded barcode result which is a value of the `EnumBarcodeFormat` enumeration.

**See Also**

[EnumBarcodeFormat]({{ site.dcvb_enumerations }}barcode-reader/barcode-format.html?lang=python)

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

[Quadrilateral]({{ site.dcv_python_api }}core/basic-classes/quadrilateral.html)

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

