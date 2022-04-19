---
layout: default-layout
title: GrayscaleTransformationModes
keywords: GrayscaleTransformationModes, parameters, reference, documentation
description: Dynamsoft Document Normalizer Parameter Reference - GrayscaleTransformationModes
---

# GrayscaleTransformationModes

This parameter helps control the colour mode of the grayscale image. By default, the library can only locate the dark barcodes that stand on a light background. Assume your image has different features to default, this parameter may help configure the appropriate settings for your case.  

It consisits of one or more modes, each mode represents a way to transform the grayscale image.

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

`BinarizationModes` as a JSON parameter is a JSON Object array defined as below.

| Parent Json Object | Key Name | Key Value |
| ------------------ | ------------------- | ---------- |
| ImageParameter | GrayscaleTransformationModes | A JSON Object array while each Object is defined as below |

| Key Name | Key Value | Description |
| -------- | --------- | ----------- |
| Mode | Any one in Candidate Mode List as string | (Required) Specifies a mode for grayscale transformation.  |

**JSON Parameter Example**   
```
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
