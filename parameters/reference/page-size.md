---
layout: default-layout
title: PageSize
keywords: PageSize, parameters, reference, documentation
description: Dynamsoft Document Normalizer Parameter Reference - PageSize
---

# PageSize

Sets the page size (width by height in pixels) of the normalized image.

## Setting Methods

### As Json Parameter

`PageSize` as a JSON parameter is a string value defined as below.

| Parent Json Object | Key Name | Key Value Type | Key Value Range | Key Default Value |
| ------------------ | -------- | -------------- | ----------- | ------------- |
| NormalizerParameter | PageSize | *int array* | A value representing the page size defined as bellow | [-1, -1] |

**Remarks**

- A page size is defined as: [`TargetPageWidth`, `TargetPageHeight`]
- Allowed value range of `TargetPageWidth` and `TargetPageHeight`: [-1, 0x7fffffff]
- TargetPageWidth * TargetPageHeight < 100000000
- If any of `TargetPageWidth` and `TargetPageHeight` is 0 or -1, the original width and height of the detected content will be used.

**Example**

```json
{
    "PageSize": [210, 297]
}
```
