---
layout: default-layout
title: Dynamsoft Document Normalizer Android API Reference - DetectedQuadResult Class
description: This page shows the DetectedQuadResult Class of Dynamsoft Document Normalizer for Android SDK.
keywords: DetectedQuadResult, class, api reference, android
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# DetectedQuadResult

Stores the detected quad result.

```java
class com.dynamsoft.ddn.DetectedQuadResult;
```

| Attribute | Type | Descriptions |
| --------- | ---- | ------------ |
| [`location`](#location) | [`Quadrilateral`](quadrilateral.md) | The location of the detected quad result. |
| [`confidenceAsDocumentBoundary`](#confidenceasdocumentboundary) | *int* | The confidence as document boundary. |

## location

The location of the detected quad result.

```java
Quadrilateral location;
```

## confidenceAsDocumentBoundary

The confidence as document boundary.

```java
int confidenceAsDocumentBoundary;
```
