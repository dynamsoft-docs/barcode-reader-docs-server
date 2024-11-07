---
layout: default-layout
title: Release Notes v10.x - Dynamsoft Barcode Reader SDK Python Edition
description: This is the release notes page of Dynamsoft Barcode Reader SDK Python Edition v10.x.
keywords: release notes, python
needGenerateH3Content: false
---

# Release Notes for Python Edition - 10.x

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
