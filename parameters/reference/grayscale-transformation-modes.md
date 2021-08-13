---
title: Dynamsoft Content Normalizer Parameter Reference - GrayscaleTransformationModes
keywords: grayscaletransformationmodes, parameters, reference, dcn, documentation
description: Dynamsoft Content Normalizer Parameter Reference - GrayscaleTransformationModes
needGenerateH3Content: true
---


# GrayscaleTransformationModes
Sets the mode array for the grayscale image conversion.

## Mode Properties

### `GTM_INVERTED`
Transforms to inverted grayscale. Recommended for light on dark images.


### `GTM_ORIGINAL`
Keeps the original grayscale. Recommended for dark on light images.


### `GTM_AUTO`
Let the library choose an algorithm automatically for grayscale transformation.


## Setting Methods
### As Json Parameter

| Parent Json Object | Json Parameter Name | Value Type | 
| ------------------ | ------------------- | ---------- |
| ContentNormalizerParameter | GrayscaleTransformationModes | *JSON object array* |

**Default Setting**   
```json
{
    "GrayscaleTransformationModes":[
        {
            "Mode": "GTM_ORIGINAL"
        }
    ],
}
```

**Example**  
```json
{
    "GrayscaleTransformationModes":[
        {
            "Mode": "GTM_INVERTED"
        },
        {
            "Mode": "GTM_ORIGINAL"
        }
    ],
}
```

### As Struct Member

| Struct | Struct Member Name | Value Type | 
| ------ | ------------------ | ---------- |
| DCN_RuntimeSettings->furtherModes | grayscaleTransformationModes | [`GrayscaleTransformationMode`]({{ site.enumerations }}grayscale-transformation-mode.html) array |

**Value Range**    
    Each array item can be any one of the [`GrayscaleTransformationMode`]({{ site.enumerations }}grayscale-transformation-mode.html) Enumeration items.

**Default Value**   
    [GTM_ORIGINAL,GTM_SKIP,GTM_SKIP,GTM_SKIP,GTM_SKIP,GTM_SKIP,GTM_SKIP,GTM_SKIP]

**Code Snippet**  
```cpp
// This is a c++ sample code.
ContentNormalizer::InitLicense("t0260NwAAAHV***************");
ContentNormalizer* normalizer = new ContentNormalizer();
DCN_RuntimeSettings settings;
int errorCode = normalizer->GetRuntimeSettings(&settings);
settings->furtherModes.grayscaleTransformationModes[0] = GTM_INVERTED;
settings->furtherModes.grayscaleTransformationModes[1] = GTM_ORIGINAL;
char errorMessage[256];
errorCode = normalizer->UpdateRuntimeSettings(&settings, errorMessage, 256);
delete normalizer;
```

