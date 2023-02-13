---
layout: default-layout
title: iOS DCECameraView Class - Dynamsoft Document Normalizer Documents
description: This is the documentation - iOS DCECameraView Class page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, iOS DCECameraView Class
needAutoGenerateSidebar: true
noTitleIndex: true
needGenerateH3Content: true
breadcrumbText: iOS DCECameraView Class
---

# DCECameraView

`DCECameraView` is the class that enables users to add elements on camera view conveniently.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface DCECameraView: UIView<CALayerDelegate>
```
2. 
```swift
class DCECameraView : UIView, CALayerDelegate
```

| Method/Property Name | Description |
| ----------- | ----------- |
| [`initWithFrame`](#initwithframe) | Init the `DCECameraView`. |
| [`cameraWithFrame`](#camerawithframe) | Init the `DCECameraView` with a static method. |
| [`setTorchButton`](#settorchbutton) | Set the position, size and image of the torch button. |
| [`torchButtonVisible`](#torchbuttonvisible) | The property controls the visibility of the torch Button. |
| [`getDrawingLayer`](#getdrawinglayer) | Get the [`DCEDrawingLayer`](dcedrawinglayer.md) instance with the layer ID. |
| [`createDrawingLayer`](#createdrawinglayer) | Create a user-defined [`DCEDrawingLayer`](dcedrawinglayer.md) instance. |
| [`getVisibleRegionOfVideo`](#getvisibleregionofvideo) | Get the region of video that is visible on the camera. It help you to set the scan region when the shape of `DCECameraView` is quite different from the video streaming. |
| [`overlayVisible`](#overlayvisible) | **Deprecated**. The property stores the BOOL value that controls the visibility of the overlays. |
| [`setOverlayColour`](#setoverlaycolour) | **Deprecated**. Set the stroke and fill in colour of the overlay(s). |
| [`viewfinderVisible`](#viewfindervisible) | **Deprecated**. The property stores the BOOL value that controls the visibility of the viewfinder. |
| [`setViewfinder`](#setviewfinder) | **Deprecated**. Set the attribute of the viewfinder. Currently only available for position and size setting. |

&nbsp;

## initWithFrame

Init the DCECameraView.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (instancetype)initWithFrame:(CGRect)frame;
```
2. 
```swift
init(frame: CGRect)
```

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
_dceView = [[DCECameraView alloc] initWithFrame:self.view.bounds]
```
2. 
```swift
let dceView = DCECameraView.init(frame self.view.bounds)
```

&nbsp;

## cameraWithFrame

Statically init the DCECameraView.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
+ (instancetype)cameraWithFrame:(CGRect)frame NS_SWIFT_NAME(init(frame:));
```
2. 
```swift
init(frame: CGRect)
```

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
_dceView = [DCECameraView cameraWithFrame:self.view.bounds];
```
2. 
```swift
let dceView = DCECameraView.init(frame self.view.bounds)
```

&nbsp;

## setTorchButton

Set the position, size and image for the torch button.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (void)setTorchButton:(CGRect)torchButton torchOnImage:(UIImage*)torchOnImage torchOffImage:(UIImage*)torchOffImage;
```
2. 
```swift
func setTorchButton(frame: CGRect, torchOnImage: UIImage?, torchOffImage: UIImage?)
```

**Parameters**

`frame`: The frame of torch button. It includes the width, height and top-left corner coordinate of the torch button. You can input a nil value to apply no changes on the frame of button.  
`torchOnImage`: Display this image when the torch is on. You can input a null value to apply no changes to the image of the torch button when the torch is on.  
`torchOffImage`: Display this image when the torch is off. You can input a null value to apply no changes to the image of the torch button when the torch is off.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
CGRect rect = {0, 0, 30, 30};
[_dceView setTorchButton:(rect) torchOnImage: image torchOffImage: image];
```
2. 
```swift
_dceView.setTorchButton(CGRect.init(x: 0, y: 0, width: 500, height: 500), torchOnImage: image, torchOffImage:image)
```

**Remarks**

Method `- (void)setTorchButton:(CGPoint)torchButtonPosition` is deprecated. Please use the new `setTorchButton` method.

&nbsp;

## torchButtonVisible

`torchButtonVisible` is a property that controls the visibility of the `torchButton`. The torch button icon is preset in the SDK. If the `torchButtonPosition` has never been configured, the `torchButton` will be displayed on the default position. Currently, the icon and the size of the button are not available for setting.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (assign, nonatomic) BOOL torchVisible;
```
2. 
```swift
var torchButtonVisible: Bool { get set }
```

**Parameters**

When the property value is true, the torch button should be displayed. Otherwise, the torch button should be hidden.

&nbsp;

## getDrawingLayer

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (DCEDrawingLayer*) getDrawingLayer:(NSInteger)id;
```
2. 
```swift
func getDrawingLayer(_ layerId: Int) -> DCEDrawingLayer
```

**Parameters**

`id`: The id of the drawing layer.

**Available ID List**

| Layer | ID |
| ----- | -- |
| DDN_LAYER_ID | 1 |
| DBR_LAYER_ID | 2 |
| DLR_LAYER_ID | 3 |
| USER_DEFINED_LAYER_BASE_ID | 100 |

**Return Value**

The targeting instance of [`DCEDrawingLayer`](dcedrawinglayer.md).

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
DCEDrawingLayer *drawingLayer = [_dceView getDrawingLayer:DBR_LAYER_ID];
```
2. 
```swift
let drawingLayer = try? dceView.getDrawingLayer(DBR_LAYER_ID)
```

&nbsp;

## createDrawingLayer

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (DCEDrawingLayer*) createDrawingLayer;
```
2. 
```swift
func createDrawingLayer() -> DCEDrawingLayer
```

**Return Value**

A user-defined drawing layer.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
DCEDrawingLayer *drawingLayer = [_dceView createDrawingLayer:1];
```
2. 
```swift
let drawingLayer = try? dceView.createDrawingLayer(1)
```

&nbsp;

## getVisibleRegionOfVideo

Get the visible region of the video streaming.

When the shape of your camera view is quite different from the shape of the video streaming, there might exist a large area that is invisible. You can use this method to get the region of this invisible area.

<div align="center">
    <p><img src="../../assets/visible-region.png" width="30%" alt="visible-region"></p>
    <p>What's Visible Region</p>
</div>

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (iRegionDefinition*) getVisibleRegionOfVideo;
```
2. 
```swift
func getVisbleRegionOfVideo() -> iRegionDefinition
```

**Return Value**

An object of `iRegionDefinition`. You can use this `iRegionDefinition` object to set the scan region.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
iRegionDefinition *region = [_dceView getVisibleRegionOfVideo];
[_dce setScanRegion:region error:nil];
```
2. 
```swift
let region = dceView.getVisibleRegionOfVideo()
dce.setScanRegion(region, error: &error)
```

&nbsp;

## overlayVisible

> The method is deprecated

The property stores the BOOL value that controls the visibility of the overlays.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (assign, nonatomic) BOOL overlayVisible;
```
2. 
```swift
var overlayVisible: Bool { get set }
```

**Remarks**

If the property value is `true`, the `cameraView` will try to draw and display overlays on the interest areas. Otherwise, the `cameraView` will not draw overlays.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
[_dceView setOverlayVisible:true];
```
2. 
```swift
dceView.overlayVisible = true
```

&nbsp;

## setOverlayColour

> The method is deprecated

Set the stroke and fill in colour of the overlay(s).

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (void)setOverlayColour:(UIColor*)stroke fill:(UIColor*)fill;
```
2. 
```swift
func setOverlayColour(_ stroke: UIColor, fill: UIColor)
```

**Parameters**

`stroke`: The stroke colour of the overlay.  
`fill`: The fill in colour of the overlay.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
// RGB 0 ~ 255, alpha 0 ~ 1
UIColor* strokeColor = [UIColor colorWithRed:0 green:245 blue:255 alpha:0.5];
UIColor* fillColor = [UIColor colorWithRed:0 green:245 blue:255 alpha:0.5];
[_dceView setOverlayColour:strokeColor fill:fillColor];
```
2. 
```swift
// RGB 0 ~ 255, alpha 0 ~ 1
let strokeColour = UIColor(red: 0, green: 245, blue: 255, alpha: 0.5)
let fillColour = UIColor(red: 0, green: 245, blue: 255, alpha: 0.5)
_dceView.setOverlayColour(strokeColour, fill: fillcolour)
```

&nbsp;

## viewfinderVisible

> The method is deprecated

The property stores the BOOL value that controls the visibility of the viewfinder.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (assign, nonatomic) BOOL viewfinderVisible;
```
2. 
```swift
var viewfinderVisible: Bool { get set }
```

**Remarks**

If the property value is `true`, the `cameraView` will try to create and display a viewfinder. Otherwise, the `cameraView` will not create the viewfinder.

&nbsp;

## setViewfinder

> The method is deprecated

Set the attribute of the viewfinder. Currently only available for position and size setting.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (void)setViewfinder:(CGFloat)left top:(CGFloat)top right:(CGFloat)right bottom:(CGFloat)bottom error:(NSError * _Nullable * _Nullable)error;
```
2. 
```swift
func setViewFinder(_ left: CGFloat, top: CGFloat, right: CGFloat, bottom: CGFloat, error: NSErrorPointer)
```

**Parameters**

`left`: The distance (by percentage) between the left border of the viewfinder and the left side of the screen. The default value is 0.15.  
`top`: The distance (by percentage) between the top border of the viewfinder and the top side of the screen. The default value is 0.3.  
`right`: The distance (by percentage) between the right border of the viewfinder and the left side of the screen. The default value is 0.85.  
`bottom`: The distance (by percentage) between the bottom border of the viewfinder and the top side of the screen. The default value is 0.7.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
[_dceView setViewfinder:0.1 top: 0.3 right: 0.9 bottom: 0.7];
```
2. 
```swift
_dceView.setViewfinder(0.1, top: 0.3, right: 0.9, bottom: 0.7)
```

**Remarks**

The viewfinder is built based on the screen coordinate system. The origin of the coordinate is the left-top point of the mobile device. The `left border` of the viewfinder always means the closest border that parallels to the left side of the mobile device no matter how the mobile device is rotated.

&nbsp;
