---
layout: default-layout
title: Android DrawingStyleManager Class - Dynamsoft Document Normalizer Documents
description: Documentation page of Android DrawingStyleManager Class of Dynamsoft Document Normalizer.
keywords:  Camera Enhancer, Android, DrawingStyleManager
needAutoGenerateSidebar: true
noTitleIndex: true
needGenerateH3Content: true
breadcrumbText: Android DrawingStyleManager Class
---

# DrawingStyleManager

`DrawingStyleManager` is the class for users to create and adjust `DrawingStyles`.

```java
class com.dynamsoft.dce.DrawingStyleManager
```

| Method | Description |
| ------ | ----------- |
| [`getDrawingStyle`](#getdrawingstyle) | Get the `DrawingStyle` instance with the style ID. |
| [`createDrawingStyle`](#createdrawingstyle) | Create a user-defined `DrawingStyle` and get the style ID. |

## getDrawingStyle

Get the `DrawingStyle` instance with the style ID.

```java
public static DrawingStyle getDrawingStyle(int styleId);
```

**Parameters**

`styleId`: The ID of the target `DrawingStyle`.

**Return Value**

An instance of `DrawingStyle`.

**Code Snippet**

```java
DrawingStyle defaultStyle = DrawingStyleManager.getDrawingStyle(DrawingStyleManager.STYLE_ORANGE_STROKE);
```

**Remarks**

There are 8 preset drawing styles.

| ID | Style Name |
| -- | ---------- |
| 1 | `STYLE_BLUE_STROKE` |
| 2 | `STYLE_GREEN_STROKE` |
| 3 | `STYLE_ORANGE_STROKE` |
| 4 | `STYLE_YELLOW_STROKE` |
| 5 | `STYLE_BLUE_STROKE_FILL` |
| 6 | `STYLE_GREEN_STROKE_FILL` |
| 7 | `STYLE_ORANGE_STROKE_FILL` |
| 8 | `STYLE_YELLOW_STROKE_FILL` |

&nbsp;

## createDrawingStyle

Create a user-defined `DrawingStyle` and get the style ID.

```java
public static int createDrawingStyle(int strokeColor, float strokeWidth, int fillColor, int textColor, int fontSize, String fontFamily);
```

**Parameters**

`strokeColor`: The stroke colour.
`strokeWidth`: The width of the stroke (measured by px).
`fillColor`: The fill colour.
`textColor`: The text colour.
`fontSize`: The font size (measured by sp).
`fontFamily`: The font family.

**Code Snippet**

```java
int myStyleId = styleManager.createDrawingStyle(0xff00ff00,2,0xff00ff00,0xff00ff00,12,"sans-serif")
```
