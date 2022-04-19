---
layout: default-layout
title: TextFilterMode Enumeration
keywords: TextFilterMode, enumerations, enums, documentation
description: Dynamsoft Document Normalizer - TextFilterMode Enumeration
---

# TextFilterMode

## Declarations

| Language | Declaration |
| -------- | ----------- |
| C/C++ | `enum TextFilterMode` |

## Members

| Member | Value | Description | Valid Arguments |
| ------ | ----- | ----------- | --------------- |
| TFM_SKIP | 0x00 | Skip the text filtering. | `N/A` |
| TFM_AUTO | 0x01 | **Not supported yet.** | `N/A` |
| TFM_GENERAL_CONTOUR | 0x02 | Filters text using the general algorithm based on contour. | [`IfEraseTextZone`]({{ site.parameters_reference }}text-filter-modes.html#iferasetextzone)<br>[`MinImageDimension`]({{ site.parameters_reference }}text-filter-modes.html#minimagedimension)<br>[`Sensitivity`]({{ site.parameters_reference }}text-filter-modes.html#sensitivity) |
