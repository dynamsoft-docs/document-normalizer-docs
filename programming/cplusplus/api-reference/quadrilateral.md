---
layout: default-layout
title: CQuadrilateral Class
description: This page shows CQuadrilateral class definition of Dynamsoft Document Normalizer SDK C++ Edition.
keywords: CQuadrilateral, api reference
---


# CQuadrilateral

Stores the quadrilateral.  

```cpp
class dynamsoft::core::CQuadrilateral
```
  
| Attribute | Type |
|---------- | ---- |
| [`points`](#points) | *CPoint[4]* |

| Method | Description |
|--------|-------------|
| [`GetArea`](#getarea) | Returns the area of the quadrilateral. |
| [`IsPointInQuadrilateral`](#ispointinquadrilateral) | Returns whether the point is in the quadrilateral. |

## points

Four vertexes in a clockwise direction of a quadrilateral. Index 0 represents the left-most vertex.

```cpp
CPoint points[4]
```

## GetArea

Returns the area of the quadrilateral.

```cpp
int GetArea()
```

**Return Value**

The area of the quadrilateral.

## IsPointInQuadrilateral

Returns whether the point is in the quadrilateral.

```c
bool IsPointInQuadrilateral(const CPoint* point)
```

**Parameters**

`[in] point` The point.

**Return Value**

A boolean value representing whether the point is in the quadrilateral.

**See Also**

[`CPoint`](point.md)
