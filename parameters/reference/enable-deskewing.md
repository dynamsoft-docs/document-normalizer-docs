---
title: Dynamsoft Document Normalizer Parameter Reference - EnableDeskewing
keywords: enabledeskewing, parameters, reference, ddn, documentation
description: Dynamsoft Document Normalizer Parameter Reference - EnableDeskewing
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
| DDN_RuntimeSettings->normalizationSettings | enableDeskewing | *int* |

**Value Range**  
    [0, 1]

**Default Value**  
    1

**Code Snippet**  
```cpp
// This is a c++ sample code.
DocumentNormalizer::InitLicense("t0260NwAAAHV***************");
DocumentNormalizer* normalizer = new DocumentNormalizer();
DDN_RuntimeSettings settings;
int errorCode = normalizer->GetRuntimeSettings(&settings);
settings->normalizationSettings.enableDeskewing = 0;
char errorMessage[256];
errorCode = normalizer->UpdateRuntimeSettings(&settings, errorMessage, 256);
delete normalizer;
```

