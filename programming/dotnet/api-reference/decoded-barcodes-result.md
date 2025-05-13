---
layout: default-layout
title: DecodedBarcodesResult Class - Dynamsoft Barcode Reader Module .NET Edition API Reference
description: Definition of DecodedBarcodesResult class in Dynamsoft Barcode Reader Module .NET Edition.
keywords: GetOriginalImageHashId, GetItemsCount, GetErrorCode, DecodedBarcodesResult, api reference
---
# DecodedBarcodesResult Class

The `DecodedBarcodesResult` class represents the result of a barcode reading process. It provides access to information about the decoded barcodes, the source image, and any errors that occurred during the barcode reading process.

## Definition

*Namespace:* Dynamsoft.DBR

*Inheritance:* [CapturedResultBase]({{ site.dcv_dotnet_api }}core/basic-classes/captured-result-base.html) -> DecodedBarcodesResult

```csharp
public class DecodedBarcodesResult : CapturedResultBase, IEnumerable<BarcodeResultItem>
```

## Methods

| Method               | Description |
|----------------------|-------------|
| [`GetItems`](#getitems) | Gets all the barcode result items. |
| [`GetItemsCount`](#getitemscount) | Gets the number of barcode result items in current result object. |
| [`GetItem`](#getitem) | Gets a specific barcode result item. |

### GetItems

Gets all the decoded barcode result items.

```csharp
BarcodeResultItem[] GetItems()
```

**Return Value**

Returns a `BarcodeResultItem` array.

**See Also**

[BarcodeResultItem]({{ site.dbr_dotnet_api }}barcode-result-item.html)

### GetItemsCount

Gets the number of barcode result items in current result object.

```csharp
int GetItemsCount()
```

**Return value**

Returns the number of barcode result items in current result object.

### GetItem

Gets a specific barcode result item.

```csharp
BarcodeResultItem GetItem(int index)
```

**Parameters**

`[in] index` The index of specific barcode result item.

**Return value**

Returns the specific barcode result item.

**See Also**

[BarcodeResultItem]({{ site.dbr_dotnet_api }}barcode-result-item.html)
