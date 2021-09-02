---
title: Dynamsoft Document Normalizer Parameter Reference - ExecutePhases
keywords: executephases, parameters, reference, ddn, documentation
description: Dynamsoft Document Normalizer Parameter Reference - ExecutePhases
needGenerateH3Content: true
---


# ExecutePhases
Sets the string array for specifying the phase(s) to be executed.

## Setting Methods
### As Json Parameter

| Parent Json Object | Json Parameter Name | Value Type | 
| ------------------ | ------------------- | ---------- |
| DocumentNormalizerParameter | ExecutePhases | *string array* |

**Value Range**    
    An array item can be any one of the [`ExecutePhase`]({{ site.enumerations }}execute-phase.html) Enumeration items.

**Default Value**   
    ["EP_ALL"]

**Example**  
```json
{
    "ExecutePhases": ["EP_QUAD_DETECTION", "EP_BASIC_NORMALIZATION"],
}
```

### As Struct Member

| Struct | Struct Member Name | Value Type | 
| ------ | ------------------ | ---------- |
| DDN_RuntimeSettings | executePhases | *int* |

**Value Range**    
    A combined value of [`ExecutePhase`]({{ site.enumerations }}execute-phase.html) Enumeration items.

**Default Value**   
    EP_ALL

**Code Snippet**  
```cpp
// This is a c++ sample code.
DocumentNormalizer::InitLicense("t0260NwAAAHV***************");
DocumentNormalizer* normalizer = new DocumentNormalizer();
DDN_RuntimeSettings settings;
int errorCode = normalizer->GetRuntimeSettings(&settings);
settings->executePhases = EP_QUAD_DETECTION | EP_BASIC_NORMALIZATION;
char errorMessage[256];
errorCode = normalizer->UpdateRuntimeSettings(&settings, errorMessage, 256);
delete normalizer;
```

