---
layout: default-layout
title: Dynamsoft Camera Enhancer - Android QuadDrawingItem Class
description: This is the documentation - Android QuadDrawingItem Class page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, Android, QuadDrawingItem
needAutoGenerateSidebar: true
noTitleIndex: true
needGenerateH3Content: true
breadcrumbText: Android QuadDrawingItem Class
---

# QuadDrawingItem

`QuadDrawingItem` is a subclass of `DrawingItem`. Dynamsoft Camera Enhancer will draw the `QuadDrawingItem` on the UI if it is created and added to the `DCECameraView` or `DCEImageEditorView`.

```java
class QuadDrawingItem extends DrawingItem
```

| Method | Descriptions |
| ------ | ------------ |
| [`QuadDrawingItem`](#quaddrawingitem) | The constructor of `QuadDrawingItem`. Create an instance of `QuadDrawingItem`. |
| [`getMediaType`](#getmediatype) | Get the media type of the `QuadDrawingItem`. |
| [`getQuad`](#getquad) | Get the `Quad` of the `QuadDrawingItem`. |
| [`getDrawingStyleId`](#getdrawingstyleid) | Get the drawing style of the current drawing item. |
| [`setDrawingStyleId`](#setdrawingstyleid) | Set the drawing style of the current drawing item. |
| [`getState`](#getstate) | Get the state of the current drawing item. |
| [`setState`](#setstate) | Set the state of the current drawing item. |

## QuadDrawingItem

The constructor of `QuadDrawingItem`. Create an instance of `QuadDrawingItem`.

```java
public QuadDrawingItem(com.dynamsoft.core.Quadrilateral quad;
```

**Parameters**

`quad`: The `Quadrilateral` that indicates the location of the `QuadDrawingItem`.

**Code Snippet**

```java
DrawingItem drawingItem = new QuadDrawingItem(quad);
```

&nbsp;

## getMediaType

Get the media type of the `QuadDrawingItem`.

```java
public EnumDrawingItemMeidaType getMediaType();
```

**Return Value**

The media type of the `QuadDrawingItem`.

**Code Snippet**

```java
EnumDrawingItemMediaType mediaType = drawingItem.getMediaType();
```

&nbsp;

## getQuad

Get the `Quad` of the `QuadDrawingItem`.

```java
public com.dynamsoft.core.Quadrilateral getQuad();
```

**Return Value**

The `Quadrilateral` that indicates the location of the `QuadDrawingItem`.

**Code Snippet**

```java
com.dynamsoft.core.Quadrilateral quad = drawingItem.getRect();
```

{%- include api-reference/drawing-item-android.md -%}
