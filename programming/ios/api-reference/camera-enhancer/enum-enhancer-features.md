---
layout: default-layout
title: iOS EnumEnhancerFeatures - Dynamsoft Document Normalizer Documents
description: This is the documentation - EnumEnhancerFeatures page of DynamsoftCameraEnhancer library.
keywords:  Camera Enhancer, EnumEnhancerFeatures
needAutoGenerateSidebar: true
breadcrumbText: EnumEnhancerFeatures
---

# EnumEnhancerFeatures

## Declarations

| Language | Declaration |
|----------|-------------|
| Objective-C & Swift | `enum EnumEnhancerFeatures` |

## Members

| Member (Objective-C) | Member (Swift) | Value | Description |
| -------------------- | -------------- | ----- | ----------- |
| `EnumFRAME_FILTER` | `EnumFRAME_FILTER` | 0x01 | The frame sharpness filter feature of DCE. By enabling this feature, the low-quality frame will be recognized and discarded automatically. |
| `EnumSENSOR_CONTROL` | `EnumSENSOR_CONTROL` | 0x02 | The sensor filter feature of DCE. By enabling this feature, the frames will be discarded automatically while the device is shaking. |
| `EnumENHANCED_FOCUS` | `EnumENHANCED_FOCUS` | 0x04 | The enhanced focus feature. DCE will support the camera in triggering auto-focus. |
| `EnumFAST_MODE` | `EnumFAST_MODE` | 0x08 | The fast mode of DCE. By enabling the fast mode, the frames will be cropped to speed up the following processing. |
| `EnumAUTO_ZOOM` | `EnumAUTO_ZOOM` | 0x10 | The auto-zoom feature of DCE. By enabling this feature, the camera will automatically zoom in to the interest area. |
| `EnumSMART_TORCH` | `EnumSMART_TORCH` | 0x20 | Add a smart torch on the UI. The torch will be hided when the environment brightness is high and displayed when the brightness is low. |
| `EnumALL` | `EnumALL` | 0x3f | Enable all the above features. |
