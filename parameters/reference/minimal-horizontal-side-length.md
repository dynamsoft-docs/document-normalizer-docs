---
title: Dynamsoft Document Normalizer Parameter Reference - MinimalHorizontalSideLength
keywords: minimalhorizontalsidelength, parameters, reference, ddn, documentation
description: Dynamsoft Document Normalizer Parameter Reference - MinimalHorizontalSideLength
needGenerateH3Content: true
---


# MinimalHorizontalSideLength
Sets the minimal horizontal side length of the quadrilateral. 

## Setting Methods
### As Json Parameter

| Parent Json Object | Json Parameter Name | Value Type | 
| ------------------ | ------------------- | ---------- |
| DocumentNormalizerParameter | MinimalHorizontalSideLength | *int array* |

**Value Range**    
    Format: [`minimalSideLength`, `ByPercentage`]    
    Allowed value range:   
        &emsp;&emsp;For `minimalSideLength`: `ByPercentage`=0: [1, 0x7fffffff], `ByPercentage`=1: [1, 100]   
        &emsp;&emsp;For `ByPercentage`: [0, 1]   

**Default Value**   
    [15, 1]

**Example**  
```json
{
    "MinimalHorizontalSideLength": [200, 0],
}
```

### As Struct Member

| Struct | Struct Member Name | Value Type | 
| ------ | ------------------ | ---------- |
| DDN_RuntimeSettings | minimalHorizontalSideLength | *int array* |

**Value Range**    
    Format: [`minimalSideLength`, `ByPercentage`]    
    Allowed value range:   
        &emsp;&emsp;For `minimalSideLength`: `ByPercentage`=0: [1, 0x7fffffff], `ByPercentage`=1: [1, 100]   
        &emsp;&emsp;For `ByPercentage`: [0, 1]   

**Default Value**   
    [15, 1]

**Code Snippet**  
```cpp
// This is a c++ sample code.
DocumentNormalizer::InitLicense("t0260NwAAAHV***************");
DocumentNormalizer* normalizer = new DocumentNormalizer();
DDN_RuntimeSettings settings;
int errorCode = normalizer->GetRuntimeSettings(&settings);
settings->minimalHorizontalSideLength[0] = 200;
settings->minimalHorizontalSideLength[1] = 0;
char errorMessage[256];
errorCode = normalizer->UpdateRuntimeSettings(&settings, errorMessage, 256);
delete normalizer;
```

