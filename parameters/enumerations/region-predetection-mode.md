---
layout: default-layout
title: RegionPredetectionMode Enumeration
keywords: RegionPredetectionMode, enumerations, enums, documentation
description: Dynamsoft Document Normalizer - RegionPredetectionMode Enumeration
---

# RegionPredetectionMode

## Declarations

| Language | Declaration |
| -------- | ----------- |
| C/C++ | `enum RegionPredetectionMode` |

## Members

| Member | Value | Description | Valid Arguments |
| ------ | ----- | ----------- | --------------- |
| RPM_SKIP | 0x00 | Skips region detection. | `N/A` |
| RPM_AUTO | 0x01 | Lets the library choose an algorithm automatically to detect region. | `N/A` |
| RPM_GENERAL | 0x02 | Takes the whole image as a region. | `N/A` |
| RPM_GENERAL_RGB_CONTRAST | 0x04 | Detects region using the general algorithm based on RGB colour contrast. | [`ImageParameterName`]({{ site.parameters_reference }}region-predetection-modes.html#imageparametername)<br>[`MinImageDimension`]({{ site.parameters_reference }}region-predetection-modes.html#minimagedimension)<br>[`Sensitivity`]({{ site.parameters_reference }}region-predetection-modes.html#sensitivity)<br>[`RelativeRegions`]({{ site.parameters_reference }}region-predetection-modes.html#relativeregions)<br>[`SpatialIndexBlockSize`]({{ site.parameters_reference }}region-predetection-modes.html#spatialindexblocksize) |
| RPM_GENERAL_GRAY_CONTRAST | 0x08 | Detects region using the general algorithm based on gray contrast. | [`ImageParameterName`]({{ site.parameters_reference }}region-predetection-modes.html#imageparametername)<br>[`MinImageDimension`]({{ site.parameters_reference }}region-predetection-modes.html#minimagedimension)<br>[`Sensitivity`]({{ site.parameters_reference }}region-predetection-modes.html#sensitivity)<br>[`RelativeRegions`]({{ site.parameters_reference }}region-predetection-modes.html#relativeregions)<br>[`SpatialIndexBlockSize`]({{ site.parameters_reference }}region-predetection-modes.html#spatialindexblocksize) |
| RPM_GENERAL_HSV_CONTRAST | 0x10 | Detects region using the general algorithm based on HSV colour contrast. | [`AspectRatioRange`]({{ site.parameters_reference }}region-predetection-modes.html#aspectratiorange)<br>[`FindAccurateBoundary`]({{ site.parameters_reference }}region-predetection-modes.html#findaccurateboundary)<br>[`ForeAndBackgroundColours`]({{ site.parameters_reference }}region-predetection-modes.html#foreandbackgroundcolours)<br>[`HeightRange`]({{ site.parameters_reference }}region-predetection-modes.html#heightrange)<br>[`ImageParameterName`]({{ site.parameters_reference }}region-predetection-modes.html#imageparametername)<br>[`MinImageDimension`]({{ site.parameters_reference }}region-predetection-modes.html#minimagedimension)<br>[`RelativeRegions`]({{ site.parameters_reference }}region-predetection-modes.html#relativeregions)<br>[`Sensitivity`]({{ site.parameters_reference }}region-predetection-modes.html#sensitivity)<br>[`SpatialIndexBlockSize`]({{ site.parameters_reference }}region-predetection-modes.html#spatialindexblocksize)<br>[`WidthRange`]({{ site.parameters_reference }}region-predetection-modes.html#widthrange) |
| RPM_MANUAL_SPECIFICATION | 0x20 | Defines a region directly by specifying the coordinate. | [`FirstPoint`]({{ site.parameters_reference }}region-predetection-modes.html#firstpoint)<br>[`FourthPoint`]({{ site.parameters_reference }}region-predetection-modes.html#fourthpoint)<br>[`ImageParameterName`]({{ site.parameters_reference }}region-predetection-modes.html#imageparametername)<br>[`MeasuredByPercentage`]({{ site.parameters_reference }}region-predetection-modes.html#measuredbypercentage)<br>[`RelativeRegions`]({{ site.parameters_reference }}region-predetection-modes.html#relativeregions)<br>[`SecondPoint`]({{ site.parameters_reference }}region-predetection-modes.html#secondpoint)<br>[`ThirdPoint`]({{ site.parameters_reference }}region-predetection-modes.html#thirdpoint)<br> |
