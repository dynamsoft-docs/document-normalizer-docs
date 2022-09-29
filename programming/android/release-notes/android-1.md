---
layout: default-layout
title: Dynamsoft Document Normalizer for Android SDK - Release Notes v7.6.1 and below
description: This is the release notes page of Dynamsoft Document Normalizer for Android SDK v7.6.1 and below.
keywords: release notes, android, 
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
---

# Release Notes for Android SDK - 1.0.0

## 1.0.10 (09/29/2022)

### New

- Added a new method [`setImageSource`](../api-reference/document-normalizer-video.md#setimagesource) in `DocumentNormalizer` class to set up image source.
- Added a new method [`saveToFile`](../api-reference/normalized-image-result.md#savetofile) in class `NormalizedImageResult` to support saving the normalized image as a BMP/JPEG/PNG/PDF file.
- Added a new property [`orientation`](../api-reference/image-data.md#orientation) in class `ImageData`.

### Changed

- Updated [ErrorCode](../../enumerations/error-code.md)
  - Added `DMERR_IMAGE_ORIENTATION_INVALID` (-10060).
  - Change the value of `DDNERR_CONTENT_NOT_FOUND` from -10056 to -50001.
  - Renamed `DDNERR_QUADRILATERAL_INVALID` to `DMERR_QUADRILATERAL_INVALID`.

### Deprecated

- Deprecated `setCameraEnhancer`.

## 1.0.0 (06/21/2022)

### Highlights

{%- include release-notes/product-highlight-1.0.0.md -%}
