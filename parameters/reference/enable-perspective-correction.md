---
title: Dynamsoft Content Normalizer Parameter Reference - EnablePerspectiveCorrection
keywords: enableperspectivecorrection, parameters, reference, dcn, documentation
description: Dynamsoft Content Normalizer Parameter Reference - EnablePerspectiveCorrection
needGenerateH3Content: true
---

# EnablePerspectiveCorrection
Sets enable perspective correction during normalization or not.

## Setting Methods
### As Json Parameter

| Parent Json Object | Json Parameter Name | Value Type | 
| ------------------ | ------------------- | ---------- |
| NormalizationDefinition | EnablePerspectiveCorrection | *int* |

**Value Range**  
    [0, 1]

**Default Value**  
    1

**Example**  
```json
{
    "EnablePerspectiveCorrection": 0,
}
```

### As Struct Member

| Struct | Struct Member Name | Value Type | 
| ------ | ------------------ | ---------- |
| DCN_RuntimeSettings->normalizationSettings | enablePerspectiveCorrection | *int* |

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
settings->normalizationSettings.enablePerspectiveCorrection = 0;
char errorMessage[256];
errorCode = normalizer->UpdateRuntimeSettings(&settings, errorMessage, 256);
delete normalizer;
```
