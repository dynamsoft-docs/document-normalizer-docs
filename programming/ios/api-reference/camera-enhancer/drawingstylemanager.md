---
layout: default-layout
title: iOS DrawingStyleManager Class - Dynamsoft Document Normalizer Documents
description: Documentation page of iOS DrawingStyleManager Class of Dynamsoft Document Normalizer.
keywords:  Camera Enhancer, iOS, DrawingStyleManager
needAutoGenerateSidebar: true
noTitleIndex: true
needGenerateH3Content: true
breadcrumbText: iOS DrawingStyleManager Class
---

# DrawingStyleManager

`DrawingStyleManager` is the class for users to create and adjust `DrawingStyles`.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface DrawingStyleManager
```
2. 
```swift
class DrawingStyleManager : NSObject
```

| Method | Description |
| ------ | ----------- |
| [`getDrawingStyle`](#getdrawingstyle) | Get the `DrawingStyle` instance with the style ID. |
| [`createDrawingStyle`](#createdrawingstyle) | Create a user-defined `DrawingStyle` instance. |

&nbsp;

## getDrawingStyle

Get the `DrawingStyle` instance with the style ID.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
+(DrawingStyle*)getDrawingStyle:(NSInteger)styleId;
```
2. 
```swift
class func getDrawingStyle(_ styleId: Int) -> DrawingStyle
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
DrawingStyle* style = [DrawingStyleManager getDrawingStyle:STYLE_BLUE_STROKE_FILL];
```
2. 
```swift
let style = DrawingStyleManager.getDrawingStyle(STYLE_BLUE_STROKE_FILL)
```

**Remarks**

There are 8 preset drawing styles.

| ID | Style Name |
| -- | ---------- |
| 1 | `STYLE_BLUE_STROKE_FILL` |
| 2 | `STYLE_GREEN_STROKE_FILL` |
| 3 | `STYLE_ORANGE_STROKE_FILL` |
| 4 | `STYLE_YELLOW_STROKE_FILL` |
| 5 | `STYLE_BLUE_STROKE_FILL` |
| 6 | `STYLE_GREEN_STROKE_FILL` |
| 7 | `STYLE_ORANGE_STROKE_FILL` |
| 8 | `STYLE_YELLOW_STROKE_FILL` |

&nbsp;

## createDrawingStyle

Create a user-defined `DrawingStyle` instance.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
+(NSInteger)createDrawingStyle:(UIColor*)strokeColor
                   strokeWidth:(CGFloat)strokeWidth
                     fillColor:(UIColor*) fillColor
                     textColor:(UIColor*) textColor
                          font:(UIFont*) font;

```
2. 
```swift
class func createDrawingStyle(_ strokeColor: UIColor, strokeWidth: CGFloat, fill fillColor: UIColor, textColor: UIColor, font: UIFont) -> Int
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
