---
layout: default-layout
title: Dynamsoft Camera Enhancer - Android DrawingStyle Class
description: This is the documentation - Android DrawingStyle Class page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, Android, DrawingStyle
needAutoGenerateSidebar: true
noTitleIndex: true
needGenerateH3Content: true
breadcrumbText: Android DrawingStyle Class
---

# DrawingStyle

The class of DrawingStyle. It stores the detailed styles of the drawing item.

```java
class DrawingStyle 
```

| Method | Description |
| ------ | ----------- |
| [`DrawingStyle`](#drawingstyle) | The constructor of the `DrawingStyle`. |
| [`getId`](#getid) | Get the id of the drawing style. |
| [`getStrokeColor`](#getstrokecolor) | Get the stroke color of the drawing style. |
| [`setStrokeColor`](#setstrokecolor) | Set the stroke color of the drawing style. |
| [`getFillColor`](#getfillcolor) | Get the fill color of the drawing style. |
| [`setFillColor`](#setfillcolor) | Set the fill color of the drawing style. |
| [`getTextColor`](#gettextcolor) | Get the text color of the drawing style. |
| [`setTextColor`](#settextcolor) | Set the text color of the drawing style. |
| [`getStrokeWidth`](#getstrokewidth) | Get the stroke width of the drawing style. |
| [`setStrokeWidth`](#setstrokewidth) | Set the stroke width of the drawing style. |
| [`getFontSize`](#getfontsize) | Get the font size of the drawing style. |
| [`setFontSize`](#setfontsize) | Set the font size of the drawing style. |
| [`getFontFamily`](#getfontfamily) | Get the font-Family of the drawing style. |
| [`setFontFamily`](#setfontfamily) | Set the font-Family of the drawing style. |

&nbsp;

## DrawingStyle

The constructor of the `DrawingStyle`.

```java
public DrawingStyle(int id, int strokeColor, float strokeWidth, int fillColor, int textColor, int fontSize, String fontFamily);
```

**Remarks**

Please use [`DrawingStyleManager.createDrawingStyle`](drawingstylemanager.md#createdrawingstyle) to create the drawing style.

&nbsp;

## getId

Get the id of the drawing style.

```java
public int getId();
```

&nbsp;

## getStrokeColor

Get the stroke color of the drawing style.

```java
public int getStrokeColor();
```

&nbsp;

## setStrokeColor

Set the stroke color of the drawing style.

```java
public void setStrokeColor(int color);
```

&nbsp;

## getFillColor

Get the fill color of the drawing style.

```java
public int getFillColor();
```

&nbsp;

## setFillColor

Set the fill color of the drawing style.

```java
public void setFillColor(int color);
```

&nbsp;

## getTextColor

Get the text color of the drawing style.

```java
public int getTextColor();
```

&nbsp;

## setTextColor

Set the text color of the drawing style.

```java
public void setTextColor(int color);
```

&nbsp;

## getStrokeWidth

Get the stroke width of the drawing style.

```java
public float getStrokeWidth();
```

&nbsp;

## setStrokeWidth

Set the stroke width of the drawing style.

```java
public void setStrokeWidth(float width);
```

&nbsp;

## getFontSize

Get the font size of the drawing style.

```java
public int getFontSize();
```

&nbsp;

## setFontSize

Set the font size of the drawing style.

```java
public void setFontSize(int size);
```

&nbsp;

## getFontFamily

Get the font-Family of the drawing style.

```java
public String getFontFamily();
```

&nbsp;

## setFontFamily

Set the font-Family of the drawing style.

```java
public void setFontFamily(String font);
```
