---
title: Dynamsoft Document Normalizer Parameter Reference - MaxThreadCount
keywords: maxthreadcount, parameters, reference, ddn, documentation
description: Dynamsoft Document Normalizer Parameter Reference - MaxThreadCount
needGenerateH3Content: true
---


# MaxThreadCount
Sets the maximum number of threads the algorithm will use to normalize content.

## Setting Methods
### As Json Parameter

| Parent Json Object | Json Parameter Name | Value Type | 
| ------------------ | ------------------- | ---------- |
| DocumentNormalizerParameter | MaxThreadCount | *int* |

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
| DDN_RuntimeSettings | maxThreadCout | *int* |

**Value Range**  
    [1, 4]

**Default Value**  
    4

**Code Snippet**  
```cpp
// This is a c++ sample code.
DocumentNormalizer::InitLicense("t0260NwAAAHV***************");
DocumentNormalizer* normalizer = new DocumentNormalizer();
DDN_RuntimeSettings settings;
int errorCode = normalizer->GetRuntimeSettings(&settings);
settings->maxThreadCout = 1;
char errorMessage[256];
errorCode = normalizer->UpdateRuntimeSettings(&settings, errorMessage, 256);
delete normalizer;
```

