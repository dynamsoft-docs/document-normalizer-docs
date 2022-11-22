---
layout: default-layout
title: DM_Point Struct - Dynamsoft Document Normalizer SDK C Edition
description: This page shows DM_Point struct definition of Dynamsoft Document Normalizer SDK C Edition.
keywords: DM_Point, struct, api reference
---

# DM_Point Struct

Stores the point.

## Definition

```c
typedef struct tagDMPoint
{
    int coordinate[2];
}DM_Point;
```

### coordinate

The coordinate defining a point. coordinate\[0\] represents the X coordinate and coordinate\[1\] represents the Y coordinate of the point.
