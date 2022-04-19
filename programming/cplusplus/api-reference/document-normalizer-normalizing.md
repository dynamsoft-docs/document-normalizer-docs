---
layout: default-layout
title: CDocumentNormalizer - Detecting and Normalizing Methods
description: This page shows Detecting and Normalizing Methods of class CDocumentNormalizer of Dynamsoft Document Normalizer SDK C++ Edition.
keywords: DetectQuad, Normalize, CDocumentNormalizer, api reference, c++
---

# Detecting and Normalizing Methods

| Method               | Description |
|----------------------|-------------|
| [`DetectQuad`](#detectquad) | Detects quad from source image. |
| [`Normalize`](#normalize) | Normalizes the source image. |

## DetectQuad

Detects quad from source image.

```cpp
int dynamsoft::ddn::CDocumentNormalizer::DetectQuad(const char* sourceFilePath, const char* templateName, CDetectedQuadResultArray** result)

int dynamsoft::ddn::CDocumentNormalizer::DetectQuad(const CImageData* sourceImage, const char* templateName, CDetectedQuadResultArray** result)

```

**Parameters**  
`[in] sourceFilePath` A string defining the source file path.

`[in] sourceImage` The source image buffer.

`[in] templateName` The template name. A template name is the value of key ImageParameter.Name defined in JSON formatted settings. If no template name is specified, current runtime settings will be used.

`[out] result` An array of all detected quad results. It is allocated by the SDK and should be freed by calling function [FreeDetectedQuadResultArray](document-normalizer-result.md#freedetectedquadresultarray).

**Return Value**  
Returns error code (returns 0 if the function operates successfully).
*You can call [`GetErrorString`](status-retrieval.md#geterrorstring) to get detailed error message.*

## Normalize

Normalizes the source image.

```cpp
int dynamsoft::ddn::CDocumentNormalizer::Normalize(const char* sourceFilePath, const char* templateName, const CQuadrilateral* quad, CNormalizedImageResult** result)

int dynamsoft::ddn::CDocumentNormalizer::Normalize( const CImageData* sourceImage, const char* templateName, const CQuadrilateral* quad, CNormalizedImageResult ** result)

```

**Parameters**  
`[in] sourceFilePath` A string defining the source file path.

`[in] sourceImage` The source image buffer.

`[in] templateName` The template name. A template name is the value of key ImageParameter.Name defined in JSON formatted settings. If no template name is specified, current runtime settings will be used.

`[in] quad` The quadrilateral representing the boundary of the content to be normalized.

`[out] result` The normalized image result. It is allocated by the SDK and should be freed by calling function [FreeNormalizedImageResult](document-normalizer-result.md#freenormalizedimageresult).

**Return Value**  
Returns error code (returns 0 if the function operates successfully).
*You can call [`GetErrorString`](status-retrieval.md#geterrorstring) to get detailed error message.*
