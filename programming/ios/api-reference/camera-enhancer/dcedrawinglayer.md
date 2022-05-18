---
layout: default-layout
title: Dynamsoft Camera Enhancer - iOS DCEDrawingLayer Class
description: This is the documentation - iOS DCEDrawingLayer Class page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, iOS, DCEDrawingLayer
needAutoGenerateSidebar: true
noTitleIndex: true
needGenerateH3Content: true
breadcrumbText: iOS DCEDrawingLayer Class
---

# DCEDrawingLayer

The layers that contains `DrawingItems`. Users can add configurations for the `DrawingItems` via `DCEDrawingLayer`

```objc
@interface DCEDrawingLayer
```

| Method Name | Description |
| ----------- | ----------- |
| [`initWithId`](#dcedrawinglayer) | The constructor of the `DCEDrawingLayer` class. |
| [`id`](#id) | Get the `DrawingLayer` ID of the `DrawingLayer`. |
| [`drawingItems`](#drawingitems) | A list of `DrawingItems`. |
| [`addDrawingItems`](#adddrawingitems) | Add a list of `DrawingItems` to the `DrawingLayer`. These `DrawingItems` will be appended to the `DrawingItem` list of the current `DrawingLayer`. |
| [`setDrawingStyleId`](#setdrawingstyleid) | Set the `DrawingStyle` of the `DrawingLayer` by ID. |
| [`setDrawingStyleId:state:`](#setdrawingstyleidstate) | Set the `DrawingStyle` of the `DrawingLayer` by ID. |
| [`setDrawingStyleId:state:mediaType:`](#setdrawingstyleidstatemediatype) | Set the `DrawingStyle` of the `DrawingLayer` by ID. |
| [`visible`](#visible) | The property that stores the visibility of the `DrawingLayer`. |

&nbsp;

## initWithId

The constructor of the [`DCEDrawingLayer`](dcedrawinglayer.md) class. Initialize the instance of the [`DCEDrawingLayer`](dcedrawinglayer.md) class.

```objc
- (instancetype) initWithId:(NSInteger)id;
```

**Parameters**

`id`: Indicates the id of the layer.

**Remarks**

Please initialize the DrawingLayers via the following methods:

- [`DCEImageEditorView.createDrawingLayer`](dceimageeditorview.md#createdrawinglayer)
- [`DCECameraView.createDrawingLayer`](dcecameraview.md#createdrawinglayer)

&nbsp;

## id

The ID of the `DrawingLayer`.

```objc
@property (assign, nonatomic) NSInteger id;
```

&nbsp;

## drawingItems

The property that stores all the `DrawingItems` on the layer. This property determines which `DrawingItems` will be displayed on the layer.

```objc
@property (nonatomic, strong, readwrite, nullable) NSArray<DrawingItem *> *drawingItems;
```

## addDrawingItems

Add a list of `DrawingItems` to the `DrawingLayer`. These `DrawingItems` will be appended to the property `drawingItems`.

```objc
- (void) addDrawingItems:(NSArray<DrawingItem*>*)items; 
```

**Parameters**

`items`: A list of `DrawingItems`.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
// Create a new DrawingItem array.
NSMutableArray<DrawingItem *> *array = [NSMutableArray array];
// You can append QuadDrawingItems, RectDrawingItems and TextDrawingItems in the array.
// For example, we use QuadDrawingItems here. The quad data here is obtained from Dynamsoft Document Normalizer
for (iDetectedQuadResult *detectedQuadResult in [StaticClass instance].quadArr) {
   iQuadrilateral *quad = detectedQuadResult.location;
   QuadDrawingItem *quadItem = [[QuadDrawingItem alloc] initWithQuad:quad];
   [array addObject:quadItem];
}
layer.drawingItems = array;
```
2. 
```swift
// Create a new DrawingItem array.
var array:[DrawingItem]? = []
// You can append QuadDrawingItems, RectDrawingItems and TextDrawingItems in the array.
// For example, we use QuadDrawingItems here. The quad data here is obtained from Dynamsoft Document Normalizer
for detectQuadResult in StaticClass.instance.quadArray{
   let quad = detectQuadResult.location
   let quadItem = QuadDrawingItem.init(quad: quad)
   array?.append(quadItem)
}
// Assign the new DrawingItem array to the drawingItems.
layer.drawingItems = array
```

&nbsp;

## setDrawingStyleId

Specify a style ID for all available `DrawingItems`.

```objc
- (void) setDrawingStyleId:(NSInteger)styleId;
```

**Parameters**

`styleId`: The style ID.  

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
[drawingLayer setDrawingStyleId:0];
```
2. 
```swift
drawingLayer.setDrawingStyleId(0)
```

&nbsp;

## setDrawingStyleId:state:

Specify a style ID for the targeting `DrawingItems`.

```objc
- (void) setDrawingStyleId:(NSInteger)styleId
                     state:(EnumDrawingItemState)state;
```

**Parameters**

`styleId`: The style ID.  
`state`: The state of the `DrawingLayer`.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
[drawingLayer setDrawingStyleId:0 state:EnumDrawingItemStateSelected];
```
2. 
```swift
drawingLayer.setDrawingStyleId(0, state:EnumDrawingItemState.selected)
```

&nbsp;

## setDrawingStyleId:state:mediaType:

Specify a style ID for the targeting `DrawingItems`.

```objc
- (void) setDrawingStyleId:(NSInteger)styleId
                     state:(EnumDrawingItemState)state
                mediaTypes:(NSArray*)mediaTypes;
```

**Parameters**

`styleId`: The style ID.  
`state`: The state of the `DrawingLayer`.  
`mediaType`: The media type of the `DrawingLayer`.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
[drawingLayer setDrawingStyleId:0 state:EnumDrawingItemStateSelected mediaType:@[@(EnumDrawingItemMediaTypeRectangle), @(EnumDrawingItemMediaTypeQuadrilateral)]];
```
2. 
```swift
drawingLayer.setDrawingStyleId(0, state:EnumDrawingItemState.selected, mediaType:[EnumDrawingItemMediaType.quadrilateral.rawValue, EnumDrawingItemMediaType.rectangle.rawValue])
```

&nbsp;

## visible

The property that stores the visibility of the `DrawingLayer`.

```objc

@property (assign, nonatomic) BOOL visible;
```

**Remarks**

When visible is true, the `DrawingLayer` is visible. Otherwise, the `DrawingLayer` is invisible.
