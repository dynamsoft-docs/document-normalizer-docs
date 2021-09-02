---
title: Dynamsoft Document Normalizer Parameter Reference - InteriorAngleRange
keywords: interioranglerange, parameters, reference, ddn, documentation
description: Dynamsoft Document Normalizer Parameter Reference - InteriorAngleRange
needGenerateH3Content: true
---


# InteriorAngleRange
Sets the quadrilateral interior angle range.

## Setting Methods
### As Json Parameter

| Parent Json Object | Json Parameter Name | Value Type | 
| ------------------ | ------------------- | ---------- |
| DocumentNormalizerParameter | InteriorAngleRange | *int array* |

**Value Range**    
    Format: [`minInteriorAngleValue`, `maxInteriorAngleValue`]    
    Allowed value range:   
        &emsp;&emsp;For `minInteriorAngleValue` / `maxInteriorAngleValue`: [0, 180]  

**Default Value**   
    [70, 110]

**Example**  
```json
{
    "InteriorAngleRange": [60, 120],
}
```

### As Struct Member

| Struct | Struct Member Name | Value Type | 
| ------ | ------------------ | ---------- |
| DDN_RuntimeSettings | interiorAngleRange | *int array* |

**Value Range**    
    Format: [`minInteriorAngleValue`, `maxInteriorAngleValue`]    
    Allowed value range:   
        &emsp;&emsp;For `minInteriorAngleValue` / `maxInteriorAngleValue`: [0, 180]  

**Default Value**   
    [70, 110]

**Code Snippet**  
```cpp
// This is a c++ sample code.
DocumentNormalizer::InitLicense("t0260NwAAAHV***************");
DocumentNormalizer* normalizer = new DocumentNormalizer();
DDN_RuntimeSettings settings;
int errorCode = normalizer->GetRuntimeSettings(&settings);
settings->interiorAngleRange[0] = 60;
settings->interiorAngleRange[1] = 120;
char errorMessage[256];
errorCode = normalizer->UpdateRuntimeSettings(&settings, errorMessage, 256);
delete normalizer;
```
