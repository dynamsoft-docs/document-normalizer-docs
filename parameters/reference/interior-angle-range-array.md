---
layout: default-layout
title: InteriorAngleRangeArray
keywords: InteriorAngleRangeArray, parameters, reference, documentation
description: Dynamsoft Document Normalizer Parameter Reference - InteriorAngleRangeArray
---

# InteriorAngleRangeArray

`InteriorAngleRangeArray` is a parameter to specify the ranges of angles (in degrees) of the extracted corners.

## Setting Methods

### As JSON Parameter

`InteriorAngleRangeArray` as a JSON parameter is a JSON Object array defined as below.

| Parent Json Object | Key Name | Key Value |
| ------------------ | ------------------- | ---------- |
| NormalizerParameter | InteriorAngleRangeArray | A JSON Object array while each Object is defined as below |

| Key Name | Key Value | Description | Key Default Value |
| -------- | --------- | ----------- | ----------------- |
| MinValue | A number from [0, 180] | Sets the minimum interior angle. | 70 |
| MaxValue | A number from [0, 180] | Sets the maximum interior angle. | 110 |

**JSON Example**

```json
{
    "InteriorAngleRangeArray": [
    {
        "MinValue": 70,
        "MaxValue": 110
    }
    ]
}
```
