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

**Code Snippet**

```cpp
CDocumentNormalizer ddn;
CDetectedQuadResultArray* detectedQuadResultArray = NULL;
ddn.DetectQuad("YOUR-SOURCE-FILE-PATH", "", &detectedQuadResultArray);
//...do something with the detectedQuadResultArray
if (detectedQuadResultArray != NULL)
    CDocumentNormalizer::FreeDetectedQuadResultArray(&detectedQuadResultArray);
```

## FreeNormalizedImageResult

Releases memory allocated for CNormalizedImageResult.

```cpp
static void dynamsoft::ddn::CDocumentNormalizer::FreeNormalizedImageResult(CNormalizedImageResult** result)
```

**Parameters**

`[in] result` The normalized image result that needs to be released.

**Code Snippet**

```cpp
CDocumentNormalizer ddn;
CNormalizedImageResult* normalizedResult = NULL;
ddn.Normalize("YOUR-SOURCE-FILE-PATH", "", NULL, &normalizedResult);
//...do something with the normalizedResult
if (normalizedResult != NULL)
    CDocumentNormalizer::FreeNormalizedImageResult(&normalizedResult);
```

## FreeString

Releases memory allocated for a string.

```cpp
static void dynamsoft::ddn::CDocumentNormalizer::FreeString(char** content)
```

**Parameters**

`[in] content` The string that needs to be released.

**Code Snippet**

```cpp
CDocumentNormalizer ddn;
char* content = NULL;
ddn.OutputRuntimeSettingsToString("", &content);
//...do something with the content
if (content != NULL)
    CDocumentNormalizer::FreeString(&content);
```

## SaveImageDataToFile

Save the image data to a file.

```cpp
static int dynamsoft::ddn::CDocumentNormalizer::SaveImageDataToFile(const CImageData* imageData, const char* filePath)
```

**Parameters**

`[in] imageData` The image data that needs to be saved.

`[in] filePath` The path of the output image file with the extension specifying the image format. It supports BMP and PNG files.

**Code Snippet**

```cpp
CDocumentNormalizer ddn;
CNormalizedImageResult* normalizedResult = NULL;
ddn.Normalize("YOUR-SOURCE-FILE-PATH", "", NULL, &normalizedResult);
if (normalizedResult != NULL)
{   
    CDocumentNormalizer::SaveImageDataToFile(normalizedResult->GetImageData(), "YOUR-TARGET-FILE-PATH");
    CDocumentNormalizer::FreeNormalizedImageResult(&normalizedResult);
}
```
