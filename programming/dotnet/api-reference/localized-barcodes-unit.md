---
layout: default-layout
title: LocalizedBarcodesUnit Class - Dynamsoft Barcode Reader .NET Edition API Reference
description: This page shows LocalizedBarcodesUnit class definition of Dynamsoft Barcode Reader SDK .NET Edition.
keywords: GetCount, GetLocalizedBarcode, AddLocalizedBarcode, RemoveAllLocalizedBarcodes, RemoveLocalizedBarcode, SetLocalizedBarcode, LocalizedBarcodesUnit, api reference
---
# LocalizedBarcodesUnit Class

The `LocalizedBarcodesUnit` class represents a unit that contains localized barcodes unit. It inherits from the `IntermediateResultUnit` class.

## Definition

*Namespace:* Dynamsoft.DBR.intermediate_results


*Inheritance:* [IntermediateResultUnit]({{ site.dcvb_dotnet_api }}core/intermediate-results/intermediate-result-unit.html) -> LocalizedBarcodesUnit

```csharp
class LocalizedBarcodesUnit : IntermediateResultUnit, IEnumerable<LocalizedBarcodeElement>
```

## Methods

| Method                            | Description |
|-----------------------------------|-------------|
| [`AddLocalizedBarcode`](#addlocalizedbarcode)           | Adds a localized barcode.|
| [`GetCount`](#getcount)           | Gets the number of localized barcodes in the unit.|
| [`GetLocalizedBarcode`](#getlocalizedbarcode)           | Gets a specific localized barcode element.|
| [`GetLocalizedBarcodes`](#getlocalizedbarcodes)           | Gets all localized barcode elements.|
| [`RemoveAllLocalizedBarcodes`](#removealllocalizedbarcodes)           | Removes all the localized barcodes.|
| [`RemoveLocalizedBarcode`](#removelocalizedbarcode)           | Removes a localized barcode at the specified index.|
| [`SetLocalizedBarcode`](#setlocalizedbarcode)           | Sets a localized barcode at the specified index.|

### Inherited Methods

Checkout inherited methods from [IntermediateResultUnit]({{ site.dcvb_dotnet_api }}core/intermediate-results/intermediate-result-unit.html) for more details.

### AddLocalizedBarcode

Adds a localized barcode.

```csharp
int AddLocalizedBarcode(LocalizedBarcodeElement localizedBarcode, double[] matrixToOriginalImage = null)
```

**Parameters**

`localizedBarcode` The localized barcode element to be added.

`matrixToOriginalImage` The matrix to original image.

**Return value**

Returns 0 if successful, otherwise returns a negative value.

**See Also**

[LocalizedBarcodeElement]({{ site.dbr_dotnet_api }}localized-barcode-element.html)

### GetCount

Gets the number of localized barcodes in the unit.

```csharp
int GetCount()
```

**Return value**

Returns the number of localized barcodes in the unit.


### GetLocalizedBarcode

Gets a specific localized barcode element.

```csharp
LocalizedBarcodeElement GetLocalizedBarcode(int index)
```

**Parameters**

`[in] index` The index of the localized barcode element to retrieve.

**Return value**

Returns the localized barcode element at the specified index.

**See Also**

[LocalizedBarcodeElement]({{ site.dbr_dotnet_api }}localized-barcode-element.html)

### GetLocalizedBarcodes

Gets all localized barcode elements.

```csharp
LocalizedBarcodeElement[] GetLocalizedBarcodes()
```

**Return value**

Returns all the localized barcode elements.

**See Also**

[LocalizedBarcodeElement]({{ site.dbr_dotnet_api }}localized-barcode-element.html)

### RemoveAllLocalizedBarcodes

Removes all the localized barcodes.

```csharp
void RemoveAllLocalizedBarcodes()
```

### RemoveLocalizedBarcode

Removes a localized barcode at the specified index.

```csharp
int RemoveLocalizedBarcode(int index)
```

**Parameters**

`index` The index of the localized barcode.

**Return value**

Returns 0 if successful, otherwise returns a negative value.

### SetLocalizedBarcode

Sets a localized barcode at the specified index.

```csharp
int SetLocalizedBarcode(int index, LocalizedBarcodeElement localizedBarcode, double[] matrixToOriginalImage = null)
```

**Parameters**

`index` The index of the localized barcode.

`localizedBarcode` The localized barcode element to be set.

`matrixToOriginalImage` The matrix to original image.

**Return value**

Returns 0 if successful, otherwise returns a negative value.

**See Also**

[LocalizedBarcodeElement]({{ site.dbr_dotnet_api }}localized-barcode-element.html)
