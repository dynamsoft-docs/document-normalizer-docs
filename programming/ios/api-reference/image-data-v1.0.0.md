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

| Attribute | Type |
|---------- | ---- |
| [`bytes`](#bytes) | *NSData\** |
| [`width`](#width) | *NSInteger* |
| [`height`](#height) | *NSInteger* |
| [`stride`](#stride) | *NSInteger* |
| [`format`](#format) | [`EnumImagePixelFormat`]({{ site.enumerations }}image-pixel-format.html?src=ios) |
| [`orientation`](#orientation) | *NSInteger* |

&nbsp;

### bytes

The image data content in a byte array.

```objc
NSData* bytes
```

&nbsp;

### width

The width of the image in pixels.  

```objc
NSInteger width
```

&nbsp;

### height

The height of the image in pixels.

```objc
NSInteger height
```

&nbsp;

### stride

The stride (or scan width) of the image.

```objc
NSInteger stride
```

&nbsp;

### format

The image pixel format used in the image byte array.

```objc
EnumImagePixelFormat format
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
