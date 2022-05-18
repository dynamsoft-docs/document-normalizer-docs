---
layout: default-layout
title: Dynamsoft Camera Enhancer - iOS DCEFrame Class
description: This is the documentation - iOS DCEFrame Class page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, iOS DCEFrame Class
needAutoGenerateSidebar: true
noTitleIndex: true
needGenerateH3Content: true
breadcrumbText: iOS DCEFrame Class
---

# DCEFrame

The `DCEFrame` is the class that stores pixel data and further information.

```objc
@interface DCEFrame : NSObject
```

| Method & Property Name | Type/Return Value | Description |
| ---------------------- | ----------------- | ----------- |
| [`imageData`](#imagedata) | *NSData* * | The property stores the pixel data of the image. |
| [`width`](#width) | *NSInteger* | The property stores the pixel width of the image. |
| [`height`](#height) | *NSInteger* | The property stores the pixel height of the image. |
| [`stride`](#stride) | *NSInteger* | The property stores the stride of the image. |
| [`pixelFormat`](#pixelformat) | *NSInteger* | The property stores the pixel format of the image. |
| [`frameID`](#frameid) | *NSInteger* | The property stores the `frameID` of the frame. |
| [`quality`](#quality) | [`EnumFrameQuality`]({{site.enumerations}}enum-frame-quality.html) | The property stores the quality of the `DCEFrame` image. User have to enable the frame filter feature to get the quality (high/low) of the `DCEFrame`. Otherwise, the frame quality will be unknown. |
| [`isCropped`](#iscropped) | *BOOL* | The property stores a boolean value that recording whether the image is cropped. The frames can be cropped if `fast mode` is enabled. |
| [`cropRegion`](#cropregion) | *CGRect* | The property stores a CGRect value that means the crop region of the image (if the image is cropped). If the image is not cropped, the value will be null. |
| [`orientation`](#orientation) | *NSInteger* | The property stores an int value that means the rotation angle of the image. The value is 0, 90, 180 or 270 with depends on the device orientation. |
| [`toUIImage`](#touiimage) | *UIImage* * | The method converts the image to `UIImage` to make it visible on the UI. |

## imageData

The property stores the pixel data of the image.

```objectivec
NSData* imageData
```

&nbsp;

## width

The property stores the pixel width of the image.

```objectivec
NSInteger width
```

&nbsp;

## height

The property stores the pixel height of the image.

```objectivec
NSInteger height
```

&nbsp;

## stride

The property stores the stride of the image.

```objectivec
NSInteger stride
```

&nbsp;

## pixelFormat

The property stores the pixel format of the image. The property value is one of the Enumeration value of `ImagePixelFormat`. Currently, the image output formats of `DCEFrame` are NV21 or ARGB_8888. View more in Dynamsoft Barcode Reader Enumeration [`ImagePixelFormat`]({{site.barcode-enum}}other-enums.html#imagepixelformat)

```objectivec
NSInteger pixelFormat
```

&nbsp;

## frameID

The property stores the `frameID` of the frame.

```objectivec
NSInteger frameID
```

&nbsp;

## quality

The property stores the quality of the `DCEFrame` image. User have to enable the frame filter feature to get the quality (high/low) of the `DCEFrame`. Otherwise, the frame quality will be unknown. View more about the frame quality in enumeration [`EnumFrameQuality`]({{site.enumerations}}enum-frame-quality.html).

```objectivec
EnumFrameQuality quality
```

&nbsp;

## isCropped

The property stores a boolean value that recording whether the image is cropped. The frames can be cropped if `fast mode` is enabled. Property value `true` means the image is cropped and `false` means the image has never been cropped.

```objectivec
BOOL isCropped
```

&nbsp;

## cropRegion

The property stores a CGRect value that means the crop region of the image (if the image is cropped). If the image is not cropped, the value will be null.

```objectivec
CGRect cropRegion
```

&nbsp;

## orientation

The property stores an int value that means the rotation angle of the image. The value is 0, 90, 180 or 270, which depends on the device orientation.

```objectivec
NSInteger orientation
```

<div align="center">
    <p><img src="assets/getOrientation.png" width="70%" alt="getOrientation"></p>
    <p>All examples of the orientation</p>
</div>

&nbsp;

## toUIImage

The method converts the image to `UIImage` to make it visible on the UI.

```objc
- (UIImage*)toUIImage;
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
