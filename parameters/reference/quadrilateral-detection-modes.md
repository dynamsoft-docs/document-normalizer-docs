---
layout: default-layout
title: QuadrilateralDetectionModes
keywords: QuadrilateralDetectionModes, parameters, reference, documentation
description: Dynamsoft Document Normalizer Parameter Reference - QuadrilateralDetectionModes
---

# QuadrilateralDetectionModes

`QuadrilateralDetectionModes` controls the quadrilateral detection process on an image. It currently includes only one mode.

## Candidate Mode List

- QDM_GENERAL

### QDM_GENERAL

Detects quadrilateral(s) using the general algorithm.

## Setting Methods

### As JSON Parameter

`QuadrilateralDetectionModes` as a JSON parameter is a JSON Object array defined as below.

| Parent Json Object | Key Name | Key Value |
| ------------------ | ------------------- | ---------- |
| NormalizerParameter | QuadrilateralDetectionModes | A JSON Object array while each Object is defined as below |

| Key Name | Key Value | Description |
| -------- | --------- | ----------- |
| Mode | Any one in Candidate Mode List as string | (Required) Specifies a mode for quadrilateral detection.  |

**JSON Parameter Example**

```json
{
    "QuadrilateralDetectionModes": [
        {
            "Mode": "QDM_GENERAL"
        }
    ]
}
```
