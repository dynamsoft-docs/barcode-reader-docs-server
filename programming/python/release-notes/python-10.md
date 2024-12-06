---
layout: default-layout
title: Release Notes v10.x - Dynamsoft Barcode Reader SDK Python Edition
description: This is the release notes page of Dynamsoft Barcode Reader SDK Python Edition v10.x.
keywords: release notes, python
needGenerateH3Content: false
---

# Release Notes for Python Edition - 10.x

## 10.5.2100 (12/05/2024)

### New

- Added `Intermediate Results`, completing DCV's feature set with real-time feedback and interactivity. Learn more about [Bidirectional Interactivity with Intermediate Results]({{ site.dcvb_architecture}}index.html#bidirectional-interactivity-with-intermediate-results).
- Added support for Python 3.13.

### Fixed

- Removed the `static dependency on NumPy`, allowing users to import it only when needed.

## 10.4.2100 (11/07/2024)

### New

- Added support for `numpy.ndarray` image type in the `capture` interface.

### Improved

- Optimized the usage of list type member variables, allowing modification of individual objects within the list without needing to reassign the entire list.
- Improved the usage of `EnumPresetTemplate` and `EnumBarcodeFormat`, no longer requiring `.value` for accessing enum members.

### Fixed

- Fixed a bug where initializing `FileImageTag` would raise a `TypeError` exception.

## 10.4.2000 (10/10/2024)

### Highlights

{%- include release-notes/python-highlight-10.4.2000.md -%}
