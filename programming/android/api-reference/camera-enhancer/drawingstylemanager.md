---
layout: default-layout
title: Dynamsoft Camera Enhancer - Android DrawingStyleManager Class
description: This is the documentation - Android DrawingStyleManager Class page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, Android, DrawingStyleManager
needAutoGenerateSidebar: true
noTitleIndex: true
needGenerateH3Content: true
breadcrumbText: Android DrawingStyleManager Class
---

# DrawingStyleManager

&nbsp;

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
DrawingStyle defaultStyle = DrawingStyleManager.getDrawingStyle(DrawingStyleManager.DEFAULT_STYLE_ID_1);
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
