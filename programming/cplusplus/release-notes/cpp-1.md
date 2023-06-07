---
layout: default-layout
title: Release Notes for C++ Edition - v1.x
description: This is the release notes page of Dynamsoft Document Normalizer SDK C++ Edition for version 1.x.
keywords: release notes, c++, 
needGenerateH3Content: false
---

# Release Notes for C++ Edition - v1.x

## 1.0.30 (06/07/2023)

### Fixed

- Fixed a bug where document boundary might not be detected when scanning from the video streaming.

## 1.0.20 (02/02/2023)

### Fixed

- Fixed a bug where the colours of binarized images might be inverted when using [`LEM_MARGIN_BASED`]({{site.parameters}}reference/line-extraction-modes.html) mode for `LineExtractionModes`.

## 1.0.10 (09/29/2022)

### New

- Added a new method [`SaveToFile`]({{ site.cpp_api }}normalized-image-result.html#savetofile) in class `CNormalizedImageResult` to support saving the normalized image as a BMP/JPEG/PNG/PDF file.
- Added PDF as a supported file format of method [`Normalize`]({{ site.cpp_api }}document-normalizer-normalizing.html#normalize) and [`DetectQuad`]({{ site.cpp_api }}document-normalizer-normalizing.html#detectquad).
- Added a new method [`GetOrientation`]({{ site.cpp_api }}image-data.html#getorientation) in class `CImageData`.
- Added error code `DMERR_IMAGE_ORIENTATION_INVALID`.

### Changed

- Updated [ErrorCode]({{ site.enumerations }}error-code.html?src=cpp)
  - Change the value of `DDNERR_CONTENT_NOT_FOUND` from -10056 to -50001.
  - Renamed `DDNERR_QUADRILATERAL_INVALID` to `DMERR_QUADRILATERAL_INVALID`.

### Removed

- Removed method `SaveImageDataToFile` from class `CDocumentNormalizer`.

## 1.0.0 (06/21/2022)

### Highlights

{%- include release-notes/product-highlight-1.0.0.md -%}
