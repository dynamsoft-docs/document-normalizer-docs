---
title: Dynamsoft Document Normalizer Parameter Reference - Brightness
keywords: brightness, parameters, reference, ddn, documentation
description: Dynamsoft Document Normalizer Parameter Reference - Brightness
needGenerateH3Content: true
---


# Brightness
Sets the target brightness value of the final normalized image.

## Setting Methods
### As Json Parameter

| Parent Json Object | Json Parameter Name | Value Type | 
| ------------------ | ------------------- | ---------- |
| NormalizationDefinition | Brightness | *int* |

**Value Range**  
    [-100, 100]

**Default Value**  
    0

**Example**  
```json
{
    "Brightness": 50,
}
```

### As Struct Member

| Struct | Struct Member Name | Value Type | 
| ------ | ------------------ | ---------- |
| DDN_RuntimeSettings->normalizationSettings | brightness | *int* |

**Value Range**  
    [-100, 100]

**Default Value**  
    0

**Code Snippet**  
```cpp
// This is a c++ sample code.
DocumentNormalizer::InitLicense("t0260NwAAAHV***************");
DocumentNormalizer* normalizer = new DocumentNormalizer();
DDN_RuntimeSettings settings;
int errorCode = normalizer->GetRuntimeSettings(&settings);
settings->normalizationSettings.brightness = 50;
char errorMessage[256];
errorCode = normalizer->UpdateRuntimeSettings(&settings, errorMessage, 256);
delete normalizer;
```
