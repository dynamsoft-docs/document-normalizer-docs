---
layout: default-layout
title: GrayscaleEnhancementMode Enumeration
keywords: grayscaleenhancementmode, enumerations, enums, documentation
description: Dynamsoft Document Normalizer - GrayscaleEnhancementMode Enumeration
---

# GrayscaleEnhancementMode

## Declarations

| Language | Declaration |
| -------- | ----------- |
| C/C++ | `enum GrayscaleEnhancementMode` |
| Android | `class com.dynamsoft.core.EnumGrayscaleEnhancementMode` |
| ObjC / Swift | `enum EnumGrayscaleEnhancementMode` |

## Members

| Member (except ObjC/Swift) | Member (ObjC/Swift) | Value | Description | Valid Arguments |
| ------ | ------ |----- | ----------- | --------------- |
| GEM_GENERAL | EnumGrayscaleEnhancementModeGeneral| 0x02 | Takes the un-preprocessed grayscale image for following operations. | `N/A` |
| GEM_GRAY_EQUALIZE | EnumGrayscaleEnhancementModeGrayEqualize| 0x04 | Preprocesses the grayscale image using the gray equalization algorithm. | [`Sensitivity`]({{ site.parameters_reference }}grayscale-enhancement-modes.html#sensitivity) |
| GEM_GRAY_SMOOTH | EnumGrayscaleEnhancementModeGraySmooth| 0x08 | Preprocesses the grayscale image using the gray smoothing algorithm. | [`SmoothBlockSizeX`]({{ site.parameters_reference }}grayscale-enhancement-modes.html#smoothblocksizex)<br>[`SmoothBlockSizeY`]({{ site.parameters_reference }}grayscale-enhancement-modes.html#smoothblocksizey) |
| GEM_SHARPEN_SMOOTH | EnumGrayscaleEnhancementModeSharppenSmooth| 0x10 | Preprocesses the grayscale image using the sharpening and smoothing algorithm. | [`SmoothBlockSizeX`]({{ site.parameters_reference }}grayscale-enhancement-modes.html#smoothblocksizex)<br>[`SmoothBlockSizeY`]({{ site.parameters_reference }}grayscale-enhancement-modes.html#smoothblocksizey)<br>[`SharpenBlockSizeX`]({{ site.parameters_reference }}grayscale-enhancement-modes.html#sharpenblocksizex)<br>[`SharpenBlockSizeY`]({{ site.parameters_reference }}grayscale-enhancement-modes.html#sharpenblocksizey) |
