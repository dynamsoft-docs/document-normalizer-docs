---
layout: default-layout
title: Dynamsoft Camera Enhancer - iOS DrawingStyle Class
description: This is the documentation - iOS DrawingStyle Class page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, iOS, DrawingStyle
needAutoGenerateSidebar: true
noTitleIndex: true
needGenerateH3Content: true
breadcrumbText: iOS DrawingStyle Class
---

# DrawingStyle

The class of `DrawingStyle`. It stores the detailed styles of the drawing item.

```objc
@interface DrawingStyle 
```

| Method | Description |
| ------ | ----------- |
| [`initWithId`](#initwithid) | The constructor of the `initWithId`. |
| [`id`](#id) | The id of the `DrawingStyle`. |
| [`strokeColor`](#strokecolor) | The stroke color of the `DrawingStyle`. |
| [`fillColor`](#fillcolor) | The fill color of the `DrawingStyle`. |
| [`textColor`](#textcolor) | The text color of the `DrawingStyle`. |
| [`strokeWidth`](#strokewidth) | The stroke width of the `DrawingStyle`. |
| [`fontSize`](#fontsize) | The font size of the `DrawingStyle`. |
| [`fontFamily`](#fontfamily) | The font-Family of the `DrawingStyle`. |

&nbsp;

## initWithId

The constructor of the `DrawingStyle`.

```objc
- (instancetype)initWithId:(NSInteger)id
               strokeColor:(UIColor*)strokeColor
               strokeWidth:(CGFloat)strokeWidth
                 fillColor:(UIColor*)fillColor
                 textColor:(UIColor*)textColor
                      font:(UIFont*) font;
```

**Remarks**

Please use [`DrawingStyleManager.createDrawingStyle`](drawingstylemanager.md#createdrawingstyle) to create the drawing style.

&nbsp;

## id

The id of the `DrawingStyle`.

```objc
@property (assign, nonatomic, readonly) NSInteger id;
```

&nbsp;

## strokeColor

The stroke color of the `DrawingStyle`.

```objc
@property (assign, nonatomic) UIColor strokeColor;
```

&nbsp;

## fillColor

The fill color of the `DrawingStyle`.

```objc
@property (assign, nonatomic) UIColor fillColor;
```

&nbsp;

## textColor

The text color of the `DrawingStyle`.

```objc
@property (assign, nonatomic) UIColor textColor;
```

&nbsp;

## strokeWidth

The stroke width of the `DrawingStyle`.

```objc
@property (assign, nonatomic) CGFloat strokeWidth;
```

&nbsp;

## fontSize

The font size of the `DrawingStyle`.

```objc
@property (assign, nonatomic) NSInteger fontSize;
```

&nbsp;

## fontFamily

The font-Family of the `DrawingStyle`.

```objc
@property (assign, nonatomic) NSString* fontFamily;
```
