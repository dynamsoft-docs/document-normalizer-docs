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

## 1.0.10 (11/04/2022)

### Highlights

{%- include release-notes/product-highlight-1.0.0.md -%}

## 1.0.11 (12/01/2022)

### Fixed

* Fixed a bug where camera will be detected when an instance of `DocumentNormalizer` is created.
* Fixed a bug where the normalized image may have black borders when setting `ColourMode` of `NormalizerParameter` to `ICM_BINARY`.

### Changed

* Reduced the size of `core.js`.
