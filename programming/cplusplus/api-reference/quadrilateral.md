---
layout: default-layout
title: CQuadrilateral Class
description: This page shows CQuadrilateral class definition of Dynamsoft Document Normalizer SDK C++ Edition.
keywords: CQuadrilateral, api reference
---


# CQuadrilateral

Stores the quadrilateral.  

```c++
class dynamsoft::core::CQuadrilateral
```
  
| Attribute | Type |
|---------- | ---- |
| [`points`](#points) | *CPoint[4]* |

## points

Four vertexes in a clockwise direction of a quadrilateral. Index 0 represents the left-most vertex.

```c++
CPoint points[4]
```
