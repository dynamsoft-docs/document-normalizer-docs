---
layout: default-layout
title: Quadrilateral Struct - Dynamsoft Document Normalizer SDK C Edition
description: This page shows Quadrilateral struct definition of Dynamsoft Document Normalizer SDK C Edition.
keywords: Quadrilateral, struct, api reference
---


# Quadrilateral Struct

Stores the quadrilateral.  

## Definition

```c
typedef struct tagQuadrilateral
{
    DM_Point points[4];
}Quadrilateral,*PQuadrilateral;
```

### points

Four vertexes in a clockwise direction of a quadrilateral. Index 0 represents the left-most vertex.

**See Also**

[DM_Point](point.md)
