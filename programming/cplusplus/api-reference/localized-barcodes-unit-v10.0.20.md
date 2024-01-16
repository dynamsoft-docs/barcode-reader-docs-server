---
layout: default-layout
title: CLocalizedBarcodesUnit Class
description: This page shows CLocalizedBarcodesUnit class definition of Dynamsoft Barcode Reader SDK C++ Edition.
keywords: GetCount, GetLocalizedBarcode, CLocalizedBarcodesUnit, api reference
---
# CLocalizedBarcodesUnit Class

The `CLocalizedBarcodesUnit` class represents a unit that contains localized barcodes unit. It inherits from the `CIntermediateResultUnit` class.

## Definition

*Namespace:* dynamsoft::dbr::intermediate_results

*Assembly:* DynamsoftBarcodeReader

*Inheritance:* [CIntermediateResultUnit]({{ site.dcv_cpp_api }}core/intermediate-results/intermediate-result-unit.html) -> CLocalizedBarcodesUnit

```cpp
class CLocalizedBarcodesUnit: public CIntermediateResultUnit
```

## Methods

| Method                            | Description |
|-----------------------------------|-------------|
| [`GetCount`](#getcount)           | Gets the number of localized barcodes in the unit.|
| [`GetLocalizedBarcode`](#getlocalizedbarcode)           | Gets a pointer to a specific localized barcode element.|

### Inherited Methods

{%- include inherited-methods/intermediate-result-unit-10.0.20.md -%}

### GetCount

Gets the number of localized barcodes in the unit.

```cpp
virtual int GetCount() const = 0;
```

**Return value**

Returns the number of localized barcodes in the unit.


### GetLocalizedBarcode

Gets a pointer to a specific localized barcode element.

```cpp
virtual const CLocalizedBarcodeElement* GetLocalizedBarcode(int index) const = 0;
```

**Parameters**

`[in] index` The index of the localized barcode element to retrieve.

**Return value**

Returns a const pointer to the localized barcode element at the specified index.

**See Also**

[CLocalizedBarcodeElement]({{ site.cpp_api }}localized-barcode-element.html)
