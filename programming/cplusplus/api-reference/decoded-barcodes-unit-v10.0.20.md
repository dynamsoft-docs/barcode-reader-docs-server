---
layout: default-layout
title: CDecodedBarcodesUnit Class - Dynamsoft Barcode Reader C++ Edition API Reference
description: This page shows CDecodedBarcodesUnit class definition of Dynamsoft Barcode Reader SDK C++ Edition.
keywords: GetCount, GetDecodedBarcode, CDecodedBarcodesUnit, api reference
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
| [`GetDecodedBarcode`](#getdecodedbarcode)           | Gets a pointer to the CDecodedBarcodeElement object at the specified index.|

### Inherited Methods

{%- include inherited-methods/intermediate-result-unit-10.0.20.md -%}

### GetCount

Gets the number of decoded barcodes in the unit.

```cpp
virtual int GetCount() const = 0;
```

**Return value**

Returns the number of decoded barcodes in the unit.

### GetDecodedBarcode

Gets a pointer to the CDecodedBarcodeElement object at the specified index.

```cpp
virtual const CDecodedBarcodeElement* GetDecodedBarcode(int index) const = 0;
```

**Parameter**

`[in] index` The index of the desired CDecodedBarcodeElement object.

**Return value**

Returns a pointer to the CDecodedBarcodeElement object at the specified index.

**See Also**

[CDecodedBarcodeElement]({{ site.dbr_cpp_api }}decoded-barcode-element.html)