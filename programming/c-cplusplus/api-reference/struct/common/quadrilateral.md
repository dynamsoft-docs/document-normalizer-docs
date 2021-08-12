---
title: Dynamsoft Content Normalizer - Quadrilateral Struct
keywords: quadrilateral, struct, api, api reference, c, c language, c++, cplusplus, dcn, documentation
description: Dynamsoft Content Normalizer - quadrilateral Struct
---

# Quadrilateral
Stores the quadrilateral.

```cpp
typedef struct tagQuadrilateral  Quadrilateral
```  

## Attributes
  
| Attribute | Type |
|---------- | ---- |
| `points`(#points) | [`DM_Point`](dm-point.md)[4] |


&nbsp;

### points
Four vertexes in a clockwise direction of a quadrilateral. Index 0 represents the left-most vertex.

```cpp
DM_Point points[4]
```
