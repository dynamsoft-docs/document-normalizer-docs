---
title: Dynamsoft Content Normalizer Parameter Reference - TargetContentPageSize
keywords: targetcontentpagesize, parameters, reference, dcn, documentation
description: Dynamsoft Content Normalizer Parameter Reference - TargetContentPageSize
needGenerateH3Content: true
---

## TargetContentPageSize
Sets the target content page size (width x height in millimeters).

### Setting Methods
#### As Json Parameter

| Parent Json Object | Json Parameter Name | Value Type | 
| ------------------ | ------------------- | ---------- |
| NormalizationDefinition | TargetContentPageSize | *int array* |

**Value Range**    
    Format: [`targetPageWidth`, `targetPageHeight`]    
    Allowed value range:   
        &emsp;&emsp;For `targetPageWidth` / `targetPageHeight`: [-1, 0x7fffffff] 

**Default Value**   
    [-1, -1]

**Example**  
```json
{
    "TargetContentPageSize": [210, 297],
}
```

#### As Struct Member

| Struct | Struct Member Name | Value Type | 
| ------ | ------------------ | ---------- |
| DCN_RuntimeSettings->normalizationSettings | targetContentPageSize | *int array* |

**Value Range**    
    Format: [`targetPageWidth`, `targetPageHeight`]    
    Allowed value range:   
        &emsp;&emsp;For `targetPageWidth` / `targetPageHeight`: [-1, 0x7fffffff] 

**Default Value**   
    [-1, -1]

**Code Snippet**  
```cpp
// This is a c++ sample code.
ContentNormalizer::InitLicense("t0260NwAAAHV***************");
ContentNormalizer* normalizer = new ContentNormalizer();
DCN_RuntimeSettings settings;
int errorCode = normalizer->GetRuntimeSettings(&settings);
settings->normalizationSettings.targetContentPageSize[0] = 210;
settings->normalizationSettings.targetContentPageSize[1] = 297;
char errorMessage[256];
errorCode = normalizer->UpdateRuntimeSettings(&settings, errorMessage, 256);
delete normalizer;
```


