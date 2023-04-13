---
layout: default-layout
title: CDetectedQuadsResult Class
description: This page shows CDetectedQuadsResult class definition of Dynamsoft Document Normalizer SDK C++ Edition.
keywords: GetCount, GetErrorCode, GetErrorString, GetItem, GetSourceImageHashId, GetSourceImageTag, CDetectedQuadsResult, api reference
permalink: /programming/cplusplus/api-reference/detected-quads-result.html
---

# CDetectedQuadsResult Class

## Definition

*Namespace:* dynamsoft::ddn

*Assembly:* DynamsoftDocumentNormalizer.dll

```cpp
class CDetectedQuadsResult
```

## Methods

| Method | Description |
|--------|-------------|
| [`GetCount`](#getcount) | Gets the number of detected quadrilaterals. |
| [`GetErrorCode`](#geterrorcode) | Gets the error code of the detection operation. |
| [`GetErrorString`](#geterrorstring) | Gets the error message of the detection operation. |
| [`GetItem`](#getitem) | Gets the detected quadrilateral item at a specified index. |
| [`GetSourceImageHashId`](#getsourceimagehashid) | Gets the hash ID of the source image. |
| [`GetSourceImageTag`](#getsourceimagetag) | Gets the tag of the source image. |

### GetCount

Gets the number of detected quadrilaterals.

```cpp
int GetCount()
```

**Return value**

Returns the number of detected quadrilaterals.

### GetErrorCode

Gets the error code of the detection operation.

```cpp
int GetErrorCode()
```

**Return value**

Returns the error code.

**See Also**

* [ErrorCode]()

### GetErrorString

Gets the error message of the detection operation.

```cpp
const char* GetErrorString()
```

**Return value**

Returns a pointer to a null-terminated string that represents the error message.

### GetItem

Gets the detected quadrilateral item at a specified index.

```cpp
const CDetectedQuadResultItem* GetItem(int index)
```

**Parameters**

`[in] index` The index of the detected quadrilateral to retrieve.

**Return value**

Returns a pointer to a CDetectedQuadResultItem object that represents the detected quadrilateral at the specified index.

**See Also**

* [CDetectedQuadResultItem]()

### GetSourceImageHashId

Gets the hash ID of the source image.

```cpp
const char* GetSourceImageHashId()
```

**Return value**

Returns a pointer to a null-terminated string that represents the hash ID of the source image.

### GetSourceImageTag

Gets the tag of the source image.

```cpp
const CImageTag* GetSourceImageTag()
```

**Return value**

Returns a pointer to a CImageTag object that represents the tag of the source image.

**See Also**

* [CImageTag]()
