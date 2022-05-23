


&nbsp;

## getDrawingStyleId

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

```java
public EnumDrawingItemState getState();
```

**Return Value**

The value that indicates the state of the `DrawingItem`. View all available `DrawingItem` states in [`EnumDrawingItemState`](enum-drawing-item-state.md).

**Code Snippet**

```java
EnumDrawingItemState state = drawingItem.getState();
```

&nbsp;

## setState

```java
public void setState(EnumDrawingItemState state);
```

**Parameters**

`state`: The value that indicates the state of the `DrawingItem`. View all available `DrawingItem` states in [`EnumDrawingItemState`](enum-drawing-item-state.md).

**Code Snippet**

```java
drawingItem.setState(EnumDrawingItemState.DIS_SELECTED)
```

&nbsp;
