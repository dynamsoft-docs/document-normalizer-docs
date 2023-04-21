---
layout: default-layout
title: TextureDetectionModes
keywords: TextureDetectionModes, parameters, reference, documentation
description: Dynamsoft Document Normalizer Parameter Reference - TextureDetectionModes
---

# TextureDetectionModes

`TextureDetectionModes` controls how to detect texture on an image. It currently only supports a single mode for texture detection.

## Candidate Mode List

- TDM_GENERAL_WIDTH_CONCENTRATION

### TDM_GENERAL_WIDTH_CONCENTRATION

Detects texture using the general algorithm. This mode has the following arguments for further customization.

- [Sensitivity](#sensitivity)

## Setting Methods

### As JSON Parameter

`TextureDetectionModes` as a JSON parameter is a JSON Object array defined as below.

| Parent Json Object | Key Name | Key Value |
| ------------------ | ------------------- | ---------- |
| ImageParameter | TextureDetectionModes | A JSON Object array while each Object is defined as below |

| Key Name | Key Value | Description |
| -------- | --------- | ----------- |
| Mode | Any one in Candidate Mode List as string | (Required) Specifies a mode for text filtering.  |
| Sensitivity | A number from value range of Sensitivity | (Optional) Sets the Argument [Sensitivity](#sensitivity). |

**Default Value**

```json
{
    "TextureDetectionModes":[
        {
            "Mode": "TDM_GENERAL_WIDTH_CONCENTRATION",
            "Sensitivity": 5
        }
    ]
}
```

**JSON Parameter Example**

```json
{
    "TextureDetectionModes": [
        {
            "Mode": "TDM_GENERAL_WIDTH_CONCENTRATION", 
            "Sensitivity": 1
        },
        {
            "Mode": "TDM_GENERAL_WIDTH_CONCENTRATION", 
            "Sensitivity": 9
        }
    ]
}
```

## Candidate Argument List

- [Sensitivity](#sensitivity)

### Sensitivity

Sets the sensitivity used for texture detection.

| Value Type | Value Range | Default Value | Valid For |
| ---------- | ----------- | ------------- | --------- |
| *int* | [1, 9] | 5 | TDM_GENERAL_WIDTH_CONCENTRATION |

**Remarks**

A larger value means the library will take more effort to detect texture.
