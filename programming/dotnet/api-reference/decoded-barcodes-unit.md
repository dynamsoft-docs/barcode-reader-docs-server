---
layout: default-layout
title: DecodedBarcodesUnit Class - Dynamsoft Barcode Reader .NET Edition API Reference
description: This page shows DecodedBarcodesUnit class definition of Dynamsoft Barcode Reader SDK .NET Edition.
keywords: GetCount, GetDecodedBarcode, RemoveAllDecodedBarcodes, SetDecodedBarcode, DecodedBarcodesUnit, api reference
---
# DecodedBarcodesUnit Class

The `DecodedBarcodesUnit` class represents a unit that contains decoded barcode elements. It inherits from the `IntermediateResultUnit` class.

## Definition

*Namespace:* Dynamsoft.DBR.intermediate_results


*Inheritance:* [IntermediateResultUnit]({{ site.dcvb_dotnet_api }}core/intermediate-results/intermediate-result-unit.html) -> DecodedBarcodesUnit

```csharp
class DecodedBarcodesUnit : IntermediateResultUnit, IEnumerable<DecodedBarcodeElement>
```

## Methods

| Method                            | Description |
|-----------------------------------|-------------|
| [`GetCount`](#getcount)           | Gets the number of decoded barcodes in the unit.|
| [`GetDecodedBarcode`](#getdecodedbarcode)           | Gets the `DecodedBarcodeElement` object at the specified index.|
| [`GetDecodedBarcodes`](#getdecodedbarcodes)           | Gets all the `DecodedBarcodeElement` objects.|
| [`RemoveAllDecodedBarcodes`](#removealldecodedbarcodes)           | Removes all the decoded barcodes in the unit.|
| [`SetDecodedBarcode`](#setdecodedbarcode)           | Sets the decoded barcode.|

### Inherited Methods

Checkout inherited methods from [IntermediateResultUnit]({{ site.dcvb_dotnet_api }}core/intermediate-results/intermediate-result-unit.html) for more details.

### GetCount

Gets the number of decoded barcodes in the unit.

```csharp
int GetCount()
```

**Return value**

Returns the number of decoded barcodes in the unit.

### GetDecodedBarcode

Gets the `DecodedBarcodeElement` object at the specified index.

```csharp
DecodedBarcodeElement GetDecodedBarcode(int index)
```

**Parameter**

`[in] index` The index of the desired `DecodedBarcodeElement` object.

**Return value**

Returns the `DecodedBarcodeElement` object at the specified index.

**See Also**

[DecodedBarcodeElement]({{ site.dbr_dotnet_api }}decoded-barcode-element.html)

### GetDecodedBarcodes

Gets all the `DecodedBarcodeElement` objects.

```csharp
DecodedBarcodeElement[] GetDecodedBarcodes()
```

**Return value**

Returns all the `DecodedBarcodeElement` objects.

**See Also**

[DecodedBarcodeElement]({{ site.dbr_dotnet_api }}decoded-barcode-element.html)

### RemoveAllDecodedBarcodes

Removes all the decoded barcodes in the unit.

```csharp
void RemoveAllDecodedBarcodes()
```

### SetDecodedBarcode

Sets the decoded barcode.

```csharp
int SetDecodedBarcode(DecodedBarcodeElement decodedBarcodeElement, double[] matrixToOriginalImage = null)
```

**Parameters**

`decodedBarcodeElement` The decoded barcode element.

`matrixToOriginalImage` The matrix to original image.

**Return value**

Returns 0 if successful, otherwise returns a negative value.

**See Also**

[DecodedBarcodeElement]({{ site.dbr_dotnet_api }}decoded-barcode-element.html)
