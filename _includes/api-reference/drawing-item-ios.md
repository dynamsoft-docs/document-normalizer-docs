

&nbsp;

## drawingStyleId

The property that identifies the ID of the `DrawingStyle`.

```objc
@property (assign, nonatomic) NSInteger drawingStyleId;
```

&nbsp;

## state

The property that indicates the state of the `DrawingItem`. View all available `DrawingItem` states in [`EnumDrawingItemState`]({{ site.enumerations }}enum-drawing-item-state.html).

```objc
@property (assign, nonatomic) EnumDrawingItemState state;
```

&nbsp;

## getMediaType

Get the media type of the `DrawingItem`.

```objc
- (EnumDrawingItemMediaType) getMediaType;
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

