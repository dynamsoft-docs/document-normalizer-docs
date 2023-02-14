---
layout: default-layout
title: Dynamsoft Document Normalizer iOS API Reference - NormalizedImageResult Class
description: This page shows the NormalizedImageResult Class of Dynamsoft Document Normalizer for iOS SDK.
keywords: NormalizedImageResult, class, api reference, ios
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# iNormalizedImageResult

Stores the detected quad result.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface iNormalizedImageResult
```
2. 
```swift
class iNormalizedImageResult : NSObject
```

| Attribute | Type | Descriptions |
| --------- | ---- | ------------ |
| [`image`](#image) | [`iImageData*`](image-data.md) | The normalized image in iImageData structure. |

## image

The location of the detected quad result.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
iImageData* image;
```
2. 
```swift
var image: iImageData { get set }
```
