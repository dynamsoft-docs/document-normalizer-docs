---
layout: default-layout
title: CDetectedQuadResultArray Class
description: This page shows CDetectedQuadResultArray class definition of Dynamsoft Document Normalizer SDK C++ Edition.
keywords: GetCount, GetDetectedQuadResult, CDetectedQuadResultArray, api reference
---

# CDetectedQuadResultArray Class

An array storing detected quad results.

```cpp
class dynamsoft::ddn::CDetectedQuadResultArray
```

| Method | Description |
|--------|-------------|
| [`GetCount`](#getcount) | Gets the count of detected quad results in the array.|
| [`GetDetectedQuadResult`](#getdetectedquadresult) | Gets a detected quad result by specifying the index in the array.|

## GetCount

Gets the count of detected quad results in the array.

```cpp
const CQuadrilateral* GetCount() 
```

**Return Value**

The count of detected quad results in the array.

## GetDetectedQuadResult

Gets a detected quad result by specifying the index in the array.

```cpp
int GetDetectedQuadResult(int index, CDetectedQuadResult** result) 
```

**Parameters**

`[in] index` The index of the detected quad result to get in the array.

`[in] result` The detected quad result got from the array.

**Return Value**  
Returns error code (returns 0 if the function operates successfully).

*You can call [`DC_GetErrorString`](document-normalizer-general.md#dc_geterrorstring) to get detailed error message.*
