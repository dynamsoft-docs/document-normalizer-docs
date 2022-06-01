---
layout: default-layout
title: Dynamsoft Document Normalizer iOS API Reference - iDetectedQuadResult Class
description: This page shows the iDetectedQuadResult Class of Dynamsoft Document Normalizer for iOS SDK.
keywords: iDetectedQuadResult, class, api reference, ios
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# iDetectedQuadResult

Stores the detected quad result.

```objc
@interface iDetectedQuadResult
```

| Attribute | Type | Descriptions |
| --------- | ---- | ------------ |
| [`location`](#location) | [`iQuadrilateral*`](quadrilateral.md) | The location of the detected quad result. |
| [`confidenceAsDocumentBoundary`](#confidenceasdocumentboundary) | *int* | The confidence as document boundary. |

## location

The location of the detected quad result.

```objc
iQuadrilateral* location;
```

## confidenceAsDocumentBoundary

The confidence as document boundary.

```objc
NSInteger confidenceAsDocumentBoundary;
```
