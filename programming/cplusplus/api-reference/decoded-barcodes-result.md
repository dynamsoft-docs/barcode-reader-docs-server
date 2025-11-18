---
layout: default-layout
title: CDecodedBarcodesResult Class - Dynamsoft Barcode Reader C++ Edition API Reference
description: This page shows CDecodedBarcodesResult class definition of Dynamsoft Barcode Reader SDK C++ Edition.
keywords: GetOriginalImageHashId, GetItemsCount, GetErrorCode, CDecodedBarcodesResult, api reference
---
# CDecodedBarcodesResult Class

The `CDecodedBarcodesResult` class represents the result of a barcode reading process. It provides access to information about the decoded barcodes, the source image, and any errors that occurred during the barcode reading process.

## Definition

*Namespace:* dynamsoft::dbr

*Assembly:* DynamsoftBarcodeReader

*Inheritance:* [CCapturedResultBase]({{ site.dcvb_cpp_api }}core/basic-structures/captured-result-base.html) -> CDecodedBarcodesResult

```cpp
class CDecodedBarcodesResult: public CCapturedResultBase
```

## Methods

| Method               | Description |
|----------------------|-------------|
| [`GetItemsCount`](#getitemscount) | Gets the number of barcode result items in the barcode reading result. |
| [`GetItem`](#getitem) | Gets the barcode result item at the specified index. |
| [`HasItem`](#hasitem) | Check if the barcode result item is present in the array.|
| [`RemoveItem`](#removeitem) | Remove a specific barcode result item from the result array.|
| [`Release`](#release) | Decreases the reference count of the `CDecodedBarcodesResult` object. |
| [`Retain`](#retain) | Increases the reference count of the `CDecodedBarcodesResult` object. |
| [`operator[]`](#operator)           | Gets a pointer to the `CBarcodeResultItem` object at the specified index.|
| [`AddItem`](#additem) | Adds a specific item to the array in the decoded barcodes result. |
| **Methods Inherited from [CCapturedResultBase]({{ site.dcvb_cpp_api }}core/basic-structures/captured-result-base.html):** | |
| [`GetOriginalImageHashId`]({{ site.dcvb_cpp_api }}core/basic-structures/captured-result-base.html#getoriginalimagehashid) | Gets the hash ID of the original image. |
| [`GetOriginalImageTag`]({{ site.dcvb_cpp_api }}core/basic-structures/captured-result-base.html#getoriginalimagetag) | Gets the tag of the original image. |
| [`GetRotationTransformMatrix`]({{ site.dcvb_cpp_api }}core/basic-structures/captured-result-base.html#getrotationtransformmatrix) | Gets the rotation transformation matrix of the original image relative to the rotated image. |
| [`GetErrorCode`]({{ site.dcvb_cpp_api }}core/basic-structures/captured-result-base.html#geterrorcode) | Gets the error code of the recognition result, if an error occurred. |
| [`GetErrorString`]({{ site.dcvb_cpp_api }}core/basic-structures/captured-result-base.html#geterrorstring) | Gets the error message of the recognition result, if an error occurred. |

### GetItemsCount

Gets the number of decoded barcode items in the barcode reading result.

```cpp
virtual int GetItemsCount() const = 0;
```

**Return value**

Returns the number of decoded barcode items in the barcode reading result.

### GetItem

Gets the decoded barcode result item at the specified index.

```cpp
virtual const CBarcodeResultItem* GetItem(int index) const = 0;
```

**Parameters**

`[in] index` The zero-based index of the barcode result item to retrieve.

**Return value**

Returns a pointer to the CBarcodeResultItem object at the specified index.

**See Also**

[CBarcodeResultItem]({{ site.dbr_cpp_api }}barcode-result-item.html)

### HasItem

Check if the barcode result item is present in the array.

```cpp
bool HasItem(const CBarcodeResultItem* item) const
```

**Parameters**

`[in] item` The specific item to check.

**Return value**

Returns a bool value indicating whether the item is present in the array or not.

**See Also**

[CBarcodeResultItem]({{ site.dbr_cpp_api }}barcode-result-item.html)

### RemoveItem

Remove a specific barcode result item from the result array.

```cpp
int RemoveItem(const CBarcodeResultItem* item)
```

**Parameters**

`[in] item` The specific item to remove.

**Return value**

Return value indicating whether the deletion was successful or not.

**See Also**

[CBarcodeResultItem]({{ site.dbr_cpp_api }}barcode-result-item.html)

### Release

Decreases the reference count of the `CDecodedBarcodesResult` object.

```cpp
virtual void Release() = 0;
```

### Retain

Increases the reference count of the `CDecodedBarcodesResult` object.

```cpp
virtual CDecodedBarcodesResult* Retain() = 0;
```

**Return value**

Returns an object of `CDecodedBarcodesResult`.

### operator[]

Gets a pointer to the `CBarcodeResultItem` object at the specified index.

```cpp
virtual const CBarcodeResultItem* operator[](int index) const = 0;
```

**Parameters**

`[in] index` The index of the barcode result item to retrieve.

**Return value**

Returns a pointer to the `CBarcodeResultItem` object at the specified index.

**See Also**

[CBarcodeResultItem]({{ site.dbr_cpp_api }}barcode-result-item.html)

### AddItem

Adds a specific item to the array in the parsed result.

```cpp
virtual int AddItem(const CBarcodeResultItem* item) = 0;
```

**Parameters**

`[in] item` The specific item to be added.

**Return value**

Returns an error code. Zero indicates success.

**See Also**

[CBarcodeResultItem]({{ site.dbr_cpp_api }}barcode-result-item.html)
