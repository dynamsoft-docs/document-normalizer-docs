---
layout: default-layout
title: GrayscaleTransformationMode Enumeration
keywords: grayscaletransformationmode, enumerations, enums, documentation
description: Dynamsoft Document Normalizer - GrayscaleTransformationMode Enumeration
---

# ColourConversionMode

## Declarations

| Language | Declaration |
| -------- | ----------- |
| C/C++ | `enum GrayscaleTransformationMode` |

## Members

| Member | Value | Description |
| ------ | ----- | ----------- |
| GTM_INVERTED | 0x01 | Transforms to inverted grayscale. Recommended for light on dark images. |
| GTM_ORIGINAL | 0x02 | Keeps the original grayscale. Recommended for dark on light images. |
| GTM_AUTO | 0x04 | Let the library choose an algorithm automatically for grayscale transformation. |
