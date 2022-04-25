---
layout: default-layout
title: CDocumentNormalizer - General Methods
description: This page shows General Methods of class CDocumentNormalizer of Dynamsoft Document Normalizer SDK C++ Edition.
keywords: DDN_FreeDetectedQuadResultArray, DDN_FreeNormalizedImageResult, DDN_FreeString, DDN_SaveImageDataToFile, CDocumentNormalizer, api reference, c++
---

# Result Methods

| Method               | Description |
|----------------------|-------------|
| [`DDN_FreeDetectedQuadResultArray`](#ddn_freedetectedquadresultarray) | Releases memory allocated for DetectedQuadResultArray. |
| [`DDN_FreeNormalizedImageResult`](#ddn_freenormalizedimageresult) | Releases memory allocated for NormalizedImageResult. |
| [`DDN_FreeString`](#ddn_freestring) | Releases memory allocated for a string. |
| [`DDN_SaveImageDataToFile`](#ddn_saveimagedatatofile) | Save the image data to a file. |

## DDN_FreeDetectedQuadResultArray

Releases memory allocated for DetectedQuadResultArray.

```c
void DDN_FreeDetectedQuadResultArray(DetectedQuadResultArray** results)
```

**Parameters**  
`[in] results` An array of all detected quad results that needs to be released.

## DDN_FreeNormalizedImageResult

Releases memory allocated for NormalizedImageResult.

```c
void DDN_FreeNormalizedImageResult(NormalizedImageResult** result)
```

**Parameters**  
`[in] result` The normalized image result that needs to be released.

## DDN_FreeString

Releases memory allocated for a string.

```c
void DDN_FreeString(char** content)
```

**Parameters**  
`[in] content` The string that needs to be released.

## DDN_SaveImageDataToFile

Save the image data to a file.

```c
int DDN_SaveImageDataToFile(const ImageData* imageData, const char* filePath)
```

**Parameters**  
`[in] imageData` The image data that needs to be saved.

`[in] filePath` The path of the output image with the extension specified image format.
