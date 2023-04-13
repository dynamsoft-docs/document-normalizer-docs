---
layout: default-layout
title: CNormalizedImageResultItem Class
description: This page shows CNormalizedImageResultItem class definition of Dynamsoft Document Normalizer SDK C++ Edition.
keywords: GetImageData, SaveToFile, CNormalizedImageResultItem, api reference
permalink: /programming/cplusplus/api-reference/normalized-image-result-item.html
---

# CNormalizedImageResultItem Class

## Definition

*Namespace:* dynamsoft::ddn

*Assembly:* DynamsoftDocumentNormalizer.dll

```cpp
class CNormalizedImageResultItem: CCapturedResultItem
```

*Inheritance:* [CCapturedResultItem]() -> CNormalizedImageResultItem

## Methods

| Method | Description |
|--------|-------------|
| [`GetImageData`](#getimagedata) | Gets the ImageData of current object. |
| [`SaveToFile`](#savetofile) | Save the ImageData to a file. |

## GetImageData

Gets the ImageData of current object.

```cpp
const CImageData* GetImageData() 
```

**Return Value**

The image data.

**See Also**

* [CImageData]()

## SaveToFile

Save the ImageData to a file.

```cpp
int SaveToFile(const char* filePath)
```

**Parameters**

`[in] filePath` The path of the output image file with the extension specifying the image format. It supports BMP, PNG, JPEG and PDF file types. If the target file exists, the image will be appended to the last page of the PDF file while the BMP, PNG and JPEG file will be replaced.

**Return Value**

Returns the error code.

**See Also**

* [ErrorCode]()
