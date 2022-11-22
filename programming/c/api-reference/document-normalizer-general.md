---
layout: default-layout
title: General Methods - Dynamsoft Document Normalizer SDK C Edition
description: This page shows General Methods of Dynamsoft Document Normalizer SDK C Edition.
keywords: DC_GetErrorString, DDN_GetVersion, CDocumentNormalizer, api reference, c
---

# General Methods

| Method               | Description |
|----------------------|-------------|
| [`DC_GetErrorString`](#dc_geterrorstring) | Returns the corresponding error message of the input error code. |
| [`DC_GetQuadrilateralArea`](#dc_getquadrilateralarea) | Returns the area of the quadrilateral. |
| [`DC_IsPointInQuadrilateral`](#dc_ispointinquadrilateral) | Returns whether the point is in the quadrilateral. |
| [`DDN_GetVersion`](#ddn_getversion) | Returns the version info string of the Dynamsoft Document Normalizer SDK. |

## DC_GetQuadrilateralArea

Returns the area of the quadrilateral.

```c
int DC_GetQuadrilateralArea(const Quadrilateral* quad)
```

**Parameters**

`[in] quad` The quadrilateral to get area.

**Return Value**

The area of the quadrilateral.

**See Also**

[`Quadrilateral`](quadrilateral.md)

## DC_IsPointInQuadrilateral

Returns whether the point is in the quadrilateral.

```c
int DC_IsPointInQuadrilateral(const DM_Point* point, const Quadrilateral* quad)
```

**Parameters**

`[in] point` The point.

`[in] quad` The quadrilateral.

**Return Value**

- 0: the point is not in the quadrilateral.
- 1: the point is in the quadrilateral.

**See Also**

[`DM_Point`](point.md)

[`Quadrilateral`](quadrilateral.md)

## DC_GetErrorString

Returns the corresponding error message of the input error code.

```c
const char* DC_GetErrorString(const int errorCode)
```

**Parameters**

`[in] errorCode` Error code.

**Return Value**

The error message.

**Code Snippet**

```c
int errorCode = 0;
void* ddn = NULL;
NormalizedImageResult* normalizedResult = NULL;
ddn = DDN_CreateInstance();
errorCode = DDN_NormalizeFile(ddn, "YOUR-SOURCE-FILE-PATH", "", NULL, &normalizedResult);
if (errorCode != DM_OK)
    const char* errorString = DC_GetErrorString(errorCode);
    //...do something with the errorString
```

## DDN_GetVersion

Returns the version info string of the SDK.

```c
const char* DDN_GetVersion()
```

**Return Value**

The version information string.

**Code Snippet**

```c
const char* versionInfo = DDN_GetVersion();
```
