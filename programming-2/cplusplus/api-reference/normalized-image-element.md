---
layout: default-layout
title: CNormalizedImageElement Class
description: This page shows CNormalizedImageElement class definition of Dynamsoft Document Normalizer SDK C++ Edition.
keywords: GetImageData, GetReferencedElement, CNormalizedImageElement, api reference
permalink: /programming/cplusplus/api-reference/normalized-image-element.html
---

# CNormalizedImageElement Class

## Definition

*Namespace:* dynamsoft::ddn::intermediate_results

*Assembly:* DynamsoftDocumentNormalizer.dll

```cpp
class CNormalizedImageElement
```

## Methods

| Method | Description |
|--------|-------------|
| [`GetImageData`](#getimagedata) | Gets the ImageData of current object. |
| [`GetReferencedElement`](#getreferencedelement) | Gets the referenced RegionObjectElement object of current object. |

## GetImageData

Gets the ImageData of current object.

```cpp
const CImageData* GetImageData() 
```

**Return Value**

The image data.

**See Also**

* [CImageData]()

### GetReferencedElement

Gets the referenced RegionObjectElement object of current object.

```cpp
const CRegionObjectElement* GetReferencedElement()
```

**Return Value**

Returns the referenced RegionObjectElement object.

**See Also**

* [CRegionObjectElement]()
