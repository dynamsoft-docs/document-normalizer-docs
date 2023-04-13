---
layout: default-layout
title: CCandidateQuadEdgesUnit Class
description: This page shows CCandidateQuadEdgesUnit class definition of Dynamsoft Document Normalizer SDK C++ Edition.
keywords: GetCount, GetCandidateQuadEdge, CCandidateQuadEdgesUnit, api reference
permalink: /programming/cplusplus/api-reference/candidate-quad-edges-unit.html
---

# CCandidateQuadEdgesUnit Class

## Definition

*Namespace:* dynamsoft::ddn::intermediate_results

*Assembly:* DynamsoftDocumentNormalizer.dll

```cpp
class CCandidateQuadEdgesUnit: CIntermediateResultUnit
```

*Inheritance:* [CIntermediateResultUnit]() -> CCandidateQuadEdgesUnit

## Methods

| Method | Description |
|--------|-------------|
| [`GetCount`](#getcount) | Gets the count of CandidateQuadEdge objects in current object.|
| [`GetCandidateQuadEdge`](#getcandidatequadedge) | Gets a CandidateQuadEdge object from current object by specifying a index. |

### GetCount

Gets the count of CandidateQuadEdge objects in current object.

```cpp
int GetCount() 
```

**Return Value**

The count of CandidateQuadEdge objects in current object.

### GetCandidateQuadEdge

Gets a CandidateQuadEdge object from current object by specifying a index.

```cpp
int GetCandidateQuadEdge(int index, CEdge* edge)
```

**Parameters**

`[in] index` The index of the CandidateQuadEdge object.
`[in, out] edge` The CandidateQuadEdge object got by the specific index.

**Return Value**

Returns the error code.

**See Also**

* [CEdge]()
* [ErrorCode]()
