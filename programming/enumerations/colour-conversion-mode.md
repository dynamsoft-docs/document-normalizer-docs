---
layout: default-layout
title: ColourConversionMode Enumeration
keywords: colourconversionmode, enumerations, enums, documentation
description: Dynamsoft Document Normalizer - ColourConversionMode Enumeration
---

# ColourConversionMode

## Declarations

| Language | Declaration |
| -------- | ----------- |
| C/C++ | `enum ColourConversionMode` |
| Android | `class com.dynamsoft.core.EnumColourConversionMode` |
| ObjC / Swift | `enum EnumColourConversionMode` |

## Members

| Member (except ObjC/Swift) | Member (ObjC/Swift) | Value | Description | Valid Arguments |
| ------ |------ | ----- | ----------- | --------------- |
| CICM_GENERAL | EnumColourConversionModeGeneral| 0x01 | Converts a colour image to a grayscale image using the general RGB converting algorithm. | [`BlueChannelWeight`]({{ site.parameters_reference }}colour-conversion-modes.html#bluechannelweight)<br>[`GreenChannelWeight`]({{ site.parameters_reference }}colour-conversion-modes.html#greenchannelweight)<br>[`RedChannelWeight`]({{ site.parameters_reference }}colour-conversion-modes.html#redchannelweight) |
| CICM_HSV | EnumColourConversionModeHSV | 0x02 | Converts a colour image to a grayscale image using one of the HSV channels. | [`ReferChannel`]({{ site.parameters_reference }}colour-conversion-modes.html#referchannel) |
