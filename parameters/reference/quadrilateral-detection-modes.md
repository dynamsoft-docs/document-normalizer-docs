---
title: Dynamsoft Document Normalizer Parameter Reference - QuadrilateralDetectionModes
keywords: quadrilateraldetectionmodes, parameters, reference, ddn, documentation
description: Dynamsoft Document Normalizer Parameter Reference - QuadrilateralDetectionModes
needGenerateH3Content: true
---

# QuadrilateralDetectionModes
Sets the mode array for quadrilateral detection.

## Mode Properties

### `QDM_LINE_BASED_DETECTION`
Defines line-based quadrilateral detection.


### `QDM_MARGIN_BASED_DETECTION`
Defines margin-based quadrilateral detection.


## Setting Methods
### As Json Parameter

| Parent Json Object | Json Parameter Name | Value Type | 
| ------------------ | ------------------- | ---------- |
| DocumentNormalizerParameter | QuadrilateralDetectionModes | *JSON object array* |

**Default Setting**   
```json
{
    "QuadrilateralDetectionModes":[
        {
            "Mode": "QDM_LINE_BASED_DETECTION"
        }
    ],
}
```

**Example**  
```json
{
    "QuadrilateralDetectionModes":[
        {
            "Mode": "QDM_MARGIN_BASED_DETECTION"
        },
        {
            "Mode": "QDM_LINE_BASED_DETECTION"
        }
    ],
}
```

### As Struct Member

| Struct | Struct Member Name | Value Type | 
| ------ | ------------------ | ---------- |
| DDN_RuntimeSettings | detectionModes | [`QuadrilateralDetectionMode`]({{ site.enumerations }}quadrilateral-detection-mode.html) array |

**Value Range**    
    Each array item can be any one of the [`QuadrilateralDetectionMode`]({{ site.enumerations }}quadrilateral-detection-mode.html) Enumeration items.

**Default Value**   
    [QDM_LINE_BASED_DETECTION,QDM_SKIP_DETECTION,QDM_SKIP_DETECTION,QDM_SKIP_DETECTION,QDM_SKIP_DETECTION,QDM_SKIP_DETECTION,QDM_SKIP_DETECTION,QDM_SKIP_DETECTION]

**Code Snippet**  
```cpp
// This is a c++ sample code.
DocumentNormalizer::InitLicense("t0260NwAAAHV***************");
DocumentNormalizer* normalizer = new DocumentNormalizer();
DDN_RuntimeSettings settings;
int errorCode = normalizer->GetRuntimeSettings(&settings);
settings->detectionModes[0] = QDM_MARGIN_BASED_DETECTION;
settings->detectionModes[1] = QDM_LINE_BASED_DETECTION;
char errorMessage[256];
errorCode = normalizer->UpdateRuntimeSettings(&settings, errorMessage, 256);
delete normalizer;
```

