---
title: Dynamsoft Content Normalizer Parameter Reference - EnableDeskewing
keywords: enabledeskewing, parameters, reference, dcn, documentation
description: Dynamsoft Content Normalizer Parameter Reference - EnableDeskewing
needGenerateH3Content: true
---

# EnableDeskewing
Sets enable de-skewing during normalization or not.

## Setting Methods
### As Json Parameter

| Parent Json Object | Json Parameter Name | Value Type | 
| ------------------ | ------------------- | ---------- |
| NormalizationDefinition | EnableDeskewing | *int* |

**Value Range**  
    [0, 1]

**Default Value**  
    1

**Example**  
```json
{
    "EnableDeskewing": 0,
}
```

### As Struct Member

| Struct | Struct Member Name | Value Type | 
| ------ | ------------------ | ---------- |
| DCN_RuntimeSettings->normalizationSettings | enableDeskewing | *int* |

**Value Range**  
    [0, 1]

**Default Value**  
    1

**Code Snippet**  
```cpp
// This is a c++ sample code.
ContentNormalizer::InitLicense("t0260NwAAAHV***************");
ContentNormalizer* normalizer = new ContentNormalizer();
DCN_RuntimeSettings settings;
int errorCode = normalizer->GetRuntimeSettings(&settings);
settings->normalizationSettings.enableDeskewing = 0;
char errorMessage[256];
errorCode = normalizer->UpdateRuntimeSettings(&settings, errorMessage, 256);
delete normalizer;
```

