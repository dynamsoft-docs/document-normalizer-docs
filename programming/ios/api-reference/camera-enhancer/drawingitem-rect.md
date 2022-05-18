---
layout: default-layout
title: Dynamsoft Camera Enhancer - iOS RectDrawingItem Class
description: This is the documentation - iOS RectDrawingItem Class page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, iOS, RectDrawingItem
needAutoGenerateSidebar: true
noTitleIndex: true
needGenerateH3Content: true
breadcrumbText: iOS RectDrawingItem Class
---

# RectDrawingItem

`RectDrawingItem` is a subclass of `DrawingItem`. Dynamsoft Camera Enhancer will draw the `RectDrawingItem` on the UI if it is created and added to the `DCECameraView` or `DCEImageEditorView`.

```objc
@interface RectDrawingItem (DrawingItem)
```

| Method Name | Description |
| ----------- | ----------- |
| [`initWithRect`](#initwithrect) | The constructor of `RectDrawingItem`. Initialize the instance of `RectDrawingItem`. |
| [`rect`](#rect) | The property that indicates the `Rect` of the `RectDrawingItem`. |
| [`drawingStyleId`](#drawingstyle) | Get the drawing style of the current `DrawingItem`. |
| [`state`](#state) | Set the state of the current `DrawingItem`. |
| [`mediaType`](#mediatype) | Get the media type of the current `DrawingItem`. |

&nbsp;

## initWithRect

The constructor of `RectDrawingItem`. Initialize the instance of `RectDrawingItem`.

```objc
- (instancetype) initWithRect:(CGRect)rect;
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

```objc
@property (assign, nonatomic, readonly) CGRect rect;
```

{%- include api-reference/drawing-item-ios.md -%}
