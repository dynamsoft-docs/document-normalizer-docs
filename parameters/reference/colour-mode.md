---
title: Dynamsoft Content Normalizer Parameter Reference - ColourMode
keywords: colourmode, parameters, reference, dcn, documentation
description: Dynamsoft Content Normalizer Parameter Reference - ColourMode
needGenerateH3Content: true
---


# ColourMode
Sets the target colour mode of the final normalized image.

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
| DCN_RuntimeSettings->normalizationSettings | colourMode | [`ImageColourMode`]({{ site.enumerations }}image-colour-mode.html) |

**Value Range**  
    Any one of the [`ImageColourMode`]({{ site.enumerations }}image-colour-mode.html) items.

**Default Value**  
    `ICM_BINARY`

**Code Snippet**  
```cpp
// This is a c++ sample code.
ContentNormalizer::InitLicense("t0260NwAAAHV***************");
ContentNormalizer* normalizer = new ContentNormalizer();
DCN_RuntimeSettings settings;
int errorCode = normalizer->GetRuntimeSettings(&settings);
settings->normalizationSettings.colourMode = ICM_COLOUR;
char errorMessage[256];
errorCode = normalizer->UpdateRuntimeSettings(&settings, errorMessage, 256);
delete normalizer;
```
