---
layout: default-layout
title: Android EnumEnhancerFeatures - Dynamsoft Document Normalizer Documents
description: Documentation page of Android EnumEnhancerFeatures of Dynamsoft Document Normalizer.
keywords:  Camera Enhancer, EnumEnhancerFeatures
needAutoGenerateSidebar: true
breadcrumbText: EnumEnhancerFeatures
---

# EnumEnhancerFeatures

## Declarations

| Language | Declaration |
|----------|-------------|
| Java(Android) | `class EnumEnhancerFeatures` |

## Members

| Member (Android) | Value | Description |
| ---------------- | ----- | ----------- |
| `EF_FRAME_FILTER` | 0x01 | The frame sharpness filter feature of DCE. By enabling this feature, the low-quality frame will be recognized and discarded automatically. |
| `EF_SENSOR_CONTROL` | 0x02 | The sensor filter feature of DCE. By enabling this feature, the frames will be discarded automatically while the device is shaking. |
| `EF_ENHANCED_FOCUS` | 0x04 | The enhanced focus feature. DCE will support the camera in triggering auto-focus. |
| `EF_FAST_MODE` | 0x08 | The fast mode of DCE. By enabling the fast mode, the frames will be cropped to speed up the following processing. |
| `EF_AUTO_ZOOM` | 0x10 | The auto-zoom feature of DCE. By enabling this feature, the camera will automatically zoom in to the interest area. |
| `EF_SMART_TORCH` | 0x20 | Add a smart torch on the UI. The torch will be hided when the environment brightness is high and displayed when the brightness is low. |
| `EF_ALL` | 0x3f | Enable all the above features. |
