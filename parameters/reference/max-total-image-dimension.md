---
layout: default-layout
title: MaxTotalImageDimension
keywords: MaxTotalImageDimension, parameters, reference, documentation
description: Dynamsoft Document Normalizer Parameter Reference - MaxTotalImageDimension
---

# MaxTotalImageDimension

`MaxTotalImageDimension` is a parameter to specify the maximum value of total dimension (in million pixel) of source images the library can process concurrently.

## Setting Methods

### As JSON Parameter

`MaxTotalImageDimension` as a JSON parameter is a number value defined as below.

| Parent Json Object | Key Name | Key Value Type | Key Value Range | Key Default Value |
| ------------------ | -------- | -------------- | --------------- | ----------------- |
| GlobalParameter | MaxTotalImageDimension | *int* | [0, 0x7fffffff] | 0 |

**Remarks**

- 0: no limitation on the total image dimension.

**Example**

```json
{
    "MaxTotalImageDimension": 0
}
```
