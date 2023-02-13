---
layout: default-layout
title: iOS DCEFrame Class - Dynamsoft Document Normalizer Documents
description: This is the documentation - iOS DCEFrame Class page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, iOS DCEFrame Class
needAutoGenerateSidebar: true
noTitleIndex: true
needGenerateH3Content: true
breadcrumbText: iOS DCEFrame Class
---

# DCEFrame

The `DCEFrame` is the class that stores pixel data and further information.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface DCEFrame : NSObject
```
2. 
```swift
class DCEFrame : iImageData
```

| Method & Property Name | Type/Return Value | Description |
| ---------------------- | ----------------- | ----------- |
| [`bytes`](#imagedata) | *NSData* * | The property stores the pixel data of the image. |
| [`width`](#width) | *NSInteger* | The property stores the pixel width of the image. |
| [`height`](#height) | *NSInteger* | The property stores the pixel height of the image. |
| [`stride`](#stride) | *NSInteger* | The property stores the stride of the image. |
| [`format`](#pixelformat) | *NSInteger* | The property stores the pixel format of the image. |
| [`frameID`](#frameid) | *NSInteger* | The property stores the `frameID` of the frame. |
| [`quality`](#quality) | [`EnumFrameQuality`](enum-frame-quality.md) | The property stores the quality of the `DCEFrame` image. User have to enable the frame filter feature to get the quality (high/low) of the `DCEFrame`. Otherwise, the frame quality will be unknown. |
| [`isCropped`](#iscropped) | *BOOL* | The property stores a boolean value that recording whether the image is cropped. The frames can be cropped if `fast mode` is enabled. |
| [`cropRegion`](#cropregion) | *CGRect* | The property stores a CGRect value that means the crop region of the image (if the image is cropped). If the image is not cropped, the value will be null. |
| [`orientation`](#orientation) | *NSInteger* | The property stores an int value that means the rotation angle of the image. The value is 0, 90, 180 or 270 with depends on the device orientation. |
| [`toUIImage`](#touiimage) | *UIImage* * | The method converts the image to `UIImage`. |

## imageData

The property stores the pixel data of the image.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
NSData* imageData
```
2. 
```swift
var bytes: Data? { get set }
```

&nbsp;

## width

The property stores the pixel width of the image.

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

## height

The property stores the pixel height of the image.

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

## stride

The property stores the stride of the image.

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

## pixelFormat

The property stores the pixel format of the image. The property value is one of the Enumeration value of `ImagePixelFormat`. Currently, the image output formats of `DCEFrame` are NV21 or ARGB_8888. View more in [`EnumImagePixelFormat`]({{ site.enumerations }}image-pixel-format.html?src=ios)

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
NSInteger pixelFormat
```
2. 
```swift
var pixelFormat: Int { get set }
```

&nbsp;

## frameID

The property stores the `frameID` of the frame.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
NSInteger frameID
```
2. 
```swift
var frameID: Int { get set }
```

&nbsp;

## quality

The property indicates the image quality of the `DCEFrame`. View more in [`EnumFrameQuality`](enum-frame-quality.md). User have to enable the frame filter feature to get the quality (high/low) of the `DCEFrame`. Otherwise, the frame quality will be unknown.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
EnumFrameQuality quality
```
2. 
```swift
var quality: EnumFrameQuality { get set }
```

&nbsp;

## isCropped

The property stores a boolean value that recording whether the image is cropped. The frames can be cropped if `fast mode` is enabled. Property value `true` means the image is cropped and `false` means the image has never been cropped.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
BOOL isCropped
```
2. 
```swift
var isCropped: Bool { get set }
```

&nbsp;

## cropRegion

The property stores a CGRect value that means the crop region of the image (if the image is cropped). If the image is not cropped, the value will be null.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
CGRect cropRegion
```
2. 
```swift
var cropRegion: CGRect { get set }
```

&nbsp;

## orientation

The property stores an int value that means the rotation angle of the image. The value is 0, 90, 180 or 270, which depends on the device orientation.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
NSInteger orientation
```
2. 
```swift
var orientation: Int { get set }
```

<div align="center">
    <p><img src="assets/getOrientation.png" width="70%" alt="getOrientation"></p>
    <p>All examples of the orientation</p>
</div>

&nbsp;

## toUIImage

The method converts the image to `UIImage`.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (UIImage * _Nullable)toUIImage:(NSError *_Nullable *_Nullable)error;
```
2. 
```swift
func toUIImage() throws -> UIImage
```

**Return Value**

The converted image.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, strong) DCEFrame *dceFrame;
/*
  ...
*/
[dceFrame toUIImage];
```
2. 
```swift
var dceFrame:DCEFrame! = nil
/*
  ...
*/
dceFrame.toUIImage()
```
