---
layout: default-layout
title: Dynamsoft Document Normalizer iOS API Reference - DocumentNormalizer General Methods
description: This page shows DocumentNormalizer general methods of Dynamsoft Document Normalizer for iOS SDK.
keywords: getVersion, general methods, DocumentNormalizer, api reference, ios
needAutoGenerateSidebar: true
noTitleIndex: true
---

# General Methods

  | Method               | Description |
  |----------------------|-------------|
  | [`getVersion`](#getversion) | Get version information of SDK.|

  ---

## getVersion

Get version information of SDK.

```objc
+(NSString*)getVersion
```

**Return Value**

The version information string.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
NSString* str = [DynamsoftDocumentNormalizer getVersion];
```
2. 
```swift
let str = DynamsoftDocumentNormalizer.getVersion()
```
