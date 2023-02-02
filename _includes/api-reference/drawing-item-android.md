


&nbsp;

## getDrawingStyleId

Get the ID of the `DrawingStyle` that is applied on this `DrawingItem`.

```java
public int getDrawingStyleId();
```

**Return Value**

An int value that representing the style ID.

**Code Snippet**

```java
int styleId = drawingItem.getDrawingStyleId();
```

&nbsp;

## setDrawingStyleId

Set a `DrawingStyle` by ID for the `DrawingItem`.

```java
public void setDrawingStyleId(int style);
```

**Parameters**

`style`: An int value that representing the style ID.

**Code Snippet**

```java
drawingItem.setDrawingStyleId(0);
```

&nbsp;

## getState

Get the status of the `DrawingItem`.

```java
public EnumDrawingItemState getState();
```

**Return Value**

The value that indicates the state of the `DrawingItem`. View all available `DrawingItem` states in [`EnumDrawingItemState`]({{ site.android_camera_enhancer }}enum-drawing-item-state.html).

**Code Snippet**

```java
EnumDrawingItemState state = drawingItem.getState();
```

&nbsp;

## setState

Set the status of the `DrawingItem`.

```java
public void setState(EnumDrawingItemState state);
```

**Parameters**

`state`: The value that indicates the state of the `DrawingItem`. View all available `DrawingItem` states in [`EnumDrawingItemState`]({{ site.android_camera_enhancer }}enum-drawing-item-state.html).

**Code Snippet**

```java
drawingItem.setState(EnumDrawingItemState.DIS_SELECTED)
```

&nbsp;
