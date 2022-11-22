---
layout: default-layout
title: Initialize and Destroy Functions - Dynamsoft Document Normalizer SDK C Edition
description: This page shows Initialize and Destroy Functions of Dynamsoft Document Normalizer SDK C Edition.
keywords: DC_InitLicense, DDN_CreateInstance, DDN_DestroyInstance, api reference, c
---

# Initialize and Destroy Functions

| Method               | Description |
|----------------------|-------------|
| [`DC_GetIdleInstancesCount`](#dc_getidleinstancescount) | Gets available instances count when charging by concurrent instances count. |
| [`DC_InitLicense`](#dc_initlicense) | Sets the license key and activates the SDK. |
| [`DDN_CreateInstance`](#ddn_createinstance) | Creates an instance of Dynamsoft Document Normalizer. |
| [`DDN_DestroyInstance`](#ddn_destroyinstance) | Destroys the instance of Dynamsoft Document Normalizer. |

## DC_GetIdleInstancesCount

Gets available instances count when charging by concurrent instances count.

```c
int DC_GetIdleInstancesCount()
```

**Return Value**

Returns available instances count.

- 0: There is no space for new instance  
- -1: The available count needs to be updated from server by calling DC_InitLicense.
- N ( N > 0 ): N more instances can be created.

**Code Snippet**

```c
//...
int count = DC_GetIdleInstancesCount();
if(count > 0)
{
  //create instance and process further
}
if(count < 0)
{
  //call DC_InitLicense
  //create instance and process further
}
if(count = 0)
{
  //waiting for available instances 
}
```

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

**Code Snippet**

```c
void* ddn = NULL;
int errorCode = 0;
char szErrorMsg[256];
errorCode = DC_InitLicense("YOUR-LICENSE-KEY", szErrorMsg, 256);
//...handle the errorCode
ddn = DDN_CreateInstance();
//...do something else
DDN_DestroyInstance(ddn);
```

## DDN_CreateInstance

Creates an instance of Dynamsoft Document Normalizer.

```c
void* DDN_CreateInstance()
```

**Return Value**

Returns an instance of Dynamsoft Document Normalizer. If failed, returns `NULL`.

**Code Snippet**

```c
void* ddn = NULL;
int errorCode = 0;
char szErrorMsg[256];
errorCode = DC_InitLicense("YOUR-LICENSE-KEY", szErrorMsg, 256);
//...handle the errorCode
ddn = DDN_CreateInstance();
//...do something else
DDN_DestroyInstance(ddn);
```

## DDN_DestroyInstance

Destroys an instance of Dynamsoft Document Normalizer.

```c
void DDN_DestroyInstance(void* normalizer)
```

**Parameters**

`[in] normalizer` Handle of the Dynamsoft Document Normalizer instance.

**Code Snippet**

```c
void* ddn = NULL;
int errorCode = 0;
char szErrorMsg[256];
errorCode = DC_InitLicense("YOUR-LICENSE-KEY", szErrorMsg, 256);
//...handle the errorCode
ddn = DDN_CreateInstance();
//...do something else
DDN_DestroyInstance(ddn);
```
