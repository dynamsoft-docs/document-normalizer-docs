---
layout: default-layout
title: ColourMode
keywords: ColourMode, parameters, reference, documentation
description: Dynamsoft Document Normalizer Parameter Reference - ColourMode
---

# ColourMode

`ColourMode` is a parameter to specify the colour mode of the normalized image.

## Setting Methods

### As Json Parameter

`ColourMode` as a JSON parameter is a string value defined as below.

| Parent Json Object | Key Name | Key Value Type | Key Value Range | Key Default Value |
| ------------------ | -------- | -------------- | ----------- | ------------- |
| NormalizerParameter | ColourMode | *string* | "ICM_BINARY"<br>"ICM_GRAYSCALE"<br>"ICM_COLOUR" | "ICM_BINARY" |

**Example**

```json
{
    "ColourMode": "ICM_COLOUR",
}
```
