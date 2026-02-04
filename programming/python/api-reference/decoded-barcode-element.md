---
layout: default-layout
title: DecodedBarcodeElement Class - Dynamsoft Barcode Reader Python Edition API Reference
description: This page shows DecodedBarcodeElement class definition of Dynamsoft Barcode Reader SDK Python Edition.
keywords: get_format, get_text, get_bytes, get_angle, get_confidence, is_dpm, DecodedBarcodeElement, api reference
---
# DecodedBarcodeElement Class

The `DecodedBarcodeElement` class represents a decoded barcode element. It inherits from the `RegionObjectElement` class and provides additional functionality for retrieving information about the decoded barcode.

## Definition

*Module:* dbr

*Inheritance:* [RegionObjectElement]({{ site.dcvb_python_api }}core/intermediate-results/region-object-element.html) -> DecodedBarcodeElement

```python
class DecodedBarcodeElement(RegionObjectElement)
```

## Methods

| Method | Description |
| --- | --- |
| [`__init__`](#__init__) | Initializes a new instance of the `DecodedBarcodeElement` class. |
| [`get_format`](#get_format) | Gets the format of the barcode. |
| [`get_format_string`](#get_format_string) | Gets the string representation of the barcode format. |
| [`get_text`](#get_text) | Gets the text of the decoded barcode. |
| [`get_bytes`](#get_bytes)| Gets the raw bytes of the decoded barcode.|
| [`get_details`](#get_details) | Gets the details of the decoded barcode.|
| [`is_dpm`](#is_dpm)| Determines whether the decoded barcode is a DPM (Direct Part Marking) code.|
| [`is_mirrored`](#is_mirrored)| Determines whether the decoded barcode is mirrored.|
| [`get_angle`](#get_angle) | Gets the orientation angle of the barcode. |
| [`get_module_size`](#get_module_size) | Gets the module size of the barcode. |
| [`get_confidence`](#get_confidence) | Gets the confidence score of the barcode recognition result. |
| [`get_extended_barcode_results_count`](#get_extended_barcode_results_count) | Gets the number of extended barcode results for the decoded barcode.|
| [`get_extended_barcode_result`](#get_extended_barcode_result) | Gets the extended barcode result at the specified index for the decoded barcode.|
| [`set_format`](#set_format) | Sets the format of the barcode. |
| [`set_text`](#set_text) | Sets the text of the decoded barcode. |
| [`set_bytes`](#set_bytes)| Sets the raw bytes of the decoded barcode.|
| [`set_confidence`](#set_confidence) | Sets the confidence score of the barcode recognition result. |
| [`get_eci_segments`](#get_eci_segments) | Gets all the ECI segments in the barcode. |

### \_\_init\_\_

Initializes a new instance of the `DecodedBarcodeElement` class.

```python
def __init__(self):
```

### get_format

It is used to get the format of the barcode.

```python
def get_format(self) -> int:
```

**Return value**

Returns the format of the barcode. This is one of the values of the `EnumBarcodeFormat` enumeration.

**See Also**

[EnumBarcodeFormat]({{ site.dbr_python_api }}enum-barcode-format.html)

### get_format_string

It is used to get the string representation of the barcode format.

```python
def get_format_string(self) -> str:
```

**Return value**

Returns the string representation of the barcode format.

### get_text

Gets the text of the decoded barcode.

```python
def get_text(self) -> str:
```

**Return value**

Returns a string representing the text of the decoded barcode.

### get_bytes

Gets the raw bytes of the decoded barcode.

```python
def get_bytes(self) -> bytes:
```

**Return value**

Returns the raw bytes of the decoded barcode.

### get_details

Gets the details of the decoded barcode.

```python
def get_details(self) -> BarcodeDetails:
```

**Return value**

Returns the details of the decoded barcode.

**See Also**

- [AztecDetails]({{ site.dbr_python_api }}aztec-details.html)
- [BarcodeDetails]({{ site.dbr_python_api }}barcode-details.html)
- [DataMatrixDetails]({{ site.dbr_python_api }}datamatrix-details.html)
- [OneDCodeDetails]({{ site.dbr_python_api }}oned-code-details.html)
- [PDF417Details]({{ site.dbr_python_api }}pdf417-details.html)
- [QRCodeDetails]({{ site.dbr_python_api }}qr-code-details.html)

### is_dpm

Determines whether the decoded barcode is a DPM (Direct Part Marking) code.

```python
def is_dpm(self) -> bool:
```

**Return value**

Returns true if the decoded barcode is a DPM code, false otherwise.

### is_mirrored

Determines whether the decoded barcode is mirrored.

```python
def is_mirrored(self) -> bool:
```

**Return value**

Returns true if the decoded barcode is mirrored, false otherwise.

### get_angle

It is used to get the orientation angle of the barcode.

```python
def get_angle(self) -> int:
```

**Return value**

Returns the orientation angle of the barcode.

### get_module_size

It is used to get the module size of the barcode.

```python
def get_module_size(self) -> int:
```

**Return value**

Returns the module size of the barcode.

### get_confidence

It is used to get the confidence score of the barcode recognition result.

```python
def get_confidence(self) -> int:
```

**Return value**

Returns the confidence score of the barcode recognition result.

### get_extended_barcode_results_count

Gets the number of extended barcode results for the decoded barcode.

```python
def get_extended_barcode_results_count(self) -> int:
```

**Return value**

Returns the number of extended barcode results for the decoded barcode.

### get_extended_barcode_result

Gets the extended barcode result at the specified index for the decoded barcode.

```python
def get_extended_barcode_result(self, index: int) -> "ExtendedBarcodeResult":
```

**Parameters**

`index` The index of the extended barcode result to retrieve.

**Return value**

Returns an `ExtendedBarcodeResult` object at the specified index for the decoded barcode.

**See Also**

[ExtendedBarcodeResult]({{ site.dbr_python_api }}extended-barcode-result.html)

### set_format

Sets the format of the barcode.

```python
def set_format(self, format: int) -> None:
```

**Parameters**

`format` The format of the barcode. This is one of the values of the `EnumBarcodeFormat` enumeration.

**See Also**

[EnumBarcodeFormat]({{ site.dbr_python_api }}enum-barcode-format.html)

### set_text

Sets the text of the barcode.

```python
def set_text(self, text: str) -> None:
```

**Parameters**

`text` The text of the barcode.

### set_bytes

Sets the raw bytes of the barcode.

```python
def set_bytes(self, bytes: bytes):
```

**Parameters**

`bytes` The raw bytes of the barcode.

### set_confidence

Sets the confidence of the barcode.

```python
def set_confidence(self, confidence: int) -> None:
```

**Parameters**

`confidence` The confidence of the barcode.

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

