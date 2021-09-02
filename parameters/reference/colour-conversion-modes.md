---
title: Dynamsoft Document Normalizer Parameter Reference - ColourConversionModes
keywords: colourconversionmodes, parameters, reference, ddn, documentation
description: Dynamsoft Document Normalizer Parameter Reference - ColourConversionModes
needGenerateH3Content: true
---

# ColourConversionModes
Sets the mode array for converting a colour image to a grayscale image.


## Mode Properties

### `CICM_GENERAL`
Converts a colour image to a grayscale image using the general RGB converting algorithm.

#### Valid Argument
- [`BlueChannelWeight`](#bluechannelweight)
- [`GreenChannelWeight`](#greenchannelweight)
- [`RedChannelWeight`](#redchannelweight)


### `CICM_HSV`
Converts a colour image to a grayscale image using one of the HSV channels.

#### Valid Argument
- [`ReferChannel`](#referchannel)

## Setting Methods
### As Json Parameter

| Parent Json Object | Json Parameter Name | Value Type | 
| ------------------ | ------------------- | ---------- |
| DocumentNormalizerParameter | ColourConversionModes | *JSON object array* |

**Default Setting**   
```json
{
    "ColourConversionModes":[
        {
            "Mode": "CICM_GENERAL"
        }
    ],
}
```

**Example**  
```json
{
    "ColourConversionModes":[
        {
            "Mode": "CICM_GENERAL"
        },
        {
            "Mode": "CICM_HSV",
            "ReferChannel": "H_CHANNEL"
        }
    ],
}
```

### As Struct Member

| Struct | Struct Member Name | Value Type | 
| ------ | ------------------ | ---------- |
| DDN_RuntimeSettings->furtherModes | colourConversionModes | [`ColourConversionMode`]({{ site.common_enumerations }}colour-conversion-mode.html) array |

**Value Range**    
    Each array item can be any one of the [`ColourConversionMode`]({{ site.common_enumerations }}colour-conversion-mode.html) Enumeration items.

**Default Value**   
    [CICM_GENERAL,CICM_SKIP,CICM_SKIP,CICM_SKIP,CICM_SKIP,CICM_SKIP,CICM_SKIP,CICM_SKIP]

**Code Snippet**  
```cpp
// This is a c++ sample code.
DocumentNormalizer::InitLicense("t0260NwAAAHV***************");
DocumentNormalizer* normalizer = new DocumentNormalizer();
DDN_RuntimeSettings settings;
int errorCode = normalizer->GetRuntimeSettings(&settings);
settings->furtherModes.colourConversionModes[0] = CICM_GENERAL;
settings->furtherModes.colourConversionModes[1] = CICM_HSV;
char errorMessage[256];
errorCode = normalizer->UpdateRuntimeSettings(&settings, errorMessage, 256);
delete normalizer;
```

## Arguments Reference   
- [`BlueChannelWeight`](#bluechannelweight)
- [`GreenChannelWeight`](#greenchannelweight)
- [`RedChannelWeight`](#redchannelweight)
- [`ReferChannel`](#referchannel)


### BlueChannelWeight

| Argument Name| Valid for Mode(s) | Value Type|
| ------------ | ----------------- | --------- |
| BlueChannelWeight | `CICM_GENERAL` | *int* |

**Value Range**    
    [-1, 1000]

**Default Value**   
    -1

**Remarks**
-1: The weight value will be set automatically by the SDK.

### GreenChannelWeight

| Argument Name| Valid for Mode(s) | Value Type|
| ------------ | ----------------- | --------- |
| GreenChannelWeight | `CICM_GENERAL` | *int* |

**Value Range**    
    [-1, 1000]

**Default Value**   
    -1

**Remarks**
-1: The weight value will be set automatically by the SDK.

### RedChannelWeight

| Argument Name| Valid for Mode(s) | Value Type|
| ------------ | ----------------- | --------- |
| RedChannelWeight | `CICM_GENERAL` | *int* |

**Value Range**    
    [-1, 1000]

**Default Value**   
    -1

**Remarks**
-1: The weight value will be set automatically by the SDK.

### ReferChannel

| Argument Name| Valid for Mode(s) | Value Type|
| ------------ | ----------------- | --------- |
| ReferChannel | `CICM_HSV` | *string* |

**Value Range**    
    "H_CHANNEL"   
    "S_CHANNEL"  
    "V_CHANNEL"

**Default Value**   
    "H_CHANNEL" 

