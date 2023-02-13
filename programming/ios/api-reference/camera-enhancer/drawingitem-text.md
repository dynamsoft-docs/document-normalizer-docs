---
layout: default-layout
title: iOS TextDrawingItem Class - Dynamsoft Document Normalizer Documents
description: This is the documentation - iOS TextDrawingItem Class page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, iOS, TextDrawingItem
needAutoGenerateSidebar: true
noTitleIndex: true
needGenerateH3Content: true
breadcrumbText: iOS TextDrawingItem Class
---

# TextDrawingItem

`TextDrawingItem` is a subclass of `DrawingItem`. Dynamsoft Camera Enhancer will draw the `TextDrawingItem` on the UI if it is created and added to the `DCECameraView` or `DCEImageEditorView`.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface TextDrawingItem (DrawingItem)
```
2. 
```swift
class TextDrawingItem : DrawingItem
```

| Method Name | Description |
| ----------- | ----------- |
| [`initWithText`](#initwithtext) | The constructor of `TextDrawingItem`. Initialize the instance of `TextDrawingItem`. |
| [`text`](#text) | The property that indicates the text of the `TextDrawingItem`. |
| [`textRect`](#textrect) | The `CGRect` property that indicates the location of the `TextDrawingItem`. |
| [`drawingStyleId`](#drawingstyleid) | Get the drawing style of the current `DrawingItem`. |
| [`state`](#state) | Set the state of the current `DrawingItem`. |
| [`getMediaType`](#getmediatype) | Get the media type of the current `DrawingItem`. |

&nbsp;

## initWithText

The constructor of `TextDrawingItem`. Initialize the instance of `TextDrawingItem`.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (instancetype) initWithText:(NSString*)text textRect(CGRect)textRect;
```
2. 
```swift
init(text: String, rect: CGRect)
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

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (assign, nonatomic, readonly) NSString* text;
```
2. 
```swift
var text: String { get }
```

&nbsp;

## rect

The `CGRect` property that indicates the location of the `TextDrawingItem`.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, readonly) CGRect rect;
```
2. 
```swift
var rect: CGRect { get }
```

{%- include api-reference/drawing-item-ios.md -%}
