---
layout: default-layout
title: BinarizationMode Enumeration
keywords: binarizationmode, enumerations, enums, documentation
description: Dynamsoft Document Normalizer - BinarizationMode Enumeration
---

# BinarizationMode

## Declarations

| Language | Declaration |
| -------- | ----------- |
| C/C++ | `enum BinarizationMode` |
| Android | `class com.dynamsoft.core.EnumBinarizationMode` |
| ObjC / Swift | `enum EnumBinarizationMode` |

## Members

| Member (except ObjC/Swift) | Member (ObjC/Swift) | Value | Description | Valid Arguments |
| ------ |------ | ----- | ----------- | --------------- |
| BM_LOCAL_BLOCK | EnumBinarizationModeLocalBlock| 0x02 | Binarizes the image based on the local block. | [`BlockSizeX`]({{ site.parameters_reference }}binarization-modes.html#blocksizex)<br>[`BlockSizeY`]({{ site.parameters_reference }}binarization-modes.html#blocksizey)<br>[`EnableFillBinaryVacancy`]({{ site.parameters_reference }}binarization-modes.html#enablefillbinaryvacancy)<br>[`ThresholdCompensation`]({{ site.parameters_reference }}binarization-modes.html#thresholdcompensation)<br>[`MorphOperation`]({{ site.parameters_reference }}binarization-modes.html#morphoperation)<br>[`MorphShape`]({{ site.parameters_reference }}binarization-modes.html#morphshape)<br>[`MorphOperationKernelSizeX`]({{ site.parameters_reference }}binarization-modes.html#morphoperationkernelsizex)<br>[`MorphOperationKernelSizeY`]({{ site.parameters_reference }}binarization-modes.html#morphoperationkernelsizey) |
| BM_THRESHOLD | EnumBinarizationModeThreshold | 0x04 | Binarizes the image based on a given threshold. | [`BinarizationThreshold`]({{ site.parameters_reference }}binarization-modes.html#binarizationthreshold)<br>[`MorphOperation`]({{ site.parameters_reference }}binarization-modes.html#morphoperation)<br>[`MorphShape`]({{ site.parameters_reference }}binarization-modes.html#morphshape)<br>[`MorphOperationKernelSizeX`]({{ site.parameters_reference }}binarization-modes.html#morphoperationkernelsizex)<br>[`MorphOperationKernelSizeY`]({{ site.parameters_reference }}binarization-modes.html#morphoperationkernelsizey) |
