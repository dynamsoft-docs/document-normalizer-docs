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

`[in] sourceFilePath` A string defining the source file path. It supports BMP, JPEG, PNG, TIFF and PDF files.

`[in] sourceImage` The source image buffer.

`[in] templateName` The template name. A template name is the value of key ImageParameter.Name defined in JSON formatted settings. If no template name is specified, current runtime settings will be used.

`[out] result` An array of all detected quad results. It is allocated by the SDK and should be freed by calling function [`FreeDetectedQuadResultArray`](document-normalizer-result.md#freedetectedquadresultarray).

**Return Value**  
Returns error code (returns 0 if the function operates successfully).

*You can call [`DC_GetErrorString`](document-normalizer-general.md#dc_geterrorstring) to get detailed error message.*

**Code Snippet**

```cpp
int errorCode = 0;
char szErrorMsg[256];
errorCode = CLicenseManager::InitLicense("YOUR-LICENSE-KEY", szErrorMsg, 256);
//...handle the errorCode
CDocumentNormalizer ddn;
CDetectedQuadResultArray* detectedQuadResultArray = NULL;
errorCode = ddn.DetectQuad("YOUR-SOURCE-FILE-PATH", "", &detectedQuadResultArray);
//generate imageData from somewhere else
//errorCode = ddn.DetectQuad(imageData, "", &detectedQuadResultArray);
//...do something with the detectedQuadResultArray and errorCode
CDocumentNormalizer::FreeDetectedQuadResultArray(&detectedQuadResultArray);
```

## Normalize

Normalizes the source image.

```cpp
int dynamsoft::ddn::CDocumentNormalizer::Normalize(const char* sourceFilePath, const char* templateName, const CQuadrilateral* quad, CNormalizedImageResult** result)

int dynamsoft::ddn::CDocumentNormalizer::Normalize( const CImageData* sourceImage, const char* templateName, const CQuadrilateral* quad, CNormalizedImageResult ** result)

```

**Parameters**

`[in] sourceFilePath` A string defining the source file path. It supports BMP, JPEG, PNG, TIFF and PDF files.

`[in] sourceImage` The source image buffer.

`[in] templateName` The template name. A template name is the value of key ImageParameter.Name defined in JSON formatted settings. If no template name is specified, current runtime settings will be used.

`[in] quad` The quadrilateral representing the boundary of the content to be normalized.

`[out] result` The normalized image result. It is allocated by the SDK and should be freed by calling function [`FreeNormalizedImageResult`](document-normalizer-result.md#freenormalizedimageresult).

**Return Value**  
Returns error code (returns 0 if the function operates successfully).

*You can call [`DC_GetErrorString`](document-normalizer-general.md#dc_geterrorstring) to get detailed error message.*

**Code Snippet**

```cpp
int errorCode = 0;
char szErrorMsg[256];
errorCode = CLicenseManager::InitLicense("YOUR-LICENSE-KEY", szErrorMsg, 256);
//...handle the errorCode
CDocumentNormalizer ddn;
CNormalizedImageResult* normalizedResult = NULL;
errorCode = ddn.Normalize("YOUR-SOURCE-FILE-PATH", "", NULL, &normalizedResult);
//generate imageData from somewhere else
//errorCode = ddn.Normalize(imageData, "", NULL, &normalizedResult);
//...do something with the normalizedResult and errorCode
CDocumentNormalizer::FreeNormalizedImageResult(&normalizedResult);
```
