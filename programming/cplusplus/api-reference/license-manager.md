---
layout: default-layout
title: CLicenseManager Class
description: This page shows CLicenseManager class definition of Dynamsoft Document Normalizer SDK C++ Edition.
keywords: InitLicense, CLicenseManager, api reference
---

# CLicenseManager Class

```c++
class dynamsoft::core::CLicenseManager 
```

| Method | Description |
|--------|-------------|
| [`InitLicense`](#initlicense) | Sets the license key and activates the SDK.|

## InitLicense

Sets the license key and activates the SDK.

```c++
static int dynamsoft::core::CLicenseManager::InitLicense(const char *license, char errorMsgBuffer[], const int errorMsgBufferLen) 
```

**Parameters**  
`[in] pLicense` The license key.

`[in, out] errorMsgBuffer` The buffer is allocated by caller and the recommended length is 256. The error message will be copied to the buffer.

`[in] errorMsgBufferLen` The length of the allocated buffer.

**Return Value**  
Returns error code (returns 0 if the function operates successfully).
