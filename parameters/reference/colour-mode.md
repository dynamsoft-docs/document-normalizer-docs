---
title: Dynamsoft Document Normalizer Parameter Reference - ColourMode
keywords: colourmode, parameters, reference, ddn, documentation
description: Dynamsoft Document Normalizer Parameter Reference - ColourMode
needGenerateH3Content: true
---


# ColourMode
Sets the target colour mode of the final normalized image.

## Mode Properties

### `ICM_BINARY`
Defines a black-white image.


### `ICM_GRAYSCALE`
Defines a grayscale image.


### `ICM_COLOUR`
Defines a colour image.


## Setting Methods
### As Json Parameter

| Parent Json Object | Json Parameter Name | Value Type | 
| ------------------ | ------------------- | ---------- |
| NormalizationDefinition | ColourMode | *string* |

**Value Range**  
    Any one of the [`ImageColourMode`]({{ site.enumerations }}image-colour-mode.html) items.

**Default Value**  
    "ICM_BINARY"

**Example**  
```json
{
    "ColourMode": "ICM_COLOUR",
}
```

### As Struct Member

| Struct | Struct Member Name | Value Type | 
| ------ | ------------------ | ---------- |
| DDN_RuntimeSettings->normalizationSettings | colourMode | [`ImageColourMode`]({{ site.enumerations }}image-colour-mode.html) |

**Value Range**  
    Any one of the [`ImageColourMode`]({{ site.enumerations }}image-colour-mode.html) items.

**Default Value**  
    `ICM_BINARY`

**Code Snippet**  
```cpp
// This is a c++ sample code.
DocumentNormalizer::InitLicense("t0260NwAAAHV***************");
DocumentNormalizer* normalizer = new DocumentNormalizer();
DDN_RuntimeSettings settings;
int errorCode = normalizer->GetRuntimeSettings(&settings);
settings->normalizationSettings.colourMode = ICM_COLOUR;
char errorMessage[256];
errorCode = normalizer->UpdateRuntimeSettings(&settings, errorMessage, 256);
delete normalizer;
```
