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
| Android | `class com.dynamsoft.core.EnumTextureDetectionMode` |
| ObjC / Swift | `enum EnumTextureDetectionMode` |

## Members

| Member (except ObjC/Swift) | Member (ObjC/Swift) | Value | Description | Valid Argument(s) |
| -------------------------- | ------------------- | ----- | ----------- | ----------------- |
| TDM_SKIP  | EnumTextureDetectionModeSkip | 0x00 | Skips texture detection. | `N/A` |
| TDM_AUTO  | EnumTextureDetectionModeAuto | 0x01 | **Not supported yet.** | `N/A` |
| TDM_GENERAL_WIDTH_CONCENTRATION  | EnumTextureDetectionModeGeneralWidthConcentration | 0x02 | Detects texture using the general algorithm. | [`Sensitivity`]({{ site.parameters_reference }}texture-detection-modes.html#sensitivity) |
