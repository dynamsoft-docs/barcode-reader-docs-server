---
layout: default-layout
title: CDecodedBarcodesResultArray Class - Dynamsoft Barcode Reader C++ Edition API Reference
description: This page shows CDecodedBarcodesResultArray class definition of Dynamsoft Barcode Reader SDK C++ Edition.
keywords: GetCount, GetResult, CDecodedBarcodesResultArray, api reference
permalink: /programming/cplusplus/api-reference/decoded-barcodes-result-array.html
---
# CDecodedBarcodesResultArray Class

The `CDecodedBarcodesResultArray` class represents an array of decoded barcodes. It is an abstract class that provides an interface for accessing the results.

## Definition

*Namespace:* dynamsoft::dbr

*Assembly:* DynamsoftBarcodeReader

```cpp
class CDecodedBarcodesResultArray
```

## Methods

| Method                            | Description |
|-----------------------------------|-------------|
| [`GetCount`](#getcount)           | Gets the number of decoded barcodes in the array.|
| [`GetResult`](#getresult)           | Gets the decoded barcode at the specified index.|

### GetCount

Gets the number of localized barcodes in the unit.

```cpp
virtual int GetCount() const = 0;
```

**Return value**

Returns the number of decoded barcodes in the array.


### GetResult

It is used to get the decoded barcode at the specified index.

```cpp
virtual const CDecodedBarcodesResult* GetResult(int index) const = 0;
```

**Parameters**

`[in] index` The index of the decoded barcode.

**Return value**

Returns a pointer to the CDecodedBarcodesResult object at the specified index.

**See Also**

[CDecodedBarcodesResult]({{ site.cpp_api }}decoded-barcodes-result.html)
