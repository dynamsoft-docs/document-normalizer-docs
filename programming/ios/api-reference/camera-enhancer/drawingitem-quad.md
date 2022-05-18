---
layout: default-layout
title: Dynamsoft Camera Enhancer - iOS QuadDrawingItem Class
description: This is the documentation - iOS QuadDrawingItem Class page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, iOS, QuadDrawingItem
needAutoGenerateSidebar: true
noTitleIndex: true
needGenerateH3Content: true
breadcrumbText: iOS QuadDrawingItem Class
---

# QuadDrawingItem

`QuadDrawingItem` is a subclass of `DrawingItem`. Dynamsoft Camera Enhancer will draw the `QuadDrawingItem` on the UI if it is created and added to the `DCECameraView` or `DCEImageEditorView`.

```objc
@interface QuadDrawingItem (DrawingItem)
```

| Method Name | Description |
| ----------- | ----------- |
| [`initWithQuad`](#initwithquad) | The constructor of `QuadDrawingItem`. Initialize the instance of `QuadDrawingItem`. |
| [`quad`](#quad) | The `Quadrilateral` property that indicates the position of the `QuadDrawingItem`. |
| [`drawingStyleId`](#drawingstyle) | Get the drawing style of the current `DrawingItem`. |
| [`state`](#state) | Set the state of the current `DrawingItem`. |
| [`mediaType`](#mediatype) | Get the media type of the current `DrawingItem`. |

&nbsp;

## initWithQuad

The constructor of `QuadDrawingItem`. Initialize the instance of `QuadDrawingItem`.

```objc
- (instancetype) initWithQuad:(Quadrilateral*)quad;
```

**Parameters**

`quad`: A `Quadrilateral` that includes the position of the `QuadDrawingItem`.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
DrawingItem* drawingItem = [[QuadDrawingItem alloc] initWithQuad:quad];
```
2. 
```swift
let drawingItem = QuadDrawingItem.init(quad:quad)
```

&nbsp;

## quad

The `Quadrilateral` property that indicates the position of the `QuadDrawingItem`.

```objc
@property (assign, nonatomic, readonly) Quadrilateral* quad; 
```

{%- include api-reference/drawing-item-ios.md -%}
