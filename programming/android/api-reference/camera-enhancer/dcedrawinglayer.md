---
layout: default-layout
title: Dynamsoft Camera Enhancer - Android DCEDrawingLayer Class
description: This is the documentation - Android DCEDrawingLayer Class page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, Android, DCEDrawingLayer
needAutoGenerateSidebar: true
noTitleIndex: true
needGenerateH3Content: true
breadcrumbText: Android DCEDrawingLayer Class
---

# DCEDrawingLayer

The layers that contains `DrawingItems`. Users can add configurations for the `DrawingItems` via `DCEDrawingLayer`

```java
class com.dynamsoft.dce.DCEDrawingLayer
```

| Method Name | Description |
| ----------- | ----------- |
| [`DCEDrawingLayer`](#dcedrawinglayer) | The constructor of the `DCEDrawingLayer` class. |
| [`getId`](#getid) | Get the `DrawingLayer` ID of the `DrawingLayer`. |
| [`addDrawingItems`](#adddrawingitems) | Add a list of [`DrawingItems`](drawingitem.md) to the `DrawingLayer`. These [`DrawingItems`](drawingitem.md) will be appended to the drawing item list of the current `DrawingLayer`. |
| [`setDrawingItems`](#setdrawingitems) | Set a list of [`DrawingItems`](drawingitem.md) to the `DrawingLayer`. These [`DrawingItems`](drawingitem.md) will replace the previous [`DrawingItems`](drawingitem.md) of the current `DrawingLayer`. |
| [`getDrawingItems`](#getdrawingitems) | Get all available [`DrawingItems`](drawingitem.md) in the `DrawingLayer`. |
| [`clearDrawingItems`](#cleardrawingitems) | Clear all available [`DrawingItems`](drawingitem.md) in the `DrawingLayer`. |
| [`setDrawingStyleId(styleId)`](#setdrawingstyleidstyleid) | Specify a style ID for all available [`DrawingItems`](drawingitem.md). |
| [`setDrawingStyleId(styleId,state)`](#setdrawingstyleidstate) | Specify a style ID for the targeting [`DrawingItems`](drawingitem.md). |
| [`setDrawingStyleId(styleId,state,mediaType)`](#setdrawingstyleidstatemediatype) | Specify a style ID for the targeting [`DrawingItems`](drawingitem.md). |
| [`setVisible`](#setvisible) | Set the visibility of the `DrawingLayer`. |
| [`isVisible`](#isvisible) | Get the visibility of the `DrawingLayer`. |

&nbsp;

## DCEDrawingLayer

The constructor of the `DCEDrawingLayer` class.

```java
public DCEDrawingLayer(int id);
```

**Parameters**

`id`: Indicate the ID of the `DrawingLayer`.

**Remarks**

Please initialize the DrawingLayers via the following methods:

- [`DCEImageEditorView.createDrawingLayer`](dceimageeditorview.md#createdrawinglayer)
- [`DCECameraView.createDrawingLayer`](dcecameraview.md#createdrawinglayer)

&nbsp;

## getId

Get the ID of the `DrawingLayer`.

```java
public int getId();
```

**Return Value**

The id of the `DrawingLayer`. It can be one of the following:

- `DEFAULT_LAYER_ID`
- `DDN_LAYER_ID`
- `DBR_LAYER_ID`
- `DLR_LAYER_ID`

**Code Snippet**

```java
DCEDrawingLayer drawingLayer = dceImageEditorView.createDrawingLayer();
int id = drawingLayer.getId();
```

&nbsp;

## addDrawingItems

Add a list of [`DrawingItems`](drawingitem.md) to the `DrawingLayer`. These [`DrawingItems`](drawingitem.md) will be appended to the drawing item list of the current `DrawingLayer`.

```java
public void addDrawingItems(Arraylist<DrawingItem> items); 
```

**Parameters**

`items`: A list of [`DrawingItems`](drawingitem.md).

**Code Snippet**

```java
ArrayList<DrawingItem> drawingItems = new ArrayList<DrawingItem>();
drawingItems.add(drawingItem_1);
drawingItems.add(drawingItem_2);
drawingItems.add(drawingItem_3);
drawingLayer.addDrawingItems(drawingItems);
```

&nbsp;

## setDrawingItems

Set a list of [`DrawingItems`](drawingitem.md) to the `DrawingLayer`. These [`DrawingItems`](drawingitem.md) will replace the previous [`DrawingItems`](drawingitem.md) of the current `DrawingLayer`.

```java
public void setDrawingItems(Arraylist<DrawingItem> items); 
```

**Parameters**

`items`: A list of [`DrawingItems`](drawingitem.md).

**Code Snippet**

```java
ArrayList<DrawingItem> drawingItems = new ArrayList<DrawingItem>();
drawingItems.add(drawingItem_1);
drawingItems.add(drawingItem_2);
drawingItems.add(drawingItem_3);
drawingLayer.setDrawingItems(drawingItems);
```

&nbsp;

## getDrawingItems

Get all available [`DrawingItems`](drawingitem.md) in the `DrawingLayer`.

```java
public Arraylist<DrawingItem> getDrawingItems();
```

**Return Value**

A list that includes all available [`DrawingItems`](drawingitem.md).

**Code Snippet**

```java
ArrayList<DrawingItem> drawingItems = dceDrawingLayer.getDrawingItems();
```

&nbsp;

## clearDrawingItems

Clear all available [`DrawingItems`](drawingitem.md) in the `DrawingLayer`.

```java
public void clearDrawingItems();
```

**Code Snippet**

```java
drawingLayer.clearDrawingItems();
```

&nbsp;

## setDrawingStyleId(styleId)

Specify a style ID for all available [`DrawingItems`](drawingitem.md).

```java
public void setDrawingStyleId(int styleId);
```

**Parameters**

`id`: The style ID.

**Code Snippet**

```java
drawingLayer.setDrawingStyleId(0);
```

&nbsp;

## setDrawingStyleId(styleId,state)

Specify a style ID for the targeting [`DrawingItems`](drawingitem.md).

```java
public void setDrawingStyleId(int styleId, EnumDrawingItemState state);
```

**Parameters**

`id`: The style ID.  
`state`: The state of the `DrawingLayer`.

**Code Snippet**

```java
drawingLayer.setDrawingStyleId(0, EnumDrawingItemState.DIS_SELECTED);
```

&nbsp;

## setDrawingStyleId(styleId,state,mediaType)

Specify a style ID for the targeting [`DrawingItems`](drawingitem.md).

```java
public void setDrawingStyleId(int styleId, EnumDrawingItemState state, EnumDrawingItemMediaType[] mediaTypes);
```

**Parameters**

`id`: The style ID.  
`state`: The state of the `DrawingLayer`.  
`mediaType`: The media type of the `DrawingLayer`.

**Code Snippet**

```java
drawingLayer.setDrawingStyleId(0, EnumDrawingItemState.DIS_SELECTED, new EnumDrawingItemMediaType[]{EnumDrawingItemMediaType.DIMT_RECTANGLE ,EnumDrawingItemMediaType.DIMT_QUADRILATERAL});
```

&nbsp;

## setVisible

Set the visibility of the `DrawingLayer`.

```java
public void setVisible(boolean visible);
```

**Parameters**

`visible`:

- true: The `DrawingLayer` will be visible
- false: The `DrawingLayer` will be invisible.

**Code Snippet**

```java
drawingLayer.setVisible(true);
```

&nbsp;

## isVisible

Get the visibility of the `DrawingLayer`.

```java
public boolean isVisible();
```

**Return Value**

- true: The `DrawingLayer` is visible.
- false: The `DrawingLayer` is invisible.

**Code Snippet**

```java
boolean visible = drawingLayer.isVisible();
```
