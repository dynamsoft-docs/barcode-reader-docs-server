---
layout: default-layout
title: CBarcodeDetails Class - Dynamsoft Barcode Reader C++ Edition API Reference
description: API reference for the CBarcodeDetails abstract base class in Dynamsoft Barcode Reader C++ Edition, which is the parent class for all barcode-format-specific detail classes.
keywords: CBarcodeDetails, api reference
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
