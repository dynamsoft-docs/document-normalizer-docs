---
layout: default-layout
title: iOS iRegionDefinition Class - Dynamsoft Document Normalizer Documents
description: This page shows the iRegionDefinition Class of Dynamsoft Camera Enhancer for iOS SDK.
keywords: iRegionDefinition, class, api reference, objective-c, oc, swift
needAutoGenerateSidebar: true
noTitleIndex: true
---

# Class iRegionDefinition

Stores the region information.  

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface iRegionDefinition
```
2. 
```swift
class iRegionDefinition : NSObject
```

| Attribute | Type | Descriptions |
|---------- | ---- | ------------ |
| [`regionTop`](#regiontop) | *NSInteger* | The top-most coordinate or percentage of the region. |
| [`regionLeft`](#regionleft) | *NSInteger* | The Left-most coordinate or percentage of the region. |
| [`regionRight`](#regionright) | *NSInteger* | The Right-most coordinate or percentage of the region. |
| [`regionBottom`](#regionbottom) | *NSInteger* | The Bottom-most coordinate or percentage of the region. |
| [`regionMeasuredByPercentage`](#regionmeasuredbypercentage) | *NSInteger* | Sets whether or not to use percentage to measure the region size. |

## regionTop

The top-most coordinate or percentage of the region.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
NSInteger regionTop
```
2. 
```swift
var regionTop: Int { get set }
```

**Value Range**

regionMeasuredByPercentage = 0: [0, 0x7fffffff]  
regionMeasuredByPercentage = 1: [0, 100]  

**Default Value**

0

&nbsp;

## regionLeft

The left-most coordinate or percentage of the region.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
NSInteger regionLeft
```
2. 
```swift
var regionLeft: Int { get set }
```

**Value Range**

regionMeasuredByPercentage = 0: [0, 0x7fffffff]  
regionMeasuredByPercentage = 1: [0, 100]  

**Default Value**

0

&nbsp;

## regionRight

The right-most coordinate or percentage of the region.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
NSInteger regionRight
```
2. 
```swift
var regionRight: Int { get set }
```

**Value Range**

regionMeasuredByPercentage = 0: [0, 0x7fffffff]
regionMeasuredByPercentage = 1: [0, 100]

**Default Value**

0

&nbsp;

## regionBottom

The bottom-most coordinate or percentage of the region.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
NSInteger regionBottom
```
2. 
```swift
var regionButtom: Int { get set }
```

**Value Range**

regionMeasuredByPercentage = 0: [0, 0x7fffffff]  
regionMeasuredByPercentage = 1: [0, 100]  

**Default Value**

0

&nbsp;

## regionMeasuredByPercentage

Sets whether or not to use percentage to measure the region size.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
NSInteger regionMeasuredByPercentage
```
2. 
```swift
var regionMeasuredByPercentage: Int { get }
```

**Value Range**

[0, 1]

**Default Value**

0

**Remarks**

When it's set to 1, the values of Top, Left, Right, Bottom indicate percentage (from 0 to 100); Otherwise, they indicate coordinates. 0: not by percentage 1: by percentage.
