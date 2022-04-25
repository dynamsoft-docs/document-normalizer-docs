---
layout: default-layout
title: Detecting and Normalizing Methods
description: This page shows Detecting and Normalizing Methods of Dynamsoft Document Normalizer SDK C Edition.
keywords: DDN_DetectQuadFromBuffer, DDN_DetectQuadFromFile, DDN_NormalizeBuffer, DDN_NormalizeFile, api reference, c
---

# Detecting and Normalizing Methods

| Method               | Description |
|----------------------|-------------|
| [`DDN_DetectQuadFromBuffer`](#ddn_detectquadfrombuffer) | Detects quad from source image specified by the raw buffer. |
| [`DDN_DetectQuadFromFile`](#ddn_detectquadfromfile) | Detects quad from source image specified by file path. |
| [`DDN_NormalizeBuffer`](#ddn_normalizebuffer) | Normalizes the source image specified by file path. |
| [`DDN_NormalizeFile`](#ddn_normalizefile) | Normalizes the source image specified by raw buffer. |

## DDN_DetectQuadFromBuffer

Detects quad from source image specified by the raw buffer.

```c
int DDN_DetectQuadFromBuffer(void* normalizer, const ImageData* sourceImage, const char* templateName, DetectedQuadResultArray** result)
```

**Parameters**  
`[in] normalizer` Handle of the Dynamsoft Document Normalizer instance.

`[in] sourceImage` The source image buffer.

`[in] templateName` The template name. A template name is the value of key ImageParameter.Name defined in JSON formatted settings. If no template name is specified, current runtime settings will be used.

`[out] result` An array of all detected quad results. It is allocated by the SDK and should be freed by calling function [DDN_FreeDetectedQuadResultArray](document-normalizer-result.md#ddn_freedetectedquadresultarray).

**Return Value**  
Returns error code (returns 0 if the function operates successfully).
*You can call [`DDN_GetErrorString`](document-normalizer-general.md#ddn_geterrorstring) to get detailed error message.*

## DDN_DetectQuadFromFile

Detects quad from source image specified by file path.

```c
int DDN_DetectQuadFromFile(void* normalizer, const char* sourceFilePath, const char* templateName, DetectedQuadResultArray** result)
```

**Parameters**  
`[in] normalizer` Handle of the Dynamsoft Document Normalizer instance.

`[in] sourceFilePath` A string defining the source file path.

`[in] templateName` The template name. A template name is the value of key ImageParameter.Name defined in JSON formatted settings. If no template name is specified, current runtime settings will be used.

`[out] result` An array of all detected quad results. It is allocated by the SDK and should be freed by calling function [DDN_FreeDetectedQuadResultArray](document-normalizer-result.md#ddn_freedetectedquadresultarray).

**Return Value**  
Returns error code (returns 0 if the function operates successfully).
*You can call [`DDN_GetErrorString`](document-normalizer-general.md#ddn_geterrorstring) to get detailed error message.*

## DDN_NormalizeBuffer

Normalizes the source image specified by raw buffer.

```c
int DDN_NormalizeBuffer(void* normalizer, const ImageData* sourceImage, const char* templateName, const Quadrilateral* quad, NormalizedImageResult** result)
```

**Parameters**  
`[in] normalizer` Handle of the Dynamsoft Document Normalizer instance.

`[in] sourceImage` The source image buffer.

`[in] templateName` The template name. A template name is the value of key ImageParameter.Name defined in JSON formatted settings. If no template name is specified, current runtime settings will be used.

`[in] quad` The quadrilateral representing the boundary of the content to be normalized.

`[out] result` The normalized image result. It is allocated by the SDK and should be freed by calling function [DDN_FreeNormalizedImageResult](document-normalizer-result.md#ddn_freenormalizedimageresult).

**Return Value**  
Returns error code (returns 0 if the function operates successfully).
*You can call [`DDN_GetErrorString`](document-normalizer-general.md#ddn_geterrorstring) to get detailed error message.*

## DDN_NormalizeFile

Normalizes the source image specified by file path.

```c
int DDN_NormalizeFile(void* normalizer, const char* sourceFilePath, const char* templateName, const Quadrilateral* quad, NormalizedImageResult** result)
```

**Parameters**  
`[in] normalizer` Handle of the Dynamsoft Document Normalizer instance.

`[in] sourceFilePath` A string defining the source file path.

`[in] templateName` The template name. A template name is the value of key ImageParameter.Name defined in JSON formatted settings. If no template name is specified, current runtime settings will be used.

`[in] quad` The quadrilateral representing the boundary of the content to be normalized.

`[out] result` The normalized image result. It is allocated by the SDK and should be freed by calling function [DDN_FreeNormalizedImageResult](document-normalizer-result.md#ddn_freenormalizedimageresult).

**Return Value**  
Returns error code (returns 0 if the function operates successfully).
*You can call [`DDN_GetErrorString`](document-normalizer-general.md#ddn_geterrorstring) to get detailed error message.*
