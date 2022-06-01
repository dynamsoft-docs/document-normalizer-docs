---
layout: default-layout
title: ContentType
keywords: ContentType, parameters, reference, documentation
description: Dynamsoft Document Normalizer Parameter Reference - ContentType
---

# ContentType

`ContentType` is a parameter to specify the target content type to be normalized.

## Setting Methods

### As Json Parameter

`ContentType` as a JSON parameter is a string value defined as below.

| Parent Json Object | Key Name | Key Value Type | Key Value Range | Key Default Value |
| ------------------ | -------- | -------------- | ----------- | ------------- |
| NormalizerParameter | ContentType | *string* | "CT_DOCUMENT"<br>"CT_TABLE"<br>"CT_UNKNOWN" | "CT_DOCUMENT" |

**Example**

```json
{
    "ContentType": "CT_TABLE",
}
```
