---
layout: default-layout
title: Timeout
keywords: Timeout, parameters, reference, documentation
description: Dynamsoft Document Normalizer Parameter Reference - Timeout
---

# Timeout

`Timeout` is a parameter to specify the maximum amount of time (in milliseconds) that should be spent processing each image. It does not include the time taken to load/decode an image (Tiff, PNG, etc) from disk into memory.

## Setting Methods

### As JSON Parameter

`Timeout` as a JSON parameter is a number value defined as below.

| Parent Json Object | Key Name | Key Value Type | Key Value Range | Key Default Value |
| ------------------ | -------- | -------------- | ----------- | ------------- |
| ImageParameter | Timeout | *int* | [0, 0x7fffffff] | 10000 |

**Example**

```json
{
    "Timeout": 500
}
```
