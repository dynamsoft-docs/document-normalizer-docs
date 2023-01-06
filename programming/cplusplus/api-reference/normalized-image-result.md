---
layout: default-layout
title: CNormalizedImageResult Class
description: This page shows CNormalizedImageResult class definition of Dynamsoft Document Normalizer SDK C++ Edition.
keywords: GetImageData, CNormalizedImageResult, api reference
---

# CNormalizedImageResult Class

Stores the normalized image result.

```cpp
class dynamsoft::ddn::CNormalizedImageResult
```

| Method | Description |
|--------|-------------|
| [`GetImageData`](#getimagedata) | Gets the image data of the NormalizedImageResult.|
| [`SaveToFile`](#savetofile) | Save the normalized image result to a file. |

## GetImageData

Gets the image data of the NormalizedImageResult.

```cpp
const CImageData* GetImageData() 
```

**Return Value**

The image data.

## SaveToFile

Save the image data to a file.

```cpp
int dynamsoft::ddn::CDocumentNormalizer::SaveToFile(const char* filePath)
```

**Parameters**

`[in] filePath` The path of the output image file with the extension specifying the image format. It supports BMP, PNG, JPEG and PDF file types. If the target file exists, the image will be appended to the last page of the PDF file while the BMP, PNG and JPEG file will be replaced.

**Return Value**

Returns error code (returns 0 if the function operates successfully).

*You can call [`DC_GetErrorString`](document-normalizer-general.md#dc_geterrorstring) to get detailed error message.*

**Code Snippet**

```cpp
CDocumentNormalizer ddn;
CNormalizedImageResult* normalizedResult = NULL;
ddn.Normalize("YOUR-SOURCE-FILE-PATH", "", NULL, &normalizedResult);
if (normalizedResult != NULL)
{   
    normalizedResult->SaveToFile("YOUR-TARGET-FILE-PATH");
    CDocumentNormalizer::FreeNormalizedImageResult(&normalizedResult);
}
```
