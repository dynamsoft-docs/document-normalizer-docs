---
layout: default-layout
title: CDetectedQuadResultItem Class
description: This page shows CDetectedQuadResultItem class definition of Dynamsoft Document Normalizer SDK C++ Edition.
keywords: GetLocation, GetConfidenceAsDocumentBoundary, GetRotatationTransformMatrix, CDetectedQuadResultItem, api reference
permalink: /programming/cplusplus/api-reference/detected-quad-result-item.html
---

# CDetectedQuadResultItem Class

## Definition

*Namespace:* dynamsoft::ddn

*Assembly:* DynamsoftDocumentNormalizer.dll

```cpp
class CDetectedQuadResultItem: CCapturedResultItem
```

*Inheritance:* [CCapturedResultItem]() -> CDetectedQuadResultItem

## Methods

| Method | Description |
|--------|-------------|
| [`GetLocation`](#getlocation) | Gets the location of current object. |
| [`GetConfidenceAsDocumentBoundary`](#getconfidenceasdocumentboundary) | Gets the confidence of current object as a document boundary. |
| [`GetRotatationTransformMatrix`](#getrotatationtransformmatrix) | Gets the transformation matrix to transform the location coordinates to image’s natural orientation. |

### GetLocation

Gets the location of current object.

```cpp
const CQuadrilateral GetLocation() 
```

**Return Value**

The location of current object.

**See Also**

* [CQuadrilateral]()

### GetConfidenceAsDocumentBoundary

Gets the confidence of current object as a document boundary.

```cpp
int GetConfidenceAsDocumentBoundary() 
```

**Return Value**

The confidence as document boundary of the detected quad result.

### GetRotatationTransformMatrix

Gets the transformation matrix to transform the location coordinates to image’s natural orientation.

```cpp
void GetRotatationTransformMatrix(double matrix[9]) 
```

**Parameters**

`[in] matrix` The transformation matrix.
