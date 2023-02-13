

&nbsp;

## drawingStyleId

The property that identifies the ID of the `DrawingStyle`.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (assign, nonatomic) NSInteger drawingStyleId;
```
2. 
```swift
var drawingStyleId: Int { get set }
```

&nbsp;

## state

The property that indicates the state of the `DrawingItem`. View all available `DrawingItem` states in [`EnumDrawingItemState`]({{ site.ios_camera_enhancer }}enum-drawing-item-state.html).

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (assign, nonatomic) EnumDrawingItemState state;
```
2. 
```swift
var state: EnumDrawingItemState { get set }
```

&nbsp;

## getMediaType

Get the media type of the `DrawingItem`.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (EnumDrawingItemMediaType) getMediaType;
```
2. 
```swift
func getMediaType() -> EnumDrawingItemMediaType
```

**Return Value**

The media type of the `DrawingItem`.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
EnumDrawingItemMediaType mediaType = [drawingItem getMediaType];
```
2. 
```swift
let mediaType = drawingItem.getMediaType()
```

