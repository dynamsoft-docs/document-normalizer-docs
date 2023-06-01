---
layout: default-layout
title: Android DrawingItem Class - Dynamsoft Document Normalizer Documents
description: Documentation page of Android DrawingItem Class of Dynamsoft Document Normalizer.
keywords:  Camera Enhancer, Android, DrawingItem
needAutoGenerateSidebar: true
noTitleIndex: true
needGenerateH3Content: true
breadcrumbText: Android DrawingItem Class
---

# DrawingItem

`DrawingItem` is the class for users to draw graphic items on the UI view.

```java
class com.dynamsoft.dce.DrawingItem
```

| Method Name | Description |
| ----------- | ----------- |
| [`getDrawingStyleId`](#getdrawingstyleid) | Get the drawing style of the current drawing item. |
| [`setDrawingStyleId`](#setdrawingstyleid) | Set the drawing style of the current drawing item. |
| [`getState`](#getstate) | Get the state of the current drawing item. |
| [`setState`](#setstate) | Set the state of the current drawing item. |
| [`getMediaType`](#getmediatype) | Get the media type of the current drawing item. |

{%- include api-reference/drawing-item-android.md -%}


## getMediaType

Get the media type of the `DrawingItem`.

```java
public abstract EnumDrawingItemMediaType getMediaType();
```

**Return Value**

One of the `EnumDrawingItemMediaType` that indicates the media type of the `DrawingItem`.

**Code Snippet**

```java
EnumDrawingItemMediaType type = drawingItem.getMediaType();
```
