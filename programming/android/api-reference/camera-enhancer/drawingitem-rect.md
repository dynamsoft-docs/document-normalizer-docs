---
layout: default-layout
title: Dynamsoft Camera Enhancer - Android RectDrawingItem Class
description: This is the documentation - Android RectDrawingItem Class page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, Android, RectDrawingItem
needAutoGenerateSidebar: true
noTitleIndex: true
needGenerateH3Content: true
breadcrumbText: Android RectDrawingItem Class
---

# RectDrawingItem

`RectDrawingItem` is a subclass of `DrawingItem`. Dynamsoft Camera Enhancer will draw the `RectDrawingItem` on the UI if it is created and added to the `DCECameraView` or `DCEImageEditorView`.

```java
class RectDrawingItem extends DrawingItem
```

| Method | Descriptions |
| ------ | ------------ |
| [`RectDrawingItem`](#Rectdrawingitem) | The constructor of `RectDrawingItem`. Create an instance of `RectDrawingItem`. |
| [`getMediaType`](#getmediatype) | Get the media type of the `RectDrawingItem`. |
| [`getRect`](#getrect) | Get the `Rect` of the `RectDrawingItem`. |
| [`getDrawingStyleId`](#getdrawingstyleid) | Get the drawing style of the current drawing item. |
| [`setDrawingStyleId`](#setdrawingstyleid) | Set the drawing style of the current drawing item. |
| [`getState`](#getstate) | Get the state of the current drawing item. |
| [`setState`](#setstate) | Set the state of the current drawing item. |

&nbsp;

## RectDrawingItem

The constructor of `RectDrawingItem`. Create an instance of `RectDrawingItem`.

```java
public RectDrawingItem(android.graphics.Rect rect);
```

**Parameters**

`rect`: The `Rect` that indicates the location of the `RectDrawingItem`.

**Code Snippet**

```java
DrawingItem drawingItem = new RectDrawingItem(rect);
```

&nbsp;

## getMediaType

Get the media type of the `RectDrawingItem`.

```java
public EnumDrawingItemMeidaType getMediaType();
```

**Return Value**

The media type of the `RectDrawingItem`.

**Code Snippet**

```java
EnumDrawingItemMediaType mediaType = drawingItem.getMediaType();
```

&nbsp;

## getRect

Get the `Rect` of the `RectDrawingItem`.

```java
public android.graphics.Rect getRect();
```

**Return Value**

The `Rect` that indicates the location of the `RectDrawingItem`.

**Code Snippet**

```java
android.graphics.Rect rect = drawingItem.getRect();
```

{%- include api-reference/drawing-item-android.md -%}
