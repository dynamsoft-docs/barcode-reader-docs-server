---
layout: default-layout
title: CBarcodeDetails Class - Dynamsoft Barcode Reader C++ Edition API Reference
description: This page shows CBarcodeDetails class definition of Dynamsoft Barcode Reader SDK C++ Edition.
keywords: CBarcodeDetails, api reference
permalink: /programming/cplusplus/api-reference/barcode-details.html
---
# CBarcodeDetails

The `CBarcodeDetails` class represents the details of a barcode. It is an abstract base class.

## Definition

*Namespace:* dynamsoft::dbr

*Assembly:* DynamsoftBarcodeReader

```cpp
class CBarcodeDetails
```

## Methods

| Method               | Description |
|----------------------|-------------|
| [`~CBarcodeDetails`](#cbarcodedetails) | Destructor. |

### ~CBarcodeDetails

Destructor.

```cpp
virtual ~CBarcodeDetails(){};
```

**Remarks**

This is a pure virtual destructor. This means that this class cannot be instantiated on its own, but must be subclassed.
