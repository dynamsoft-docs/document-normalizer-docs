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
| [`InitLicense`](#initlicense) | Sets the license key and activates the SDK.|

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
