---
layout: default-layout
title: DetectedQuadResultArray Struct - Dynamsoft Document Normalizer SDK C Edition
description: This page shows DetectedQuadResultArray struct definition of Dynamsoft Document Normalizer SDK C Edition.
keywords: DetectedQuadResultArray, struct, api reference
---

# DetectedQuadResultArray Struct

An array storing detected quad results.

## Definition

```c
typedef struct tagDetectedQuadResultArray
{
    int resultsCount;
    PDetectedQuadResult *detectedQuadResults;
}DetectedQuadResultArray;
```

### resultsCount

The count of detected quad results in the array.

### detectedQuadResults

The detected quad result array.

**See Also**

[DetectedQuadResult](detected-quad-result.md)
