---
layout: default-layout
title: CDocumentNormalizer - General Methods
description: This page shows General Methods of class CDocumentNormalizer of Dynamsoft Document Normalizer SDK C++ Edition.
keywords: GetErrorString, GetVersion, CDocumentNormalizer, api reference, c++
---

# General Methods

| Method               | Description |
|----------------------|-------------|
| [`GetErrorString`](#geterrorstring) | Returns the corresponding error message of the input error code. |
| [`GetVersion`](#getversion) | Returns the version info string of the SDK. |

## GetErrorString

Returns the corresponding error message of the input error code.

```cpp
static const char* dynamsoft::ddn::CDocumentNormalizer::GetErrorString(const int errorCode)
```

**Parameters**  
`[in] errorCode` Error code.

**Return Value**  
The error message.

## GetVersion

Returns the version info string of the SDK.

```cpp
static const char* dynamsoft::ddn::CDocumentNormalizer::GetVersion()
```

**Return Value**  
The version information string.
