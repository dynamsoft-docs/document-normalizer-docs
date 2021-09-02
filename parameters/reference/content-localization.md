---
title: Dynamsoft Document Normalizer Parameter Reference - ContentLocalization
keywords: contentlocalization, parameters, reference, ddn, documentation
description: Dynamsoft Document Normalizer Parameter Reference - ContentLocalization
needGenerateH3Content: true
---


# ContentLocalization
Sets the localization of content to be normalized.

## SourceType Properties

### `CBLM_MANNUAL_SPECIFICATION`
Define the content boundary using the manually specified location.

#### Valid Argument
- [`FirstPoint`](#firstpoint)
- [`SecondPoint`](#secondpoint)
- [`ThirdPoint`](#thirdpoint)
- [`FourthPoint`](#fourthpoint)

### `CBLM_AUTO_DETECTION`
Define the content boundary using the result(s) of automatic detection.

### `CBLM_WHOLE_IMAGE`
Define the content boundary using the image boundary.

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
| DDN_RuntimeSettings->normalizationSettings | localizationMode | [`ContentBoundaryLocalizationMode`]({{ site.enumerations }}content-boundary-localization-mode.html) |

**Value Range**  
    Any one of the [`ContentBoundaryLocalizationMode`]({{ site.enumerations }}content-boundary-localization-mode.html) items.

**Default Value**  
    `CBLM_AUTO_DETECTION`

**Code Snippet**  
```cpp
// This is a c++ sample code.
DocumentNormalizer::InitLicense("t0260NwAAAHV***************");
DocumentNormalizer* normalizer = new DocumentNormalizer();
DDN_RuntimeSettings settings;
int errorCode = normalizer->GetRuntimeSettings(&settings);
settings->normalizationSettings.localizationMode = CBLM_WHOLE_IMAGE;
char errorMessage[256];
errorCode = normalizer->UpdateRuntimeSettings(&settings, errorMessage, 256);
delete normalizer;
```



## Arguments Reference
- [`FirstPoint`](#firstpoint)
- [`SecondPoint`](#secondpoint)
- [`ThirdPoint`](#thirdpoint)
- [`FourthPoint`](#fourthpoint)


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
    