---
layout: default-layout
title: CDetectedQuadElement Class
description: This page shows CDetectedQuadElement class definition of Dynamsoft Document Normalizer SDK C++ Edition.
keywords: GetConfidenceAsDocumentBoundary, CDetectedQuadElement, api reference
permalink: /programming/cplusplus/api-reference/detected-quad-element.html
---

# CDetectedQuadElement Class

## Definition

*Namespace:* dynamsoft::ddn::intermediate_results

*Assembly:* DynamsoftDocumentNormalizer.dll

```cpp
class CDetectedQuadElement: CRegionObjectElement
```

*Inheritance:* [CRegionObjectElement]() -> CDetectedQuadElement

## Methods

| Method | Description |
|--------|-------------|
| [`GetConfidenceAsDocumentBoundary`](#getconfidenceasdocumentboundary) | Gets the confidence as document boundary of current object. |

## GetConfidenceAsDocumentBoundary

Gets the confidence as document boundary of current object.

```cpp
int GetConfidenceAsDocumentBoundary() 
```

**Return Value**

The confidence as document boundary of current object.
