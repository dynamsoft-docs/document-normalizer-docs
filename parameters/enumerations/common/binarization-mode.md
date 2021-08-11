---
title: Dynamsoft Content Normalizer - BinarizationMode Enumeration
keywords: binarizationmode, enumerations, enums, dcn, documentation
description: Dynamsoft Content Normalizer - BinarizationMode Enumeration
---

# BinarizationMode

## Declarations

| Language | Declaration |
| -------- | ----------- |
| C/C++ | `enum BinarizationMode` |

## Members

| Member | Value | Description | Valid Arguments |
| ------ | ----- | ----------- | --------------- |
| `BM_SKIP` | 0x00 | Skips the binarization. | `N/A` |
| `BM_AUTO` | 0x01 | **Not supported yet.** | `N/A` |
| `BM_LOCAL_BLOCK` | 0x02 | Binarizes the image based on the local block. | `BlockSizeX`<br>`BlockSizeY`<br>`EnableFillBinaryVacancy`<br>`ThresholdCompensation`<br>`MorphOperation`<br>`MorphShape`<br>`MorphOperationKernelSizeX`<br>`MorphOperationKernelSizeY` |
| `BM_THRESHOLD` | 0x04 | Binarizes the image based on a given threshold. | `BinarizationThreshold`<br>`MorphOperation`<br>`MorphShape`<br>`MorphOperationKernelSizeX`<br>`MorphOperationKernelSizeY`  |
