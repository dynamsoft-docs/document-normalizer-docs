---
layout: default-layout
title: iOS DCEImageEditorView Class - Dynamsoft Document Normalizer Documents
description: Documentation page of iOS DCEImageEditorView Class of Dynamsoft Document Normalizer.
keywords:  Camera Enhancer, iOS, DCEImageEditorView
needAutoGenerateSidebar: true
noTitleIndex: true
needGenerateH3Content: true
breadcrumbText: iOS DCEImageEditorView Class
---

# DCEImageEditorView

`DCEImageEditorView` is the class that enable users to add UI configurations on a static image.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface DCEImageEditorView : UIView
```
2. 
```swift
class DCEImageEditorView : UIView
```

| Method Name | Description |
| ----------- | ----------- |
| [`setOriginalImage`](#setoriginalimage) | Set the background image of the view with an original image. |
| [`getOriginalImage`](#getoriginalimage) | Get the current backgroud image. |
| [`getDrawingLayer`](#getdrawinglayer) | Get the [`DCEDrawingLayer`](dcedrawinglayer.md) instance with the layer ID. |
| [`createDrawingLayer`](#createdrawinglayer) | Create a user-defined [`DCEDrawingLayer`](dcedrawinglayer.md) instance. |
| [`getSelectedDrawingItem`](#getselecteddrawingitem) | Get the selected drawing item. |

## setOriginalImage

Set an original image for the view.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (void) setOriginalImage:(ImageData)imageData;
```
2. 
```swift
func setOriginalImage(_ imageData: iImageData)
```

**Parameters**

`imageData`: The `imageData` of the image.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
[_imageEditorView setOriginalImage:imageData];
```
2. 
```swift
imageEditorView.setOriginalImage(imageData)
```

## getOriginalImage

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (ImageData*) getOriginalImage;
```
2. 
```swift
func getOriginalImage() -> iImageData
```

**Return Value**

The `imageData` of the image.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
ImageData* imageData = [imageEditorView getOriginalImage];
```
2. 
```swift
let imageData = imageEditorView.getOriginalImage()
```

## getDrawingLayer

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (DCEDrawingLayer*) getDrawingLayer:(NSInteger)id;
```
2. 
```swift
func getDrawingLayer(_ layerId: Int) -> DCEDrawingLayer
```

**Parameters**

`id`: The id of the drawing layer.

**Available ID List**

| Layer | ID |
| ----- | -- |
| DDN_LAYER_ID | 1 |
| DBR_LAYER_ID | 2 |
| DLR_LAYER_ID | 3 |
| USER_DEFINED_LAYER_BASE_ID | 100 |

**Return Value**

The targeting instance of [`DCEDrawingLayer`](dcedrawinglayer.md).

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
DCEDrawingLayer* drawingLayer = [imageEditorView getDrawingLayer:DBR_LAYER_ID];
```
2. 
```swift
let drawingLayer = imageEditorView.getDrawingLayer(DBR_LAYER_ID)
```

## createDrawingLayer

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (DCEDrawingLayer*) createDrawingLayer;
```
2. 
```swift
func createDrawingLayer() -> DCEDrawingLayer
```

**Return Value**

A user-defined drawing layer.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
DCEDrawingLayer* drawingLayer = [imageEditorView createDrawingLayer];
```
2. 
```swift
let drawingLayer = imageEditorView.createDrawingLayer()
```

## getSelectedDrawingItem

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (DrawingItem*) getSelectedDrawingItem;
```
2. 
```swift
func getSelectedDrawingItem() -> DrawingItem?
```

**Return Value**

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
DrawingItem* item = [imageEditorView getSelectedDrawingItem];
```
2. 
```swift
let item = imageEditorView.getSelectedDrawingItem()
```
