---
title: Dynamsoft Content Normalizer - GrayscaleEnhancementMode Enumeration
keywords: grayscaleenhancementmode, enumerations, enums, dcn, documentation
description: Dynamsoft Content Normalizer - GrayscaleEnhancementMode Enumeration
---

# ColourConversionMode

## Declarations

| Language | Declaration |
| -------- | ----------- |
| C/C++ | `enum GrayscaleEnhancementMode` |

## Members

| Member | Value | Description | Valid Arguments |
| ------ | ----- | ----------- | --------------- |
| `GEM_SKIP` | 0x00 | Skips grayscale image enhancement. | `N/A` |
| `GEM_AUTO` | 0x01 | **Not supported yet.** | `N/A` |
| `GEM_GENERAL` | 0x02 | Takes the un-preprocessed grayscale image for following operations. | `N/A` |
| `GEM_GRAY_EQUALIZE` | 0x04 | Preprocesses the grayscale image using the gray equalization algorithm. | `Sensitivity` |
| `GEM_GRAY_SMOOTH` | 0x08 | Preprocesses the grayscale image using the gray smoothing algorithm. | `SmoothBlockSizeX`<br>`SmoothBlockSizeY` |
| `GEM_SHARPEN_SMOOTH` | 0x10 | Preprocesses the grayscale image using the sharpening and smoothing algorithm. | `SmoothBlockSizeX`<br>`SmoothBlockSizeY`<br>`SharpenBlockSizeX`<br>`SharpenBlockSizeY` |


