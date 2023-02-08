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
| [`format`](#format) | *NSInteger* | The image pixel format used in the image byte array. View [`EnumImagePixelFormat`]({{ site.enumerations }}image-pixel-format.html?src=android) for all supported image pixel formats. |
| [`orientation`](#orientation) | *NSInteger* | The orientation of the image buffer contained in this frame data. |

## Methods

| Method | Description |
| ------ | ----------- |
| [`toUIImage`](#touiimage) | Convert the `ImageData` object to a `UIImage` object. |

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

### orientation

The orientation of the image buffer contained in this frame data. The value is the angle that the camera image needs to be rotated clockwise so it shows correctly on the display in its natural orientation. It is 0, 90, 180, or 270. A typical value for this is 90 as most camera modules record the frames in landscape right orientation. Rotating a landscape right frame by 90 degrees will show it correctly on the display in portrait orientation (which is the natural device orientation of most phones).

```objc
NSInteger orientation
```

### toUIImage

Convert the `ImageData` object to a `UIImage` object.

```objc
- (UIImage * _Nullable)toUIImage:(NSError *_Nullable *_Nullable)error;
```

**Return Value**

A `UIImage` object.
