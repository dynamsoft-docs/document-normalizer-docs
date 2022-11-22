---
layout: default-layout
title: Result Methods - Dynamsoft Document Normalizer SDK C Edition
description: This page shows Result Methods of Dynamsoft Document Normalizer SDK C Edition.
keywords: DDN_FreeDetectedQuadResultArray, DDN_FreeNormalizedImageResult, DDN_FreeString, NormalizedImageResult_SaveToFile, , api reference, c
---

# Result Methods

| Method               | Description |
|----------------------|-------------|
| [`DDN_FreeDetectedQuadResultArray`](#ddn_freedetectedquadresultarray) | Releases memory allocated for DetectedQuadResultArray. |
| [`DDN_FreeNormalizedImageResult`](#ddn_freenormalizedimageresult) | Releases memory allocated for NormalizedImageResult. |
| [`DDN_FreeString`](#ddn_freestring) | Releases memory allocated for a string. |
| [`NormalizedImageResult_SaveToFile`](#normalizedimageresult_savetofile) | Save the normalized image result to a file. |

## DDN_FreeDetectedQuadResultArray

Releases memory allocated for DetectedQuadResultArray.

```c
void DDN_FreeDetectedQuadResultArray(DetectedQuadResultArray** results)
```

**Parameters**

`[in] results` An array of all detected quad results that needs to be released.

**Code Snippet**

```c
DetectedQuadResultArray* detectedQuadResultArray = NULL;
void* ddn = DDN_CreateInstance();
DDN_DetectQuadFromFile(ddn, "YOUR-SOURCE-FILE-PATH", "", &detectedQuadResultArray);
//...do something with the detectedQuadResultArray
if (detectedQuadResultArray != NULL)
    DDN_FreeDetectedQuadResultArray(&detectedQuadResultArray);
DDN_DestroyInstance(ddn);
```

## DDN_FreeNormalizedImageResult

Releases memory allocated for NormalizedImageResult.

```c
void DDN_FreeNormalizedImageResult(NormalizedImageResult** result)
```

**Parameters**

`[in] result` The normalized image result that needs to be released.

**Code Snippet**

```c
NormalizedImageResult* normalizedResult = NULL;
void* ddn = DDN_CreateInstance();
DDN_NormalizeFile(ddn, "YOUR-SOURCE-FILE-PATH", "", NULL, &normalizedResult);
//...do something with the normalizedResult
if (normalizedResult != NULL)
    DDN_FreeNormalizedImageResult(&normalizedResult);
DDN_DestroyInstance(ddn);
```

## DDN_FreeString

Releases memory allocated for a string.

```c
void DDN_FreeString(char** content)
```

**Parameters**

`[in] content` The string that needs to be released.

**Code Snippet**

```c
void* ddn = DDN_CreateInstance();
char* content = NULL;
DDN_OutputRuntimeSettingsToString(ddn, "", &content);
//...do something with the content
if (content != NULL)
    DDN_FreeString(&content);
DDN_DestroyInstance(ddn);
```

## NormalizedImageResult_SaveToFile

Save the normalized image result to a file.

```c
int NormalizedImageResult_SaveToFile(const NormalizedImageResult* normalizedImageResult, const char* filePath)
```

**Parameters**

`[in] normalizedImageResult` The [NormalizedImageResult](normalized-image-result.md) that needs to be saved.

`[in] filePath` The path of the output image with the extension specifying the image format. It supports BMP, PNG, JPEG and PDF file types. If the target file exists, the image will be appended to the last page of the PDF file while the BMP, PNG and JPEG file will be replaced.

**Return Value**

Returns error code (returns 0 if the function operates successfully).

*You can call [`DC_GetErrorString`](document-normalizer-general.md#dc_geterrorstring) to get detailed error message.*

**Code Snippet**

```c
NormalizedImageResult* normalizedResult = NULL;
void* ddn = DDN_CreateInstance();
DDN_NormalizeFile(ddn, "YOUR-SOURCE-FILE-PATH", "", NULL, &normalizedResult);
if (normalizedResult != NULL)
{
    NormalizedImageResult_SaveToFile(normalizedResult, "YOUR-TARGET-FILE-PATH");
    DDN_FreeNormalizedImageResult(&normalizedResult);
}
DDN_DestroyInstance(ddn);
```
