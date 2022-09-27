---
layout: default-layout
title: Release Notes for C++ Edition - v1.x
description: This is the release notes page of Dynamsoft Document Normalizer SDK C++ Edition for version 1.x.
keywords: release notes, c++, 
needGenerateH3Content: false
---

# Release Notes for C++ Edition - v1.x

## 1.0.10 (09/29/2022)

### New

- Added a new method [`SaveToFile`](../api-reference/document-normalizer-result.md#savetofile) in class `CNormalizedImageResult` to support saving the normalized image as a BMP/JPEG/PNG/PDF file.
- Added PDF as a supported file format of method [`Normalize`](../api-reference/document-normalizer-normalizing.md#normalize) and [`DetectQuad`](../api-reference/document-normalizer-normalizing.md#detectquad).
- Added a new method [`GetOrientation`](../api-reference/image-data.md#getorientation) in class `CImageData`.

### Changed

- Updated [ErrorCode](../../enumerations/error-code.md)
  - Added `DMERR_IMAGE_ORIENTATION_INVALID` (-10060).
  - Change the value of `DDNERR_CONTENT_NOT_FOUND` from -10056 to -50001.
  - Renamed `DDNERR_QUADRILATERAL_INVALID` to `DMERR_QUADRILATERAL_INVALID`.

### Removed

- Removed method `SaveImageDataToFile` from class `CDocumentNormalizer`.

## 1.0.0 (06/21/2022)

### Highlights

{%- include release-notes/product-highlight-1.0.0.md -%}
