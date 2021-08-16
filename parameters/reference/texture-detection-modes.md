---
title: Dynamsoft Content Normalizer Parameter Reference - TextureDetectionModes
keywords: texturedetectionmodes, parameters, reference, dcn, documentation
description: Dynamsoft Content Normalizer Parameter Reference - TextureDetectionModes
needGenerateH3Content: true
---


## TextureDetectionModes
Sets the mode array for texture detection. 

## Mode Properties

### `TDM_GENERAL_WIDTH_CONCENTRATION`
Transforms to inverted grayscale. Recommended for light on dark images.

#### Valid Argument
- [`Sensitivity`](#sensitivity)


## Setting Methods
### As Json Parameter

| Parent Json Object | Json Parameter Name | Value Type | 
| ------------------ | ------------------- | ---------- |
| ContentNormalizerParameter | TextureDetectionModes | *JSON object array* |

**Default Setting**   
```json
{
    "TextureDetectionModes":[
        {
            "Mode": "TDM_GENERAL_WIDTH_CONCENTRATION",
            "Sensitivity": 5
        }
    ],
}
```

**Example**  
```json
{
    "TextureDetectionModes":[
        {
            "Mode": "TDM_SKIP"
        }
    ],
}
```

### As Struct Member

| Struct | Struct Member Name | Value Type | 
| ------ | ------------------ | ---------- |
| DCN_RuntimeSettings | textureDetectionModes | [`TextureDetectionMode`]({{ site.enumerations }}texture-detection-mode.html) array |

**Value Range**    
    Each array item can be any one of the [`TextureDetectionMode`]({{ site.enumerations }}texture-detection-mode.html) Enumeration items.

**Default Value**   
    [TDM_GENERAL_WIDTH_CONCENTRATION,TDM_SKIP,TDM_SKIP,TDM_SKIP,TDM_SKIP,TDM_SKIP,TDM_SKIP,TDM_SKIP]

**Code Snippet**  
```cpp
// This is a c++ sample code.
ContentNormalizer::InitLicense("t0260NwAAAHV***************");
ContentNormalizer* normalizer = new ContentNormalizer();
DCN_RuntimeSettings settings;
int errorCode = normalizer->GetRuntimeSettings(&settings);
settings->furtherModes.textureDetectionModes[0] = TDM_SKIP;
char errorMessage[256];
errorCode = normalizer->UpdateRuntimeSettings(&settings, errorMessage, 256);
delete normalizer;
```

## Arguments Reference
- [`Sensitivity`](#sensitivity)

### Sensitivity

| Argument Name | Valid for Mode(s) | Value Type | 
| ------------- | ----------------- | ---------- |
| Sensitivity | `TDM_GENERAL_WIDTH_CONCENTRATION` | *int* |

**Value Range**   
    [1, 9]

**Default Value**   
    5

**Remarks**  
A larger value means the library will take more effort to detect texture.

