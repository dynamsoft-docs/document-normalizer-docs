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

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
iQuadrilateral* location;
```
2. 
```swift
var location: iQuadrilateral { get set }
```


## confidenceAsDocumentBoundary

The confidence as document boundary.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
NSInteger confidenceAsDocumentBoundary;
```
2. 
```swift
var confidenceAsDocumentBoundary: Int { get set }
```
