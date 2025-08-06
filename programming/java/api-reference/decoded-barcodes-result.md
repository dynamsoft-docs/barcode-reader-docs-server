---
layout: default-layout
title: DecodedBarcodesResult Class - Dynamsoft Barcode Reader Java Edition API Reference
description: Definition of DecodedBarcodesResult class in Dynamsoft Barcode Reader Java Edition.
keywords: getItemsCount, getItem, getItems, DecodedBarcodesResult, api reference
---
# DecodedBarcodesResult Class

The `DecodedBarcodesResult` class represents the result of a barcode reading process. It provides access to information about the decoded barcodes, the source image, and any errors that occurred during the barcode reading process.

## Definition

*Package:* com.dynamsoft.dbr

*Inheritance:* [CapturedResultBase]({{ site.dcvb_java_api }}core/basic-classes/captured-result-base.html) -> DecodedBarcodesResult

```java
public class DecodedBarcodesResult extends CapturedResultBase
```

## Methods

| Method               | Description |
|----------------------|-------------|
| [`getItemsCount`](#getitemscount) | Gets the count of decoded barcode result items. |
| [`getItem`](#getitem) | Gets the decoded barcode result item at the specified index. |
| [`getItems`](#getitems) | Gets all the decoded barcode result items. |

## Method Details

### getItemsCount

Gets the count of decoded barcode result items.

```java
public int getItemsCount()
```

**Return Value**

Returns the count of decoded barcode result items.

### getItem

Gets the decoded barcode result item at the specified index.

```java
public BarcodeResultItem getItem(int index)
```

**Parameters**

`index`: The index of the result item to retrieve.

**Return Value**

Returns the BarcodeResultItem at the specified index.

### getItems

Gets all the decoded barcode result items.

```java
public BarcodeResultItem[] getItems()
```

**Return Value**

Returns an array of all BarcodeResultItem objects.

**See Also**

[BarcodeResultItem]({{ site.dbr_java_api }}barcode-result-item.html)
