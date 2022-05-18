---
layout: default-layout
title: Dynamsoft Camera Enhancer - iOS TextDrawingItem Class
description: This is the documentation - iOS TextDrawingItem Class page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, iOS, TextDrawingItem
needAutoGenerateSidebar: true
noTitleIndex: true
needGenerateH3Content: true
breadcrumbText: iOS TextDrawingItem Class
---

# TextDrawingItem

`TextDrawingItem` is a subclass of `DrawingItem`. Dynamsoft Camera Enhancer will draw the `TextDrawingItem` on the UI if it is created and added to the `DCECameraView` or `DCEImageEditorView`.

```objc
@interface TextDrawingItem (DrawingItem)
```

| Method Name | Description |
| ----------- | ----------- |
| [`initWithText`](#initwithtext) | The constructor of `TextDrawingItem`. Initialize the instance of `TextDrawingItem`. |
| [`text`](#text) | The property that indicates the text of the `TextDrawingItem`. |
| [`textRect`](#textrect) | The `CGRect` property that indicates the location of the `TextDrawingItem`. |
| [`drawingStyleId`](#drawingstyle) | Get the drawing style of the current `DrawingItem`. |
| [`state`](#state) | Set the state of the current `DrawingItem`. |
| [`mediaType`](#mediatype) | Get the media type of the current `DrawingItem`. |

&nbsp;

## initWithText

The constructor of `TextDrawingItem`. Initialize the instance of `TextDrawingItem`.

```objc
- (instancetype) initWithText:(NSString*)text textRect(CGRect)textRect;
```

**Parameters**

`text`: The text of the `TextDrawingItem`.
`textRect`: The `CGRect` that indicates the location of the `TextDrawingItem`.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
DrawingItem* drawingItem = [[TextDrawingItem alloc] initWithText:@"" rect:rect];
```
2. 
```swift
let drawingItem = TextDrawingItem.init(text:"Your-Text", rect:rect)
```

&nbsp;

## text

The property that indicates the text of the `TextDrawingItem`.

```objc
@property (assign, nonatomic, readonly) NSString* text;
```

&nbsp;

## textRect

The `CGRect` property that indicates the location of the `TextDrawingItem`.

```objc
@property (assign, nonatomic, readonly) CGRect textRect;
```

{%- include api-reference/drawing-item-ios.md -%}
