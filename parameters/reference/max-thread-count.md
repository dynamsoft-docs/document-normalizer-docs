---
title: Dynamsoft Content Normalizer Parameter Reference - MaxThreadCount
keywords: maxthreadcount, parameters, reference, dcn, documentation
description: Dynamsoft Content Normalizer Parameter Reference - MaxThreadCount
needGenerateH3Content: true
---


# MaxThreadCount
Sets the maximum number of threads the algorithm will use to normalize content.

## Setting Methods
### As Json Parameter

| Parent Json Object | Json Parameter Name | Value Type | 
| ------------------ | ------------------- | ---------- |
| ContentNormalizerParameter | MaxThreadCount | *int* |

**Value Range**  
    [1, 4]

**Default Value**  
    4

**Example**  
```json
{
    "MaxThreadCount": 4,
}
```

### As Struct Member

| Struct | Struct Member Name | Value Type | 
| ------ | ------------------ | ---------- |
| DCN_RuntimeSettings | maxThreadCout | *int* |

**Value Range**  
    [1, 4]

**Default Value**  
    4

**Code Snippet**  
```cpp
// This is a c++ sample code.
ContentNormalizer::InitLicense("t0260NwAAAHV***************");
ContentNormalizer* normalizer = new ContentNormalizer();
DCN_RuntimeSettings settings;
int errorCode = normalizer->GetRuntimeSettings(&settings);
settings->maxThreadCout = 1;
char errorMessage[256];
errorCode = normalizer->UpdateRuntimeSettings(&settings, errorMessage, 256);
delete normalizer;
```

