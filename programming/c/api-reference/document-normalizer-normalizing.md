---
layout: default-layout
title: Detecting and Normalizing Methods - Dynamsoft Document Normalizer SDK C Edition
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

`[out] result` An array of all detected quad results. It is allocated by the SDK and should be freed by calling function [`DDN_FreeDetectedQuadResultArray`](document-normalizer-result.md#ddn_freedetectedquadresultarray).

**Return Value**

Returns error code (returns 0 if the function operates successfully).

*You can call [`DC_GetErrorString`](document-normalizer-general.md#dc_geterrorstring) to get detailed error message.*

**Code Snippet**

```c
void* ddn = NULL;
int errorCode = 0;
char szErrorMsg[256];
DetectedQuadResultArray* detectedQuadResultArray = NULL;
errorCode = DC_InitLicense("YOUR-LICENSE-KEY", szErrorMsg, 256);
//...handle the errorCode
ddn = DDN_CreateInstance();
//...generate imageData from somewhere else
errorCode = DDN_DetectQuadFromBuffer(ddn, imageData, "", &detectedQuadResultArray);
//...do something with the detectedQuadResultArray
DDN_FreeDetectedQuadResultArray(&detectedQuadResultArray);
DDN_DestroyInstance(ddn);
```

## DDN_DetectQuadFromFile

Detects quad from source image specified by file path.

```c
int DDN_DetectQuadFromFile(void* normalizer, const char* sourceFilePath, const char* templateName, DetectedQuadResultArray** result)
```

**Parameters**

`[in] normalizer` Handle of the Dynamsoft Document Normalizer instance.

`[in] sourceFilePath` A string defining the source file path. It supports BMP, JPEG, PNG, TIFF and PDF files.

`[in] templateName` The template name. A template name is the value of key ImageParameter.Name defined in JSON formatted settings. If no template name is specified, current runtime settings will be used.

`[out] result` An array of all detected quad results. It is allocated by the SDK and should be freed by calling function [`DDN_FreeDetectedQuadResultArray`](document-normalizer-result.md#ddn_freedetectedquadresultarray).

**Return Value**

Returns error code (returns 0 if the function operates successfully).

*You can call [`DC_GetErrorString`](document-normalizer-general.md#dc_geterrorstring) to get detailed error message.*

**Code Snippet**

```c
void* ddn = NULL;
int errorCode = 0;
char szErrorMsg[256];
DetectedQuadResultArray* detectedQuadResultArray = NULL;
errorCode = DC_InitLicense("YOUR-LICENSE-KEY", szErrorMsg, 256);
//...handle the errorCode
ddn = DDN_CreateInstance();
errorCode = DDN_DetectQuadFromFile(ddn, "YOUR-SOURCE-FILE-PATH", "", &detectedQuadResultArray);
//...do something with the detectedQuadResultArray
DDN_FreeDetectedQuadResultArray(&detectedQuadResultArray);
DDN_DestroyInstance(ddn);
```

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

`[out] result` The normalized image result. It is allocated by the SDK and should be freed by calling function [`DDN_FreeNormalizedImageResult`](document-normalizer-result.md#ddn_freenormalizedimageresult).

**Return Value**

Returns error code (returns 0 if the function operates successfully).

*You can call [`DC_GetErrorString`](document-normalizer-general.md#dc_geterrorstring) to get detailed error message.*

**Code Snippet**

```c
void* ddn = NULL;
int errorCode = 0;
char szErrorMsg[256];
NormalizedImageResult* normalizedResult = NULL;
errorCode = DC_InitLicense("YOUR-LICENSE-KEY", szErrorMsg, 256);
//...handle the errorCode
ddn = DDN_CreateInstance();
//...generate imageData from somewhere else
errorCode = DDN_NormalizeBuffer(ddn, imageData, "", NULL, &normalizedResult);
//...do something with the normalizedResult
DDN_FreeNormalizedImageResult(&normalizedResult);
DDN_DestroyInstance(ddn);
```

## DDN_NormalizeFile

Normalizes the source image specified by file path.

```c
int DDN_NormalizeFile(void* normalizer, const char* sourceFilePath, const char* templateName, const Quadrilateral* quad, NormalizedImageResult** result)
```

**Parameters**

`[in] normalizer` Handle of the Dynamsoft Document Normalizer instance.

`[in] sourceFilePath` A string defining the source file path. It supports BMP, JPEG, PNG, TIFF and PDF files.

`[in] templateName` The template name. A template name is the value of key ImageParameter.Name defined in JSON formatted settings. If no template name is specified, current runtime settings will be used.

`[in] quad` The quadrilateral representing the boundary of the content to be normalized.

`[out] result` The normalized image result. It is allocated by the SDK and should be freed by calling function [`DDN_FreeNormalizedImageResult`](document-normalizer-result.md#ddn_freenormalizedimageresult).

**Return Value**

Returns error code (returns 0 if the function operates successfully).

*You can call [`DC_GetErrorString`](document-normalizer-general.md#dc_geterrorstring) to get detailed error message.*

**Code Snippet**

```c
void* ddn = NULL;
int errorCode = 0;
char szErrorMsg[256];
NormalizedImageResult* normalizedResult = NULL;
errorCode = DC_InitLicense("YOUR-LICENSE-KEY", szErrorMsg, 256);
//...handle the errorCode
ddn = DDN_CreateInstance();
errorCode = DDN_NormalizeFile(ddn, "YOUR-SOURCE-FILE-PATH", "", NULL, &normalizedResult);
//...do something with the normalizedResult and errorCode
DDN_FreeNormalizedImageResult(&normalizedResult);
DDN_DestroyInstance(ddn);
```
