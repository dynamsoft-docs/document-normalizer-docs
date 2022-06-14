---
layout: default-layout
title: DeskewMode
keywords: DeskewMode, parameters, reference, documentation
description: Dynamsoft Document Normalizer Parameter Reference - DeskewMode
---

# DeskewMode

`DeskewMode` specifies the method in which the deskew process way used to apply the deskew process on the target normalized image. It consisits one of one following candidate modes, each mode represents an implement.

## Candidate Mode List

- DM_PERSPECTIVE_CORRECTION

### DM_PERSPECTIVE_CORRECTION

Deskew the document by applying perspective correction process. This mode has the following arguments for further customizing.

- [ContentDirection](#contentdirection)

## Setting Methods

### As JSON Parameter

`DeskewMode` as a JSON parameter is a JSON Object defined as below.

| Parent Json Object | Key Name | Key Value |
| ------------------ | ------------------- | ---------- |
| ImageParameter | DeskewMode | A JSON Object defined as below |

| Key Name | Key Value | Description |
| -------- | --------- | ----------- |
| Mode | Any one in Candidate Mode List as string | (Required) Specifies a mode for deskewing.  |
| ContentDirection | A number from value range of ContentDirection | (Optional) Sets the Argument [ContentDirection](#contentdirection). |

**JSON Parameter Example**

```json
{
    "DeskewMode": {
        "Mode": "DM_PERSPECTIVE_CORRECTION", 
        "ContentDirection": 0
    }
}
```

## Candidate Argument List

- [ContentDirection](#contentdirection)

### ContentDirection

Sets the direction of the document to be normalized.

| Value Type | Value Range | Default Value | Valid For |
| ---------- | ----------- | ------------- | --------- |
| *int* | [0, 2] | 0 | DM_PERSPECTIVE_CORRECTION |

**Remarks**

- 0: Direction unknown.
- 1: Vertical direction.
- 2: Horizontal direction.
