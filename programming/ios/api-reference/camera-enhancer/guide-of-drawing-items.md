---
layout: default-layout
title: iOS UI Configuration - Dynamsoft Document Normalizer Documents
description: This is the documentation - Guide on iOS page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, Guide on iOS
needAutoGenerateSidebar: true
noTitleIndex: true
needGenerateH3Content: true
breadcrumbText: iOS Guide
---

# UI Configurations Classes

| Class | Description |
| ----- | ----------- |
| [`DCECameraView`](dcecameraview.md) | The view displays video streaming and auxiliary UI elements. |
| [`DCEImageEditorView`](dceimageeditorview.md) | The view displays still image and auxiliary UI elements. |

`DCECameraView` and `DCEImageEditorView` are the main classes for user to configure the UI. `DrawingItems` are the UI elements that user can create, modify and interact on the UI view. All the `DrawingItems` are contained in `DCEDrawingLayers` and finally displayed on the `DCECameraView` or `DCEImageEditorView`.

<div align="center">
    <p><img src="../../../../assets/drawing-items.png" width="70%" alt="drawing-item"></p>
    <p>DrawingItems in DCECameraView and DCEImageEditorView</p>
</div>

## Basic Usages

&nbsp;

### Display Highlight Overlays

When `DynamsoftCameraEnhancer(DCE)` is used together with other Dynamsoft products like `DynamsoftBarcodeReader(DBR)` and `DynamsoftDocumentNormalizer(DDN)`, it can automatically draw highlight overlays (`QuadDrawingItem`) on the detected barcodes or documents. If you want to disable this feature, you can use the following code to stop drawing the highlights.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
DCEDrawingLayer *dbrLayer = [imageEditorView getDrawingLayer:DBR_LAYER_ID];
drawingLayer
```
2. 
```swift
let dbrLayer = imageEditorView.getDrawingLayer(DBR_LAYER_ID)
dbrLayer.visible = false
```

&nbsp;

### Style Configuration

You can change the style of the `DrawingItems` specifying a `DrawingStyleId`. The `DrawingStyleId` can be a preset `DrawingStyle` or a user-defined `DrawingStyle`.

To change the style of `DrawingItems` with preset `DrawingStyles`:

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
DCEDrawingLayer *dbrLayer = [imageEditorView getDrawingLayer:DBR_LAYER_ID];
// You can change the drawing style of all DrawingItems in the layer.
[dbrLayer setDrawingStyleId:DrawingStyleManager.STYLE_ORANGE_STROKE];
// You can also change the drawing style of a part of the DrawingItems.
[dbrLayer setDrawingStyleId:DrawingStyleManager.STYLE_ORANGE_STROKE state:EnumDrawingItemStateSelected mediaType:EnumDrawingItemMediaTypeRectangle];
```
2. 
```swift
let dbrLayer = imageEditorView.getDrawingLayer(DBR_LAYER_ID)
// You can change the drawing style of all DrawingItems in the layer.
dbrLayer.setDrawingStyleId(DrawingStyleManager.STYLE_ORANGE_STROKE)
// You can also change the drawing style of a part of the DrawingItems.
dbrLayer.setDrawingStyleId(DrawingStyleManager.STYLE_ORANGE_STROKE, state:EnumDrawingItemStateSelected, mediaType:EnumDrawingItemMediaTypeRectangle)
```

List of all available preset styles:

```objc
// DrawingItems on DDN layer are using this style as default.
#define STYLE_BLUE_STROKE = 1;
// DrawingItems on DBR layer are using this style as default.
#define STYLE_GREEN_STROKE = 2;
// DrawingItems on DLR layer are using this style as default.
#define STYLE_ORANGE_STROKE = 3;
// DrawingItems on user defined layer are using this style as default.
#define STYLE_YELLOW_STROKE = 4;
// DrawingItems on DDN layer are using this style as default if they are selected.
#define STYLE_BLUE_STROKE_FILL = 5;
// DrawingItems on DBR layer are using this style as default if they are selected.
#define STYLE_GREEN_STROKE_FILL = 6;
// DrawingItems on DLR layer are using this style as default if they are selected.
#define STYLE_ORANGE_STROKE_FILL = 7;
// DrawingItems on user defined layer are using this style as default if they are selected.
#define STYLE_YELLOW_STROKE_FILL = 8;
```

<div align="center">
    <p><img src="../../../../assets/drawing-styles.png" width="50%" alt="drawing-item"></p>
    <p>Preset DrawingStyles</p>
</div>

If you want to set other styles to your UI elements, you can add your personal defined `DrawingStyles`.

```swift

int myStyleId = DrawingStyleManager.createDrawingStyle(0xff00ff00,2,0xff00ff00,0xff00ff00,12,"sans-serif");
cameraView.getDrawingLayer(DCEDrawingLayer.DBR_LAYER_ID).setDrawingStyleId(myStyleId);
```

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
// Create a new DrawingStyle via DrawingStyle manager and get the style ID of the new style.
UIColor *strokeColour = [UIColor colorWithRed:0.2 green:0.3 blue:0.4 alpha:0.5];
UIColor *fillColour = [UIColor colorWithRed:0.2 green:0.3 blue:0.4 alpha:0.5];
UIColor *textColour = [UIColor colorWithRed:0.2 green:0.3 blue:0.4 alpha:0.5];
UIFont *textFont = [UIFont systemFontOfSize:12.0];
// Assign the newly created style to the targeting DrawingItems.
NSInteger myStyle = [DrawingStyleManager createDrawingStyle:strokeColour strokeWidth:2.0 fillColor:fillColour textColor:textColour font:textFont];
```
2. 
```swift
// Create a new DrawingStyle via DrawingStyle manager and get the style ID of the new style.
let strokeColor = UIColor.init(red: 0.2, green: 0.3, blue: 0.4, alpha: 0.5)
let fillColour = UIColor.init(red: 0.2, green: 0.3, blue: 0.4, alpha: 0.5)
let textColor = UIColor.init(red: 0.2, green: 0.3, blue: 0.4, alpha: 0.5)
let textFont = UIFont.systemFont(ofSize: 12, weight: UIFont.weight.light)
// Assign the newly created style to the targeting DrawingItems.
let myStyleID = DrawingStyleManager.createDrawingStyle(strokeColor, strokeWidth:1, fillColor:fillColor, textColor:textColor, font: textFont)
```

To modify the existing DrawingStyles:

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
// Get the style by ID.
DrawingStyle *myStyle = [DrawingStyleManager getDrawingStyle:STYLE_BLUE_STROKE_FILL];
// Modify the style.
myStyle.strokeColor = [UIColor colorWithRed:0.5 green:0.5 blue:0.5 alpha:0.5];
```
2. 
```swift
// Get the style by ID.
let myStyle = DrawingStyleManager.getDrawingStyle(STYLE_BLUE_STROKE_FILL)
// Modify the style.
myStyle.strokeColor = UIColor.init(red: 0.7, green: 0.7, blue: 0.7, alpha: 0.5)
```

&nbsp;

## Advanced Usages

&nbsp;

### Add User Defined UI Elements

Apart from the system-defined items, you can add your personal defined UI elements via the `DrawingItem` APIs. On this page, we will draw a user-defined `quadrilateral` on the `DCEImageEditorView` for example.

1. Create a new `QuadDrawingItem`.

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   // Create a new quadrilateral.
   iQuadrilateral *newQuad = [iQuadrilateral init];
   // Add your code to assign the quad data.
   newQuad = @[@(CGPointMake(x:0, y:0)), @(CGPointMake(x:0, y:100)), @(CGPointMake(x:100, y:100)), @(CGPointMake(x:100, y:0))];
   // Use the newly created quadrilateral to initialize the DrawingItem.
   QuadDrawingItem *newItem = [[QuadDrawingItem alloc] initWithQuad: newQuad];
   ```
   2. 
   ```swift
   // Create a new quadrilateral.
   let newQuad:iQuadrilateral = iQuadrilateral.init()
   // Add your code to assign the quad data.
   newQuad.points = [CGPoint.init(x:0, y:0), CGPoint.init(x:0, y:100), CGPoint.init(x:100, y:100), CGPoint.init(x:100, y:0)]
   // Use the newly created quadrilateral to initialize the DrawingItem.
   let newDrawingItem = QuadDrawingItem.init(quad: newQuad)
   ```

2. Add the Created `DrawingItems` to the view.

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   // Add the previously created drawingItem to an array so that it can be assigned to the drawingItems property of the layer.
   NSMutableArray<DrawingItem *> *array = [NSMutableArray array];
   [array addObject:newDrawingItem];
   // There are multiple layers in DCECameraView and DCEImageEditorView.
   // You must select a layer for your DrawingItems.
   DCEDrawingLayer *layer = [editorView getDrawingLayer:DDN_LAYER_ID];
   // Assign the array to the drawingItems of the layer.
   layer.drawingItems = array;
   ```
   2. 
   ```swift
   // Add the previously created drawingItem to an array so that it can be assigned to the drawingItems property of the layer.
   var array:[DrawingItem]? = []
   array?.append(newDrawingItem)
   // There are multiple layers in DCECameraView and DCEImageEditorView.
   // You must select a layer for your DrawingItems.
   let layer = editorView.getDrawingLayer(DDN_LAYER_ID)
   // Assign the array to the drawingItems of the layer.
   layer.drawingItems = array
   ```

&nbsp;
