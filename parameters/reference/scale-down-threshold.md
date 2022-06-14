---
layout: default-layout
title: ScaleDownThreshold
keywords: ScaleDownThreshold, parameters, reference, documentation
description: Dynamsoft Document Normalizer Parameter Reference - ScaleDownThreshold
---

# ScaleDownThreshold

`ScaleDownThreshold` controls the threshold used when shrinking an image. If the shorter edge size is larger than the given value, the library will calculate the required height and width of the image and shrink the image to that size.

## Setting Methods

### As JSON Parameter

`ScaleDownThreshold` as a JSON parameter is a number value defined as below.

| Parent Json Object | Key Name | Key Value Type | Key Value Range | Key Default Value |
| ------------------ | -------- | -------------- | ----------- | ------------- |
| ImageParameter | ScaleDownThreshold | *int* | [512, 0x7fffffff] | 2300 |

**Example**

```json
{
    "ScaleDownThreshold": 2300
}
```
