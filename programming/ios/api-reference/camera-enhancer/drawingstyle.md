---
layout: default-layout
title: iOS DrawingStyle Class - Dynamsoft Document Normalizer Documents
description: Documentation page of iOS DrawingStyle Class of Dynamsoft Document Normalizer.
keywords:  Camera Enhancer, iOS, DrawingStyle
needAutoGenerateSidebar: true
noTitleIndex: true
needGenerateH3Content: true
breadcrumbText: iOS DrawingStyle Class
---

# DrawingStyle

The class of `DrawingStyle`. It stores the detailed styles of the drawing item.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface DrawingStyle : NSObject
```
2. 
```swift
class DrawingStyle : NSObject
```

| Method | Description |
| ------ | ----------- |
| [`initWithId`](#initwithid) | The constructor of the `initWithId`. |
| [`id`](#id) | The id of the `DrawingStyle`. |
| [`strokeColor`](#strokecolor) | The stroke color of the `DrawingStyle`. |
| [`fillColor`](#fillcolor) | The fill color of the `DrawingStyle`. |
| [`textColor`](#textcolor) | The text color of the `DrawingStyle`. |
| [`strokeWidth`](#strokewidth) | The stroke width of the `DrawingStyle`. |
| [`font`](#font) | The font settings of the `DrawingStyle`. |

&nbsp;

## initWithId

The constructor of the `DrawingStyle`.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (instancetype)initWithId:(NSInteger)id
               strokeColor:(UIColor*)strokeColor
               strokeWidth:(CGFloat)strokeWidth
                 fillColor:(UIColor*)fillColor
                 textColor:(UIColor*)textColor
                      font:(UIFont*) font;
```
2. 
```swift
init(id styleId: Int, stroke strokeColor: UIColor, strokeWidth: CGFloat, fill fillColor: UIColor, textColor: UIColor, font: UIFont)
```

**Remarks**

Please use [`DrawingStyleManager.createDrawingStyle`](drawingstylemanager.md#createdrawingstyle) to create the drawing style.

&nbsp;

## id

The id of the `DrawingStyle`.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (assign, nonatomic, readonly) NSInteger id;
```
2. 
```swift
var styleId: Int { get }
```

&nbsp;

## strokeColor

The stroke color of the `DrawingStyle`.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (assign, nonatomic) UIColor strokeColor;
```
2. 
```swift
var strokeColor: UIColor { get set }
```

&nbsp;

## fillColor

The fill color of the `DrawingStyle`.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (assign, nonatomic) UIColor fillColor;
```
2. 
```swift
var fillColor: UIColor { get set }
```

&nbsp;

## textColor

The text color of the `DrawingStyle`.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (assign, nonatomic) UIColor textColor;
```
2. 
```swift
var textColor: UIColor { get set }
```

&nbsp;

## strokeWidth

The stroke width of the `DrawingStyle`.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (assign, nonatomic) CGFloat strokeWidth;
```
2. 
```swift
var strokeWidth: CGFloat { get set }
```

&nbsp;

## fontSize

The font settings of the `DrawingStyle`.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, copy) UIFont *font;
```
2. 
```swift
var font: UIFont { get set }
```

&nbsp;
