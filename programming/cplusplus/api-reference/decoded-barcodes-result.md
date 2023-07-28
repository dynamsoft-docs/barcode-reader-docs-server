---
layout: default-layout
title: CDecodedBarcodesResult Class
description: This page shows CDecodedBarcodesResult class definition of Dynamsoft Barcode Reader SDK C++ Edition.
keywords: GetSourceImageHashId, GetCount, GetErrorCode, CDecodedBarcodesResult, api reference
permalink: /programming/cplusplus/api-reference/decoded-barcodes-result.html
---
# CDecodedBarcodesResult Class

The `CDecodedBarcodesResult` class represents the result of a barcode reading process. It provides access to information about the decoded barcodes, the source image, and any errors that occurred during the barcode reading process.

## Definition

*Namespace:* dynamsoft::dbr

*Assembly:* DynamsoftBarcodeReader

```cpp
class CDecodedBarcodesResult
```

## Methods

| Method               | Description |
|----------------------|-------------|
| [`GetSourceImageHashId`](#getsourceimagehashid) | Gets the hash ID of the source image. |
| [`GetSourceImageTag`](#getsourceimagetag) | Gets the tag of the source image. |
| [`GetCount`](#getcount) | Gets the number of barcode result items in the barcode reading result. |
| [`GetItem`](#getitem) | Gets the barcode result item at the specified index. |
| [`HasItem`](#hasitem) | Check if the barcode result item is present in the array.|
| [`RemoveItem`](#removeitem) | Remove a specific barcode result item from the result array.|
| [`GetRotationTransformMatrix`](#getrotationtransformmatrix) | Get the rotation transformation matrix of the original image relative to the rotated image.|
| [`GetErrorCode`](#geterrorcode) | Gets the error code of the barcode reading result, if an error occurred. |
| [`GetErrorString`](#geterrorstring) | Gets the error message of the barcode reading result, if an error occurred. |

### GetSourceImageHashId

Gets the hash ID of the source image.

```cpp
virtual const char* GetSourceImageHashId() const = 0;
```

**Return value**

Returns a pointer to a null-terminated string containing the hash ID of the source image.

### GetSourceImageTag

Gets the tag of the source image.

```cpp
virtual const CImageTag* GetSourceImageTag() const = 0;
```

**Return value**

Returns a pointer to a CImageTag object representing the tag of the source image.

### GetCount

Gets the number of decoded barcode items in the barcode reading result.

```cpp
virtual int GetCount() const = 0;
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

### HasItem

Check if the barcode result item is present in the array.

```cpp
bool HasItem(const CBarcodeResultItem* item) const
```

**Parameters**

`[in] item` The specific item to check.

**Return value**

Returns a bool value indicating whether the item is present in the array or not.

### RemoveItem

Remove a specific barcode result item from the result array.

```cpp
int RemoveItem(const CBarcodeResultItem* item)
```

**Parameters**

`[in] item` The specific item to remove.

**Return value**

Return value indicating whether the deletion was successful or not.

### GetRotationTransformMatrix

Get the rotation transformation matrix of the original image relative to the rotated image.

```cpp
void GetRotationTransformMatrix(double matrix[9]) const;
```

**Parameters**

`[out] matrix` A double array which represents the rotation transform matrix.

### GetErrorCode

Gets the error code of the barcode reading result, if an error occurred.

```cpp
virtual int GetErrorCode() const = 0;
```

**Return value**

Returns the error code of the barcode reading result, or 0 if no error occurred.

### GetErrorString

Gets the error message of the barcode reading result, if an error occurred.

```cpp
virtual const char* GetErrorString() const = 0;
```

**Return value**

Returns a pointer to a null-terminated string containing the error message of the barcode reading result, or a pointer to an empty string if no error occurred.
