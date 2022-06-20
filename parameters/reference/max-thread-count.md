---
layout: default-layout
title: MaxThreadCount
keywords: MaxThreadCount, parameters, reference, documentation
description: Dynamsoft Document Normalizer Parameter Reference - MaxThreadCount
---

# MaxThreadCount

`MaxThreadCount` specifies the number of threads the image processing algorithm will use.

## Setting Methods

### As JSON Parameter

`MaxThreadCount` as a JSON parameter is a number value defined as below.

| Parent Json Object | Key Name | Key Value Type | Key Value Range | Key Default Value |
| ------------------ | -------- | -------------- | ----------- | ------------- |
| ImageParameter | MaxThreadCount | *int* | [1, 4] | 4 |

**Example**

```json
{
    "MaxThreadCount": 1
}
```
