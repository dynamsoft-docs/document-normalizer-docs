---
layout: default-layout
title: General Methods
description: This page shows General Methods of Dynamsoft Document Normalizer SDK C Edition.
keywords: DDN_GetErrorString, DDN_GetVersion, CDocumentNormalizer, api reference, c
---

# General Methods

| Method               | Description |
|----------------------|-------------|
| [`DDN_GetErrorString`](#ddn_geterrorstring) | Returns the corresponding error message of the input error code. |
| [`DDN_GetVersion`](#ddn_getversion) | Returns the version info string of the Dynamsoft Document Normalizer SDK. |

## DDN_GetErrorString

Returns the corresponding error message of the input error code.

```c
const char* DDN_GetErrorString(const int errorCode)
```

**Parameters**  
`[in] errorCode` Error code.

**Return Value**  
The error message.

## DDN_GetVersion

Returns the version info string of the SDK.

```c
const char* DDN_GetVersion()
```

**Return Value**  
The version information string.
