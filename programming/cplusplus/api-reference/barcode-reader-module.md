---
layout: default-layout
title: CBarcodeReaderModule Class - Dynamsoft Barcode Reader C++ Edition API Reference
description: API reference for the CBarcodeReaderModule class in Dynamsoft Barcode Reader C++ Edition, providing module-level utilities such as version retrieval and factory methods for barcode elements.
keywords: barcode reader module, c++
needAutoGenerateSidebar: true
needGenerateH3Content: true
---

# CBarcodeReaderModule

The `CBarcodeReaderModule` class defines general functions in the barcode reader module.

## Definition

*Namespace:* dynamsoft::dbr

*Assembly:* DynamsoftBarcodeReader

```cpp
class CBarcodeReaderModule 
```

## Methods

| Method                                                    | Description                                        |
| --------------------------------------------------------- | -------------------------------------------------- |
| [GetVersion](#getversion)                                     | Returns the version of the barcode reader module. |
| [CreateDecodedBarcodeElement](#createdecodedbarcodeelement) | Create a `CDecodedBarcodeElement` object. |
| [CreateLocalizedBarcodeElement](#createlocalizedbarcodeelement) | Create a `CLocalizedBarcodeElement` object. |

## GetVersion

Returns the version of the barcode reader module.

```cpp
static const char* GetVersion();
```

**Parameters**

None.

**Return Value**

Returns a const char pointer representing the version of the barcode reader module.

## CreateDecodedBarcodeElement

Create a `CDecodedBarcodeElement` object.

```cpp
static intermediate_results::CDecodedBarcodeElement* CreateDecodedBarcodeElement();
```

**Return Value**

Returns an object of `CDecodedBarcodeElement`.

**See Also**

[CDecodedBarcodeElement]({{ site.dbr_cpp_api }}decoded-barcode-element.html)

## CreateLocalizedBarcodeElement

Create a `CLocalizedBarcodeElement` object.

```cpp
static intermediate_results::CLocalizedBarcodeElement* CreateLocalizedBarcodeElement();
```

**Return Value**

Returns an object of `CLocalizedBarcodeElement`.

**See Also**

[CLocalizedBarcodeElement]({{ site.dbr_cpp_api }}localized-barcode-element.html)
