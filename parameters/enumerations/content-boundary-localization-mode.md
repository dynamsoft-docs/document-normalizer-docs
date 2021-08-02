---
title: Dynamsoft Content Normalizer - ContentBoundaryLocalizationMode Enumeration
keywords: contentboundarylocalizationmode, enumerations, enums, dcn, documentation
description: Dynamsoft Content Normalizer - ContentBoundaryLocalizationMode Enumeration
---

# ContentBoundaryLocalizationMode

## Declarations

| Language | Declaration |
| -------- | ----------- |
| C/C++ | `enum ContentBoundaryLocalizationMode` |

## Members

| Member | Value | Description | Valid Arguments |
| ------ | ----- | ----------- | --------------- |
| `CBLM_MANNUAL_SPECIFICATION` | 0x01 | Define the content boundary using the manually specified location. | `FirstPoint`<br>`SecondPoint`<br>`ThirdPoint`<br>`FourthPoint` |
| `CBLM_AUTO_DETECTION` | 0x02 | Define the content boundary using the result(s) of automatic detection. | `N/A` |
| `CBLM_WHOLE_IMAGE` | 0x04 | Define the content boundary using the image boundary. | `N/A` |
