---
layout: default-layout
title: Initialize and Destroy Functions
description: This page shows Initialize and Destroy Functions of Dynamsoft Document Normalizer SDK C Edition.
keywords: DC_InitLicense, DDN_CreateInstance, DDN_DestroyInstance, api reference, c
---

# Initialize and Destroy Functions

| Method               | Description |
|----------------------|-------------|
| [`DC_InitLicense`](#dc_initlicense) | Sets the license key and activates the SDK. |
| [`DDN_CreateInstance`](#ddn_createinstance) | Creates an instance of Dynamsoft Document Normalizer. |
| [`DDN_DestroyInstance`](#ddn_destroyinstance) | Destroys the instance of Dynamsoft Document Normalizer. |

## DC_InitLicense

Sets the license key and activates the SDK.

```c
int DC_InitLicense(const char *license, char errorMsgBuffer[], const int errorMsgBufferLen) 
```

**Parameters**  
`[in] pLicense` The license key.

`[in, out] errorMsgBuffer` The buffer is allocated by caller and the recommended length is 256. The error message will be copied to the buffer.

`[in] errorMsgBufferLen` The length of the allocated buffer.

**Return Value**  
Returns error code (returns 0 if the function operates successfully).

## DDN_CreateInstance

Creates an instance of Dynamsoft Document Normalizer.

```c
void* DDN_CreateInstance()
```

**Return Value**

Returns an instance of Dynamsoft Document Normalizer. If failed, returns `NULL`.

## DDN_DestroyInstance

Destroys an instance of Dynamsoft Document Normalizer.

```c
void DDN_DestroyInstance(void* normalizer)
```

**Parameters**

`[in] normalizer` Handle of the Dynamsoft Document Normalizer instance.