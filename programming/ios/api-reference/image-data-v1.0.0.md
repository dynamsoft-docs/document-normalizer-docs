---
layout: default-layout
title: Dynamsoft Core Objective-C & Swift Class - iImageData
description: This page shows the iImageData class of Dynamsoft Core for iOS SDK.
keywords: iImageData, objective-c, oc, swift
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---


# iImageData

Stores the image data.  

```objc
@interface iImageData : NSObject 
```

## Attributes

| Attribute | Type | Description |
|---------- | ---- | ----------- |
| [`bytes`](#bytes) | *NSData\** | The array of bytes that stores the pixel buffer of the image. |
| [`width`](#width) | *NSInteger* | The width of the image in pixels. |
| [`height`](#height) | *NSInteger* | The height of the image in pixels. |
| [`stride`](#stride) | *NSInteger* | The stride is measured by the byte length of each line in the pixel buffer. |
| [`format`](#format) | *NSInteger* | The image pixel format used in the image byte array. View [`EnumImagePixelFormat`]({{ site.enumerations }}image-pixel-format.html?src=ios) for all supported image pixel formats. |

&nbsp;

### bytes

The image data content in a byte array.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
NSData* bytes
```
2. 
```swift
var bytes: Data? { get set }
```

&nbsp;

### width

The width of the image in pixels.  

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
NSInteger width
```
2. 
```swift
var width: Int { get set }
```

&nbsp;

### height

The height of the image in pixels.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
NSInteger height
```
2. 
```swift
var height: Int { get set }
```

&nbsp;

### stride

The stride (or scan width) of the image.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
NSInteger stride
```
2. 
```swift
var stride: Int { get set }
```

&nbsp;

### format

The image pixel format used in the image byte array.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
EnumImagePixelFormat format
```
2. 
```swift
var format: EnumImagePixelFormat { get set }
```

## Methods

| Method | Description |
| ------ | ----------- |
| `toUIImage` | Convert the `ImageData` object to a `UIImage` object. |

### toUIImage

Convert the `ImageData` object to a `UIImage` object.

```objc
- (UIImage * _Nullable)toUIImage:(NSError *_Nullable *_Nullable)error;
```

**Return Value**

A `UIImage` object.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
NSError* error;
[imageData toUIImage:error];
```
2. 
```swift
do{
   try imageData.toUIImage()
}catch{
   //
}
```
