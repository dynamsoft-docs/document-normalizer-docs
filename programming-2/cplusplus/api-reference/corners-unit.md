---
layout: default-layout
title: CCornersUnit Class
description: This page shows CCornersUnit class definition of Dynamsoft Document Normalizer SDK C++ Edition.
keywords: GetCount, GetCorner, CCornersUnit, api reference
permalink: /programming/cplusplus/api-reference/corners-unit.html
---

# CCornersUnit Class

## Definition

*Namespace:* dynamsoft::ddn::intermediate_results

*Assembly:* DynamsoftDocumentNormalizer.dll

```cpp
class CCornersUnit: CIntermediateResultUnit
```

*Inheritance:* [CIntermediateResultUnit]() -> CCornersUnit

## Methods

| Method | Description |
|--------|-------------|
| [`GetCount`](#getcount) | Gets the count of Corner objects in current object.|
| [`GetCorner`](#getcorner) | Gets a Corner object from current object by specifying a index. |

### GetCount

Gets the count of Corner objects in current object.

```cpp
int GetCount() 
```

**Return Value**

The count of Corner objects in current object.

### GetCorner

Gets a Corner object from current object by specifying a index.

```cpp
int GetCorner(int index, CCorner* corner)
```

**Parameters**

`[in] index` The index of the Corner object.
`[in, out] corner` The Corner object got by the specific index.

**Return Value**

Returns the error code.

**See Also**

* [CCorner]()
* [ErrorCode]()
