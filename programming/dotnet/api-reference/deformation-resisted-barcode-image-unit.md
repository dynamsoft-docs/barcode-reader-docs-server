---
layout: default-layout
title: DeformationResistedBarcodeImageUnit Class - Dynamsoft Barcode Reader .NET Edition API Reference
description: This page shows DeformationResistedBarcodeImageUnit class definition of Dynamsoft Barcode Reader SDK .NET Edition.
keywords: GetDeformationResistedBarcode, SetDeformationResistedBarcode, DeformationResistedBarcodeImageUnit, api reference
---
# DeformationResistedBarcodeImageUnit Class

The `DeformationResistedBarcodeImageUnit` class represents a unit that contains deformation resisted barcode image data. It inherits from the `IntermediateResultUnit` class.

## Definition

*Namespace:* Dynamsoft.DBR.intermediate_results


*Inheritance:* [IntermediateResultUnit]({{ site.dcvb_dotnet_api }}core/intermediate-results/intermediate-result-unit.html) -> DeformationResistedBarcodeImageUnit

```csharp
class DeformationResistedBarcodeImageUnit : IntermediateResultUnit
```

## Methods

| Method                            | Description |
|-----------------------------------|-------------|
| [`GetDeformationResistedBarcode`](#getdeformationresistedbarcode) | Gets the deformation resisted barcode object.|
| [`SetDeformationResistedBarcode`](#setdeformationresistedbarcode) | Sets the deformation resisted barcode object.|

### Inherited Methods

Checkout inherited methods from [IntermediateResultUnit]({{ site.dcvb_dotnet_api }}core/intermediate-results/intermediate-result-unit.html) for more details.

### GetDeformationResistedBarcode

Gets the deformation resisted barcode object.

```csharp
DeformationResistedBarcode GetDeformationResistedBarcode()
```

**Return value**

Returns an instance of `DeformationResistedBarcode`.

**See Also**

[DeformationResistedBarcode]({{ site.dbr_dotnet_api }}deformation-resisted-barcode.html)

### SetDeformationResistedBarcode

Sets the deformation resisted barcode object.

```csharp
int SetDeformationResistedBarcode(DeformationResistedBarcode barcode, double[] matrixToOriginalImage = null)
```

**Parameters**

`[in] barcode` The deformation resisted barcode object.

`matrixToOriginalImage` The matrix to original image.

**Return value**

Returns 0 if successful, otherwise returns a negative value.

**See Also**

[DeformationResistedBarcode]({{ site.dbr_dotnet_api }}deformation-resisted-barcode.html)
