---
layout: default-layout
title: Android DCEImageEditorView Class - Dynamsoft Document Normalizer Documents
description: Documentation page of Android DCEImageEditorView Class of Dynamsoft Document Normalizer.
keywords:  Camera Enhancer, Android, DCEImageEditorView
needAutoGenerateSidebar: true
noTitleIndex: true
needGenerateH3Content: true
breadcrumbText: Android DCEImageEditorView Class
---

# DCEImageEditorView

`DCEImageEditorView` is the class that enable users to add UI configurations on a static image.

```java
class com.dynamsoft.dce.DCEImageEditorView
```

| Method Name | Description |
| ----------- | ----------- |
| [`setOriginalImage`](#setoriginalimage) | Set the background image of the view with an original image. |
| [`getOriginalImage`](#getoriginalimage) | Get the current backgroud image. |
| [`getDrawingLayer`](#getdrawinglayer) | Get the [`DCEDrawingLayer`](dcedrawinglayer.md) instance with the layer ID. |
| [`createDrawingLayer`](#createdrawinglayer) | Create a user-defined [`DCEDrawingLayer`](dcedrawinglayer.md) instance. |
| [`getSelectedDrawingItem`](#getselecteddrawingitem) | Get the selected drawing item. |

&nbsp;

## setOriginalImage

Set the background image of the view with an original image.

```java
public void setOriginalImage(ImageData imageData);
```

**Parameters**

`imageData`: The `imageData` of the image.

**Code Snippet**

```java
mIEV = (DCEImageEditorView) findViewById(R.id.iev);
mImgData = getIntent().getIntExtra("imagedata");
mIEV.setOriginalImage(mImgData);
```

&nbsp;

## getOriginalImage

Get the current backgroud image.

```java
public ImageData getOriginalImage();
```

**Return Value**

The `imageData` of the image.

**Code Snippet**

```java
ImageData image = imageEditorView.getOriginalImage();
```

&nbsp;

## getDrawingLayer

Get the instance of the target `DrawingLayer`. The target `DrawingLayer` will be created if it does not exist.

```java
public DCEDrawingLayer getDrawingLayer(int id);
```

**Parameters**

`id`: The id of the `DrawingLayer`.

**Available ID List**

| Layer | ID |
| ----- | -- |
| DDN_LAYER_ID | 1 |
| DBR_LAYER_ID | 2 |
| DLR_LAYER_ID | 3 |
| USER_DEFINED_LAYER_BASE_ID | 100 |

**Return Value**

An instance of [`DCEDrawingLayer`](dcedrawinglayer.md).

**Code Snippet**

```java
DCEDrawingLayer drawingLayer = dceImageEditorView.getDrawingLayer(DCEDrawingLayer.DDN_LAYER_ID);
```

&nbsp;

## createDrawingLayer

Create a user-defined `DrawingLayer` instance.

```java
public DCEDrawingLayer createDrawingLayer();
```

**Return Value**

An instance of [`DCEDrawingLayer`](dcedrawinglayer.md).

**Code Snippet**

```java
DCEDrawingLayer drawingLayer = dceImageEditorView.createDrawingLayer();
```

&nbsp;

## getSelectedDrawingItem

Get the user selected `DrawingItem`.

```java
public DrawingItem getSelectedDrawingItem();
```

**Return Value**

An instance of `DrawingItem`.

**Code Snippet**

```java
DrawingItem drawingItem = dceImageEditorView.getSelectedDrawingItem();
```

&nbsp;
