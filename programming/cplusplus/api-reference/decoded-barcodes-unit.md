---
layout: default-layout
title: CDecodedBarcodesUnit Class - Dynamsoft Barcode Reader C++ Edition API Reference
description: This page shows CDecodedBarcodesUnit class definition of Dynamsoft Barcode Reader SDK C++ Edition.
keywords: GetCount, GetDecodedBarcode, RemoveAllDecodedBarcodes, SetDecodedBarcode, CDecodedBarcodesUnit, api reference
---
# CDecodedBarcodesUnit Class

The `CDecodedBarcodesUnit` class represents a unit that contains decoded barcode elements. It inherits from the `CIntermediateResultUnit` class.

## Definition

*Namespace:* dynamsoft::dbr::intermediate_results

*Assembly:* DynamsoftBarcodeReader

*Inheritance:* [CIntermediateResultUnit]({{ site.dcv_cpp_api }}core/intermediate-results/intermediate-result-unit.html) -> CDecodedBarcodesUnit

```cpp
class CDecodedBarcodesUnit: public CIntermediateResultUnit
```

## Methods

| Method                            | Description |
|-----------------------------------|-------------|
| [`GetCount`](#getcount)           | Gets the number of decoded barcodes in the unit.|
| [`GetDecodedBarcode`](#getdecodedbarcode)           | Gets a pointer to the `CDecodedBarcodeElement` object at the specified index.|
| [`RemoveAllDecodedBarcodes`](#removealldecodedbarcodes)           | Removes all the decoded barcodes in the unit.|
| [`SetDecodedBarcode`](#setdecodedbarcode)           | Sets the decoded barcode.|
| [`operator[]`](#operator)           | Gets a pointer to the `CDecodedBarcodeElement` object at the specified index.|

### Inherited Methods

{%- include inherited-methods/intermediate-result-unit.md -%}

### GetCount

Gets the number of decoded barcodes in the unit.

```cpp
virtual int GetCount() const = 0;
```

**Return value**

Returns the number of decoded barcodes in the unit.

### GetDecodedBarcode

Gets a pointer to the `CDecodedBarcodeElement` object at the specified index.

```cpp
virtual const CDecodedBarcodeElement* GetDecodedBarcode(int index) const = 0;
```

**Parameter**

`[in] index` The index of the desired `CDecodedBarcodeElement` object.

**Return value**

Returns a pointer to the `CDecodedBarcodeElement` object at the specified index.

**See Also**

[CDecodedBarcodeElement]({{ site.cpp_api }}decoded-barcode-element.html)

### RemoveAllDecodedBarcodes

Removes all the decoded barcodes in the unit.

```cpp
virtual void RemoveAllDecodedBarcodes() = 0;
```

### SetDecodedBarcode

Sets the decoded barcode.

```cpp
virtual int SetDecodedBarcode(const CDecodedBarcodeElement* element, const double matrixToOriginalImage[9] = IDENTITY_MATRIX) = 0;
```

**Parameters**

`element` The decoded barcode element.

`matrixToOriginalImage` The matrix to original image.

**Return value**

Returns 0 if successful, otherwise returns a negative value.

**See Also**

[CDecodedBarcodeElement]({{ site.cpp_api }}decoded-barcode-element.html)

### operator[]

Gets a pointer to the `CDecodedBarcodeElement` object at the specified index.

```cpp
virtual const CDecodedBarcodeElement* operator[](int index) const = 0;
```

**Parameter**

`[in] index` The index of the desired `CDecodedBarcodeElement` object.

**Return value**

Returns a pointer to the `CDecodedBarcodeElement` object at the specified index.

**See Also**

[CDecodedBarcodeElement]({{ site.cpp_api }}decoded-barcode-element.html)
