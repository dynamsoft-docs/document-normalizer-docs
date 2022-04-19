---
layout: default-layout
title: TextureDetectionMode Enumeration
keywords: texturedetectionmode, enumerations, enums, documentation
description: Dynamsoft Document Normalizer - TextureDetectionMode Enumeration
---

# TextureDetectionMode

## Declarations

| Language | Declaration |
| -------- | ----------- |
| C/C++ | `enum TextureDetectionMode` |

## Members

| Member | Value | Description | Valid Arguments |
| ------ | ----- | ----------- | --------------- |
| TDM_SKIP | 0x00 | Skips texture detection. | `N/A` |
| TDM_AUTO | 0x01 | **Not supported yet.** | `N/A` |
| TDM_GENERAL_WIDTH_CONCENTRATION | 0x02 | Detects texture using the general algorithm. | [`Sensitivity`]({{ site.parameters_reference }}texture-detection-modes.html#sensitivity) |
