---
layout: default-layout
title: GrayscaleTransformationModes
keywords: GrayscaleTransformationModes, parameters, reference, documentation
description: Dynamsoft Document Normalizer Parameter Reference - GrayscaleTransformationModes
---

# GrayscaleTransformationModes

`GrayscaleTransformationModes` helps control the colour mode of the grayscale image.

It consists of one or more of the following modes, each mode representing a way to transform the grayscale image.

## Candidate Mode List

- GTM_ORIGINAL
- GTM_INVERTED
- GTM_AUTO

### GTM_ORIGINAL

Keeps the original grayscale.

### GTM_INVERTED

Transforms the image to inverted grayscale.

### GTM_AUTO

Let the library choose an algorithm automatically for grayscale transformation.

## Setting Methods

### As JSON Parameter

`GrayscaleTransformationModes` as a JSON parameter is a JSON Object array defined as below.

| Parent Json Object | Key Name | Key Value |
| ------------------ | ------------------- | ---------- |
| ImageParameter | GrayscaleTransformationModes | A JSON Object array while each Object is defined as below |

| Key Name | Key Value | Description |
| -------- | --------- | ----------- |
| Mode | Any one in Candidate Mode List as string | (Required) Specifies a mode for grayscale transformation.  |

**Default Value**

```json
{
    "GrayscaleTransformationModes":[
        {
            "Mode": "GTM_ORIGINAL"
        }
    ]
}
```

**JSON Parameter Example**

```json
{
    "GrayscaleTransformationModes": [
        {
            "Mode": "GTM_ORIGINAL"
        },
        {
            "Mode": "GTM_INVERTED" 
        }
    ]
}
```
