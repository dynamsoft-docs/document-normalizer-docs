---
layout: default-layout
title: CDocumentNormalizer - General Methods
description: This page shows General Methods of class CDocumentNormalizer of Dynamsoft Document Normalizer SDK C++ Edition.
keywords: DC_GetErrorString, GetVersion, CDocumentNormalizer, api reference, c++
---

# General Methods

| Method               | Description |
|----------------------|-------------|
| [`DC_GetErrorString`](#dc_geterrorstring) | Returns the corresponding error message of the input error code. |
| [`GetVersion`](#getversion) | Returns the version info string of the SDK. |

## DC_GetErrorString

Returns the corresponding error message of the input error code.

```cpp
const char* DC_GetErrorString(const int errorCode)
```

**Parameters**

`[in] errorCode` Error code.

**Return Value**

The error message.

**Code Snippet**

```cpp
int errorCode = 0;
CDocumentNormalizer ddn;
CNormalizedImageResult* normalizedResult = NULL;
errorCode = ddn.Normalize("YOUR-SOURCE-FILE-PATH", "", NULL, &normalizedResult);
if (errorCode != DM_OK)
    const char* errorString = DC_GetErrorString(errorCode);
    //...do something with the errorString
```

## GetVersion

Returns the version info string of the SDK.

```cpp
static const char* dynamsoft::ddn::CDocumentNormalizer::GetVersion()
```

**Return Value**

The version information string.

**Code Snippet**

```cpp
const char* versionInfo = CDocumentNormalizer::GetVersion();
```
