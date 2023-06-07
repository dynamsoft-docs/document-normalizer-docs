---
layout: default-layout
title: Android TextDrawingItem Class - Dynamsoft Document Normalizer Documents
description: Documentation page of Android TextDrawingItem Class of Dynamsoft Document Normalizer.
keywords:  Camera Enhancer, Android, TextDrawingItem
needAutoGenerateSidebar: true
noTitleIndex: true
needGenerateH3Content: true
breadcrumbText: Android TextDrawingItem Class
---

# TextDrawingItem Class

`TextDrawingItem` is a subclass of `DrawingItem`. Dynamsoft Camera Enhancer will draw the `TextDrawingItem` on the UI if it is created and added to the `DCECameraView` or `DCEImageEditorView`.

```java
class com.dynamsoft.dce.TextDrawingItem extends DrawingItem
```

| Method | Descriptions |
| ------ | ------------ |
| [`TextDrawingItem`](#textdrawingitem) | The constructor of `TextDrawingItem`. Create an instance of `TextDrawingItem`. |
| [`getMediaType`](#getmediatype) | Get the media type of the `TextDrawingItem`. |
| [`getText`](#gettext) | Get the `Text` of the `TextDrawingItem`. |
| [`getDrawingStyleId`](#getdrawingstyleid) | Get the drawing style of the current drawing item. |
| [`setDrawingStyleId`](#setdrawingstyleid) | Set the drawing style of the current drawing item. |
| [`getState`](#getstate) | Get the state of the current drawing item. |
| [`setState`](#setstate) | Set the state of the current drawing item. |

&nbsp;

## TextDrawingItem

The constructor of `TextDrawingItem`. Create an instance of `TextDrawingItem`.

```java
public TextDrawingItem(String text, android.graphics.Rect textRect);
```

**Parameters**

`text`: The text of the `TextDrawingItem`.
`textRect`: The `Rect` that indicates the location of the `TextDrawingItem`.

**Code Snippet**

```java
DrawingItem drawingItem = new TextDrawingItem(Text);
```

&nbsp;

## getMediaType

Get the media type of the `TextDrawingItem`.

```java
public EnumDrawingItemMeidaType getMediaType();
```

**Return Value**

The media type of the `TextDrawingItem`.

**Code Snippet**

```java
EnumDrawingItemMediaType mediaType = drawingItem.getMediaType();
```

&nbsp;

## getText

Get the `Text` of the `TextDrawingItem`.

```java
public String getText();
```

**Return Value**

The text content of the `TextDrawingItem`.

**Code Snippet**

```java
String text = drawingItem.getText();
```

&nbsp;

## getTextRect

Get the `Rect` of the `TextDrawingItem`. It indicates the location of the `TextDrawingItem`.

```java
public android.graphics.Rect getTextRect();
```

**Return Value**

The Rect of the `TextDrawingItem`.

**Code Snippet**

```java
android.graphics.Rect rect = drawingItem.getTextRect();
```

{%- include api-reference/drawing-item-android.md -%}
