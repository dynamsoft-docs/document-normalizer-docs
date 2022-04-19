---
layout: default-layout
title: CDocumentNormalizer - General Methods
description: This page shows General Methods of class CDocumentNormalizer of Dynamsoft Document Normalizer SDK C++ Edition.
keywords: FreeDetectedQuadResultArray, FreeNormalizedImageResult, FreeString, SaveImageDataToFile, CDocumentNormalizer, api reference, c++
---

# Result Methods

| Method               | Description |
|----------------------|-------------|
| [`FreeDetectedQuadResultArray`](#freedetectedquadresultarray) | Releases memory allocated for CDetectedQuadResultArray. |
| [`FreeNormalizedImageResult`](#freenormalizedimageresult) | Releases memory allocated for CNormalizedImageResult. |
| [`FreeString`](#freestring) | Releases memory allocated for a string. |
| [`SaveImageDataToFile`](#saveimagedatatofile) | Save the image data to a file. |

## FreeDetectedQuadResultArray

Releases memory allocated for CDetectedQuadResultArray.

```cpp
static void dynamsoft::ddn::CDocumentNormalizer::FreeDetectedQuadResultArray(CDetectedQuadResultArray** results)
```

**Parameters**  
`[in] results` An array of all detected quad results that needs to be released.

## FreeNormalizedImageResult

Releases memory allocated for CNormalizedImageResult.

```cpp
static void dynamsoft::ddn::CDocumentNormalizer::FreeNormalizedImageResult(CNormalizedImageResult** result)
```

**Parameters**  
`[in] result` The normalized image result that needs to be released.

## FreeString

Releases memory allocated for a string.

```cpp
static void dynamsoft::ddn::CDocumentNormalizer::FreeString(char** content)
```

**Parameters**  
`[in] content` The string that needs to be released.

## SaveImageDataToFile

Save the image data to a file.

```cpp
static int dynamsoft::ddn::CDocumentNormalizer::SaveImageDataToFile(const CImageData* imageData, const char* filePath)
```

**Parameters**  
`[in] imageData` The image data that needs to be saved.

`[in] filePath` The path of the output image with the extension specified image format.
