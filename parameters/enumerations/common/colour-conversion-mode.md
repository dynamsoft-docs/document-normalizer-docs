---
title: Dynamsoft Content Normalizer - ColourConversionMode Enumeration
keywords: colourconversionmode, enumerations, enums, dcn, documentation
description: Dynamsoft Content Normalizer - ColourConversionMode Enumeration
---

# ColourConversionMode

## Declarations

| Language | Declaration |
| -------- | ----------- |
| C/C++ | `enum ColourConversionMode` |

## Members

| Member | Value | Description | Valid Arguments |
| ------ | ----- | ----------- | --------------- |
| `CICM_SKIP` | 0x00 | Skips the colour conversion. | `N/A` |
| `CICM_GENERAL` | 0x01 | Converts a colour image to a grayscale image using the general RGB converting algorithm. | `BlueChannelWeight`<br>`GreenChannelWeight`<br>`RedChannelWeight` |
| `CICM_HSV` | 0x02 | Converts a colour image to a grayscale image using one of the HSV channels. | `ReferChannel` |

