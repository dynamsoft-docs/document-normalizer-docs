---
title: Dynamsoft Content Normalizer Parameter Reference - ContentLocalization
keywords: contentlocalization, parameters, reference, dcn, documentation
description: Dynamsoft Content Normalizer Parameter Reference - ContentLocalization
needGenerateH3Content: true
---


# ContentLocalization
Sets the localization of content to be normalized.

## Setting Methods
### As Json Parameter

| Parent Json Object | Json Parameter Name | Value Type | 
| ------------------ | ------------------- | ---------- |
| NormalizationDefinition | ContentLocalization | *JSON Object* |

**Default Setting**  
```json
{
    "ContentLocalization": {
        "SourceType": "CBLM_AUTO_DETECTION"
    },
}
```

**Example**  
```json
{
    "ContentLocalization": {
        "SourceType": "CBLM_MANNUAL_SPECIFICATION",
        "FirstPoint": [200, 200],
        "SecondPoint": [400, 200],
        "ThirdPoint": [400, 400],
        "FourthPoint": [200, 400]
    },
}
```

### As Struct Member

| Struct | Struct Member Name | Value Type | 
| ------ | ------------------ | ---------- |
| DCN_RuntimeSettings->normalizationSettings | localizationMode | [`ContentBoundaryLocalizationMode`]({{ site.enumerations }}content-boundary-localization-mode.html) |

**Value Range**  
    Any one of the [`ContentBoundaryLocalizationMode`]({{ site.enumerations }}content-boundary-localization-mode.html) items.

**Default Value**  
    `CBLM_AUTO_DETECTION`

**Code Snippet**  
```cpp
// This is a c++ sample code.
ContentNormalizer::InitLicense("t0260NwAAAHV***************");
ContentNormalizer* normalizer = new ContentNormalizer();
DCN_RuntimeSettings settings;
int errorCode = normalizer->GetRuntimeSettings(&settings);
settings->normalizationSettings.localizationMode = CBLM_WHOLE_IMAGE;
char errorMessage[256];
errorCode = normalizer->UpdateRuntimeSettings(&settings, errorMessage, 256);
delete normalizer;
```



## Arguments Reference
- [`SourceType`](#sourcetype)
- [`FirstPoint`](#firstpoint)
- [`SecondPoint`](#secondpoint)
- [`ThirdPoint`](#thirdpoint)
- [`FourthPoint`](#fourthpoint)

### SourceType

| Argument Name | Value Type | 
| ------------- | ---------- |
| SourceType | *string* |

**Value Range**   
    Any one of the [`ContentBoundaryLocalizationMode`]({{ site.enumerations }}content-boundary-localization-mode.html) items.

**Default Value**   
    "CBLM_AUTO_DETECTION"

### FirstPoint

| Argument Name | Valid for SourceType(s) | Value Type | 
| ------------- | ----------------------- | ---------- |
| FirstPoint | `CBLM_MANNUAL_SPECIFICATION` | *int array* |

**Value Range**    
    Format: [`x-coordinate`, `y-coordinate`]    
    Allowed value range:   
        &emsp;&emsp;For `x-coordinate` / `y-coordinate`: [-1, 0x7fffffff] 

**Default Value**   
    [-1, -1]

### SecondPoint

| Argument Name | Valid for SourceType(s) | Value Type | 
| ------------- | ----------------------- | ---------- |
| SecondPoint | `CBLM_MANNUAL_SPECIFICATION` | *int array* |

**Value Range**    
    Format: [`x-coordinate`, `y-coordinate`]    
    Allowed value range:   
        &emsp;&emsp;For `x-coordinate` / `y-coordinate`: [-1, 0x7fffffff] 

**Default Value**   
    [-1, -1]

### ThirdPoint

| Argument Name | Valid for SourceType(s) | Value Type | 
| ------------- | ----------------------- | ---------- |
| ThirdPoint | `CBLM_MANNUAL_SPECIFICATION` | *int array* |

**Value Range**    
    Format: [`x-coordinate`, `y-coordinate`]    
    Allowed value range:   
        &emsp;&emsp;For `x-coordinate` / `y-coordinate`: [-1, 0x7fffffff] 

**Default Value**   
    [-1, -1]

### FourthPoint

| Argument Name | Valid for SourceType(s) | Value Type | 
| ------------- | ----------------------- | ---------- |
| FourthPoint | `CBLM_MANNUAL_SPECIFICATION` | *int array* |

**Value Range**    
    Format: [`x-coordinate`, `y-coordinate`]    
    Allowed value range:   
        &emsp;&emsp;For `x-coordinate` / `y-coordinate`: [-1, 0x7fffffff] 

**Default Value**   
    [-1, -1]
    