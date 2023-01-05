---
layout: default-layout
title: Dynamsoft Document Normalizer for JavaScript SDK - Release Notes
description: This is the release notes page of Dynamsoft Document Normalizer for JavaScript SDK v1.0.0.
keywords: release notes, javascript
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
---

# Release Notes for JavaScript SDK

## 1.0.12 (01/05/2023)

### Improved

* Added a second parameter `makeACopy` to the method [`detectQuad`](../api-reference/normalize.md#detectquad) which, when set to `true`, means the source data to process will stay valid for later processing. This is only effective when the source data is of the type DCEFrame or DSImage.

## 1.0.11 (11/30/2022)

### Fixed

* Fixed a bug where the camera permission will be requested when an instance of `DocumentNormalizer` is created.
* Fixed a bug where the normalized image may have black borders when setting `ColourMode` of `NormalizerParameter` to `ICM_BINARY`.

### Improved

* Reduced the size of `core.js`.

## 1.0.10 (11/04/2022)

### Highlights

{%- include release-notes/product-highlight-1.0.0.md -%}

