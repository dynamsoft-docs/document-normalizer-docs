---
layout: default-layout
title: iOS RectDrawingItem Class - Dynamsoft Document Normalizer Documents
description: Documentation page of iOS RectDrawingItem Class of Dynamsoft Document Normalizer.
keywords:  Camera Enhancer, iOS, RectDrawingItem
needAutoGenerateSidebar: true
noTitleIndex: true
needGenerateH3Content: true
breadcrumbText: iOS RectDrawingItem Class
---

# RectDrawingItem

`RectDrawingItem` is a subclass of `DrawingItem`. Dynamsoft Camera Enhancer will draw the `RectDrawingItem` on the UI if it is created and added to the `DCECameraView` or `DCEImageEditorView`.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface RectDrawingItem (DrawingItem)
```
2. 
```swift
class RectDrawingItem : DrawingItem
```

| Method Name | Description |
| ----------- | ----------- |
| [`initWithRect`](#initwithrect) | The constructor of `RectDrawingItem`. Initialize the instance of `RectDrawingItem`. |
| [`rect`](#rect) | The property that indicates the `Rect` of the `RectDrawingItem`. |
| [`drawingStyleId`](#drawingstyle) | Get the drawing style of the current `DrawingItem`. |
| [`state`](#state) | Set the state of the current `DrawingItem`. |
| [`getMediaType`](#getmediatype) | Get the media type of the current `DrawingItem`. |

&nbsp;

## initWithRect

The constructor of `RectDrawingItem`. Initialize the instance of `RectDrawingItem`.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (instancetype) initWithRect:(CGRect)rect;
```
2. 
```swift
init(rect: CGRect)
```

**Parameters**

`rect`: A `Rect` that indicates the location of the `RectDrawingItem`.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
DrawingItem* drawingItem = [[RectDrawingItem alloc] initWithRect:rect];
```
2. 
```swift
let drawingItem = RectDrawingItem.init(rect:rect)
```

&nbsp;

## rect

The property that indicates the `Rect` of the `RectDrawingItem`.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (assign, nonatomic, readonly) CGRect rect;
```
2. 
```swift
var rect: CGRect { get }
```

{%- include api-reference/drawing-item-ios.md -%}
