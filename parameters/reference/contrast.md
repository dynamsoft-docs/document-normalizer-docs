---
layout: default-layout
title: Contrast
keywords: Contrast, parameters, reference, documentation
description: Dynamsoft Document Normalizer Parameter Reference - Contrast
---

# Contrast

`Contrast` specifies the contrast of the normalized image.

## Setting Methods

### As Json Parameter

`Contrast` as a JSON parameter is a number value defined as below.

| Parent Json Object | Key Name | Key Value Type | Key Value Range | Key Default Value |
| ------------------ | -------- | -------------- | ----------- | ------------- |
| NormalizerParameter | Contrast | *int* | [-100, 100] | 0 |

**Example**

```json
{
    "Contrast": 50,
}
```
