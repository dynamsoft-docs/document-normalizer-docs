---
layout: default-layout
title: Dynamsoft Document Normalizer for xamarin SDK - Release Notes
description: This is the release notes page of Dynamsoft Document Normalizer for xamarin SDK.
keywords: release notes, xamarin, 
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
---

# Release Notes for Xamarin SDK

## 1.0.4 (06/07/2023)

### Fixed

- Fixed a bug where document boundary might not be detected when scanning from the video streaming.

## 1.0.3 (05/24/2023)

### Fixed

- Fixed a `DetectedQuadResult` display bug. The edge of a quadrilateral might be wrongly linked when the `ImageEditorView`
is reopened.

## 1.0.2 (02/15/2023)

### Fixed

- Fixed a crash bug where might happen when triggering method [`toImageSource`](../api-reference/image-data.md#toimagesource).

## 1.0.1 (11/11/2022)

### Fixed

- Fixed a crash bug when triggering [`getSelectedQuadResult`](../api-reference/image-editor-view.md#getselectedquadresult) on `DCVImageEditorView` without selecting any quad.  

## 1.0.0 (10/28/2022)

### Highlights

{%- include release-notes/product-highlight-1.0.0.md -%}
