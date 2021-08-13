---
title: Dynamsoft Content Normalizer Parameter Reference - GrayscaleEnhancementModes
keywords: grayscaleenhancementmodes, parameters, reference, dcn, documentation
description: Dynamsoft Content Normalizer Parameter Reference - GrayscaleEnhancementModes
needGenerateH3Content: true
---


# GrayscaleEnhancementModes
Sets the mode array for the enhancing grayscale image before content normalization. 

## Mode Properties

### `GEM_GENERAL`
Takes the un-preprocessed grayscale image for following operations.


### `GEM_GRAY_EQUALIZE`
Preprocesses the grayscale image using the gray equalization algorithm.

#### Valid Argument
- `Sensitivity`


### `GEM_GARY_SMOOTM`
Preprocesses the grayscale image using the gray smoothing algorithm.

#### Valid Argument
- `SmoothBlockSizeX`
- `SmoothBlockSizeY`


### `GEM_SHARPEN_SMOOTH`
Preprocesses the grayscale image using the sharpening and smoothing algorithm.

#### Valid Argument
- `SmoothBlockSizeX`
- `SmoothBlockSizeY`
- `SharpenBlockSizeX`
- `SharpenBlockSizeY`


## Setting Methods
### As Json Parameter

| Parent Json Object | Json Parameter Name | Value Type | 
| ------------------ | ------------------- | ---------- |
| ContentNormalizerParameter | GrayscaleEnhancementModes | *JSON object array* |

**Default Setting**   
```json
{
    "GrayscaleEnhancementModes":[
        {
            "Mode": "GEM_GENERAL"
        }
    ],
}
```

**Example**  
```json
{
    "GrayscaleEnhancementModes": [
    {
        "Mode": "GEM_GRAY_EQUALIZE",
        "Sensitivity": 5
    },
    {
        "Mode": "GEM_SHARPEN_SMOOTH",
        "SmoothBlockSizeX": 5, 
        "SmoothBlockSizeY": 5, 
        "SharpenBlockSizeX": 5, 
        "SharpenBlockSizeY": 5
    }
    ],
}
```

### As Struct Member

| Struct | Struct Member Name | Value Type | 
| ------ | ------------------ | ---------- |
| DCN_RuntimeSettings->furtherModes | grayscaleEnhancementModes | [`GrayscaleEnhancementMode`]({{ site.common_enumerations }}grayscale-enhancement-mode.html) array |

**Value Range**    
    Each array item can be any one of the [`GrayscaleEnhancementMode`]({{ site.common_enumerations }}grayscale-enhancement-mode.html) Enumeration items.

**Default Value**   
    [GEM_GENERAL,GEM_SKIP,GEM_SKIP,GEM_SKIP,GEM_SKIP,GEM_SKIP,GEM_SKIP,GEM_SKIP]

**Code Snippet**  
```cpp
// This is a c++ sample code.
ContentNormalizer::InitLicense("t0260NwAAAHV***************");
ContentNormalizer* normalizer = new ContentNormalizer();
DCN_RuntimeSettings settings;
int errorCode = normalizer->GetRuntimeSettings(&settings);
settings->furtherModes.grayscaleEnhancementModes[0] = GEM_GRAY_EQUALIZE;
settings->furtherModes.grayscaleEnhancementModes[1] = GEM_SHARPEN_SMOOTH;
char errorMessage[256];
errorCode = normalizer->UpdateRuntimeSettings(&settings, errorMessage, 256);
delete normalizer;
```


## Arguments Reference
- [`Sensitivity`](#sensitivity)
- [`SharpenBlockSizeX`](#sharpenblocksizex)
- [`SharpenBlockSizeY`](#sharpenblocksizey)
- [`SmoothBlockSizeX`](#smoothblocksizex)
- [`SmoothBlockSizeY`](#smoothblocksizey)


### Sensitivity

| Argument Name| Valid for Mode(s) | Value Type|
| ------------ | ----------------- | --------- |
| Sensitivity | `GEM_GRAY_EQUALIZE` | *int* |

**Value Range**    
    [1, 9]

**Default Value**   
    5

### SharpenBlockSizeX

| Argument Name| Valid for Mode(s) | Value Type|
| ------------ | ----------------- | --------- |
| SharpenBlockSizeX | `GEM_SHARPEN_SMOOTH` | *int* |

**Value Range**    
    [3, 1000]

**Default Value**   
    3

### SharpenBlockSizeY

| Argument Name| Valid for Mode(s) | Value Type|
| ------------ | ----------------- | --------- |
| SharpenBlockSizeY | `GEM_SHARPEN_SMOOTH` | *int* |

**Value Range**    
    [3, 1000]

**Default Value**   
    3

### SmoothBlockSizeX

| Argument Name| Valid for Mode(s) | Value Type|
| ------------ | ----------------- | --------- |
| SmoothBlockSizeX | `GEM_GARY_SMOOTM`<br>`GEM_SHARPEN_SMOOTH` | *int* |

**Value Range**    
    [3, 1000]

**Default Value**   
    3

### SmoothBlockSizeY

| Argument Name| Valid for Mode(s) | Value Type|
| ------------ | ----------------- | --------- |
| SmoothBlockSizeY | `GEM_GARY_SMOOTM`<br>`GEM_SHARPEN_SMOOTH` | *int* |

**Value Range**    
    [3, 1000]

**Default Value**   
    3
