---
title: Dynamsoft Content Normalizer - GrayscaleTransformationMode Enumeration
keywords: grayscaletransformationmode, enumerations, enums, dcn, documentation
description: Dynamsoft Content Normalizer - GrayscaleTransformationMode Enumeration
---

# ColourConversionMode

## Declarations

| Language | Declaration |
| -------- | ----------- |
| C/C++ | `enum GrayscaleTransformationMode` |

## Members

| Member | Value | Description | 
| ------ | ----- | ----------- |
| `GTM_SKIP` | 0x00 | Skips grayscale transformation. | 
| `GTM_INVERTED` | 0x01 | Transforms to inverted grayscale. Recommended for light on dark images. | 
| `GTM_ORIGINAL` | 0x02 | Keeps the original grayscale. Recommended for dark on light images. | 
| `GTM_AUTO` | 0x04 | Let the library choose an algorithm automatically for grayscale transformation. | 
