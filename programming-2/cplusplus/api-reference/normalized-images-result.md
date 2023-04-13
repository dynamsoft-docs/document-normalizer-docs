---
layout: default-layout
title: CNormalizedImagesResult Class
description: This page shows CNormalizedImagesResult class definition of Dynamsoft Document Normalizer SDK C++ Edition.
keywords: GetCount, GetErrorCode, GetErrorString, GetItem, GetSourceImageHashId, GetSourceImageTag, CNormalizedImagesResult, api reference
permalink: /programming/cplusplus/api-reference/normalized-images-result.html
---

# CNormalizedImagesResult

The CNormalizedImagesResult class represents the result of a normalization process on a set of images. It provides information about the source image, the number of items in the result, and access to individual normalized image result items.

## Definition

*Namespace:* dynamsoft::ddn

*Assembly:* DynamsoftDocumentNormalizer.dll

```cpp
class CNormalizedImagesResult
```

## Methods

| Method               | Description |
|----------------------|-------------|
| [`GetCount`](#getcount) | Gets the number of normalized images in the result. |
| [`GetErrorCode`](#geterrorcode) | Gets the error code of the operation. |
| [`GetErrorString`](#geterrorstring) | Gets the error message of the operation. |
| [`GetItem`](#getitem) | Gets a specific normalized image from the result. |
| [`GetSourceImageHashId`](#getsourceimagehashid) | Gets the hash ID of the source image that was normalized. |
| [`GetSourceImageTag`](#getsourceimagetag) | Gets the tag of the source image that was normalized. |

### GetCount

Gets the number of normalized images in the result.

```cpp
int GetCount()
```

**Return value**

Returns the number of normalized images in the result.

### GetErrorCode

Gets the error code of the operation.

```cpp
int GetErrorCode()
```

**Return value**

Returns the error code of the operation. A non-zero value indicates an error occurred.

**See Also**

* [ErrorCode]()

### GetErrorString

Gets the error message of the operation.

```cpp
const char* GetErrorString()
```

**Return value**

Returns the error message of the operation.

### GetItem

Gets a specific normalized image from the result.

```cpp
const CNormalizedImageResultItem* GetItem(int index)
```

**Parameters**

`[in] index` The index of the normalized image to get.

**Return value**

Returns a pointer to the normalized image at the specified index. If the index is out of range, returns nullptr.

**See Also**

* [CNormalizedImageResultItem]()

### GetSourceImageHashId

Gets the hash ID of the source image that was normalized.

```cpp
const char* GetSourceImageHashId()
```

**Return value**

Returns the hash ID of the source image that was normalized.

### GetSourceImageTag

Gets the tag of the source image that was normalized.

```cpp
const CImageTag* GetSourceImageTag()
```

**Return value**

Returns a pointer to the tag of the source image that was normalized.

**See Also**

* [CImageTag]()
