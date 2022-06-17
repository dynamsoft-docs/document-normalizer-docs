---
layout: default-layout
title: MaxTotalImageDimension
keywords: MaxTotalImageDimension, parameters, reference, documentation
description: Dynamsoft Document Normalizer Parameter Reference - MaxTotalImageDimension
---

# MaxTotalImageDimension

`MaxTotalImageDimension` specifies the maximum value of the total dimension area (in millions of pixels) of the source images the library can process concurrently. For example, if the library is processing 10 images concurrently, and each image has dimensions of 1920x1080. Then the total area of all the images is (1920 * 1080 * 10 = 20,736,000 pixels). So if the MaxTotalImageDimension is set to a value of 20 (which would equate to 20 million pixels) then you can process only 9 of those images at a time.

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
