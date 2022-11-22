---
layout: default-layout
title: Dynamsoft Document Normalizer C API Reference - Main Page
description: This is the main page of Dynamsoft Document Normalizer SDK API Reference for C Language.
keywords: DocumentNormalizer, api reference, C
---

# API Reference - C Edition

## Global Functions

### Initialize and Destroy

- [`DDN_CreateInstance`](document-normalizer-init.md#ddn_createinstance)
- [`DDN_DestroyInstance`](document-normalizer-init.md#ddn_destroyinstance)
- [`DC_InitLicense`](document-normalizer-init.md#dc_initlicense)
- [`DC_GetIdleInstancesCount`](document-normalizer-init.md#dc_getidleinstancescount)

### General

- [`DC_GetErrorString`](document-normalizer-general.md#dc_geterrorstring)
- [`DC_GetQuadrilateralArea`](document-normalizer-general.md#dc_getquadrilateralarea)
- [`DC_IsPointInQuadrilateral`](document-normalizer-general.md#dc_ispointinquadrilateral)
- [`DDN_GetVersion`](document-normalizer-general.md#ddn_getversion)

### Runtime Settings

- [`DDN_InitRuntimeSettingsFromFile`](document-normalizer-settings.md#ddn_initruntimesettingsfromfile)
- [`DDN_InitRuntimeSettingsFromString`](document-normalizer-settings.md#ddn_initruntimesettingsfromstring)
- [`DDN_OutputRuntimeSettingsToFile`](document-normalizer-settings.md#ddn_outputruntimesettingstofile)
- [`DDN_OutputRuntimeSettingsToString`](document-normalizer-settings.md#ddn_outputruntimesettingstostring)

### Detecting and Normalizing

- [`DDN_DetectQuadFromFile`](document-normalizer-normalizing.md#ddn_detectquadfromfile)
- [`DDN_DetectQuadFromBuffer`](document-normalizer-normalizing.md#ddn_detectquadfrombuffer)
- [`DDN_NormalizeBuffer`](document-normalizer-normalizing.md#ddn_normalizebuffer)
- [`DDN_NormalizeFile`](document-normalizer-normalizing.md#ddn_normalizefile)

### Results

- [`DDN_FreeDetectedQuadResultArray`](document-normalizer-result.md#ddn_freedetectedquadresultarray)
- [`DDN_FreeNormalizedImageResult`](document-normalizer-result.md#ddn_freenormalizedimageresult)
- [`DDN_FreeString`](document-normalizer-result.md#ddn_freestring)
- [`DDN_SaveImageDataToFile`](document-normalizer-result.md#ddn_saveimagedatatofile)

## Structs

- [`DetectedQuadResult`](detected-quad-result.md)
- [`DetectedQuadResultArray`](detected-quad-result-array.md)
- [`DM_Point`](point.md)
- [`ImageData`](image-data.md)
- [`NormalizedImageResult`](normalized-image-result.md)
- [`Quadrilateral`](quadrilateral.md)

## Enumerations

- [`ImagePixelFormat`]({{ site.enumerations }}image-pixel-format.html?src=c)

## Others

- [Error Codes]({{ site.enumerations }}error-code.html)
