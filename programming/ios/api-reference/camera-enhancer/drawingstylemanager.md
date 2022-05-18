---
layout: default-layout
title: Dynamsoft Camera Enhancer - iOS DrawingStyleManager Class
description: This is the documentation - iOS DrawingStyleManager Class page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, iOS, DrawingStyleManager
needAutoGenerateSidebar: true
noTitleIndex: true
needGenerateH3Content: true
breadcrumbText: iOS DrawingStyleManager Class
---

# DrawingStyleManager

The class that stores the `DrawingStyles`.

```objc
@interface DrawingStyleManager
```

| Method | Description |
| ------ | ----------- |
| [`getDrawingStyle`](#getdrawingstyle) | Get the `DrawingStyle` instance with the style ID. |
| [`createDrawingStyle`](#createdrawingstyle) | Create a user-defined `DrawingStyle` instance. |

&nbsp;

## getDrawingStyle

Get the `DrawingStyle` instance with the style ID.

```objc
+(DrawingStyle*)getDrawingStyle:(NSInteger)styleId;
```

**Parameters**

`styleId`: The ID of the target `DrawingStyle`.

**Return Value**

An instance of `DrawingStyle`.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
DrawingStyle* style = [DrawingStyleManager getDrawingStyle:DEFAULT_STYLE_ID_1];
```
2. 
```swift
let style = DrawingStyleManager.getDrawingStyle(DEFAULT_STYLE_ID_1)
```

**Remarks**

There are 8 preset drawing styles.

| ID | Style Name |
| -- | ---------- |
| 1 | `DEFAULT_STYLE_ID_1` |
| 2 | `DEFAULT_STYLE_ID_2` |
| 3 | `DEFAULT_STYLE_ID_3` |
| 4 | `DEFAULT_STYLE_ID_4` |
| 5 | `SELECTED_STYLE_ID_1` |
| 6 | `SELECTED_STYLE_ID_2` |
| 7 | `SELECTED_STYLE_ID_3` |
| 8 | `SELECTED_STYLE_ID_4` |

&nbsp;

## createDrawingStyle

Create a user-defined `DrawingStyle` instance.

```objc
+(NSInteger)createDrawingStyle:(UIColor*)strokeColor
                   strokeWidth:(CGFloat)strokeWidth
                     fillColor:(UIColor*) fillColor
                     textColor:(UIColor*) textColor
                          font:(UIFont*) font;

```

**Parameters**

`strokeColor`: The stroke colour.
`strokeWidth`: The width of the stroke.
`fillColor`: The fill colour.
`textColor`: The text colour.
`font`: The font style of the text.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
UIColor *strokeColour = [UIColor colorWithRed:0.2 green:0.3 blue:0.4 alpha:0.5];
UIColor *fillColour = [UIColor colorWithRed:0.2 green:0.3 blue:0.4 alpha:0.5];
UIColor *textColour = [UIColor colorWithRed:0.2 green:0.3 blue:0.4 alpha:0.5];
UIFont *textFont = [UIFont systemFontOfSize:12.0];
NSInteger myStyle = [DrawingStyleManager createDrawingStyle:strokeColour strokeWidth:2.0 fillColor:fillColour textColor:textColour font:textFont];
```
2. 
```swift
let strokeColor = UIColor.init(red: 0.2, green: 0.3, blue: 0.4, alpha: 0.5)
let fillColour = UIColor.init(red: 0.2, green: 0.3, blue: 0.4, alpha: 0.5)
let textColor = UIColor.init(red: 0.2, green: 0.3, blue: 0.4, alpha: 0.5)
let textFont = UIFont.systemFont(ofSize: 12, weight: UIFont.weight.light)
let myStyleID = DrawingStyleManager.createDrawingStyle(strokeColor, strokeWidth:1, fillColor:fillColor, textColor:textColor, font: textFont)
```
