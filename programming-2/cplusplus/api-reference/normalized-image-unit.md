---
layout: default-layout
title: CNormalizedImageUnit Class
description: This page shows CNormalizedImageUnit class definition of Dynamsoft Document Normalizer SDK C++ Edition.
keywords: GetNormalizedImage, CNormalizedImageUnit, api reference
permalink: /programming/cplusplus/api-reference/normalized-image-unit.html
---

# CNormalizedImageUnit Class

## Definition

*Namespace:* dynamsoft::ddn::intermediate_results

*Assembly:* DynamsoftDocumentNormalizer.dll

```cpp
class CNormalizedImageUnit: CIntermediateResultUnit
```

*Inheritance:* [CIntermediateResultUnit]() -> CNormalizedImageUnit

## Methods

| Method | Description |
|--------|-------------|
| [`GetNormalizedImage`](#getnormalizedimage) | Gets a NormalizedImage object from current object. |

### GetNormalizedImage

Gets a NormalizedImage object from current object.

```cpp
const CNormalizedImageElement* GetNormalizedImage()
```

**Return Value**

Returns the NormalizedImage object.

**See Also**

* [CNormalizedImageElement]({{cpp_api}}normalized-image-element.html)
