---
layout: default-layout
title: CLicenseManager Class
description: This page shows CLicenseManager class definition of Dynamsoft Document Normalizer SDK C++ Edition.
keywords: InitLicense, CLicenseManager, api reference
---

# CLicenseManager Class

```cpp
class dynamsoft::core::CLicenseManager 
```

| Method | Description |
|--------|-------------|
| [`GetIdleInstancesCount`](#getidleinstancescount) | Gets available instances count when charging by concurrent instances count. |
| [`InitLicense`](#initlicense) | Sets the license key and activates the SDK.|

## GetIdleInstancesCount

Gets available instances count when charging by concurrent instances count.

```cpp
static int dynamsoft::core::CLicenseManager::GetIdleInstancesCount()
```

**Return Value**

Returns available instances count.

- 0: There is no space for new instance  
- -1: The available count needs to be updated from server by calling InitLicense.
- N ( N > 0 ): N more instances can be created.

**Code Snippet**

```cpp
//...
int count = dynamsoft::core::CLicenseManager::GetIdleInstancesCount();
if(count > 0)
{
  //create instance and process further
}
if(count < 0)
{
  //call InitLicense
  //create instance and process further
}
if(count = 0)
{
  //waiting for available instances 
}
```

## InitLicense

Sets the license key and activates the SDK.

```cpp
static int dynamsoft::core::CLicenseManager::InitLicense(const char *license, char errorMsgBuffer[], const int errorMsgBufferLen) 
```

**Parameters**

`[in] pLicense` The license key.

`[in, out] errorMsgBuffer` The buffer is allocated by caller and the recommended length is 256. The error message will be copied to the buffer.

`[in] errorMsgBufferLen` The length of the allocated buffer.

**Return Value**

Returns error code (returns 0 if the function operates successfully).

**Code Snippet**

```cpp
int errorCode = 0;
char szErrorMsg[256];
errorCode = CLicenseManager::InitLicense("YOUR-LICENSE-KEY", szErrorMsg, 256);
if (errorCode != DM_OK)
    cout << szErrorMsg << endl;
```
