---
title: Dynamsoft Content Normalizer - Parameter Reference
keywords: parameters, reference, dcn, documentation
description: Dynamsoft Content Normalizer - Parameter Reference
---


# Parameter References

## Brightness
Sets the target brightness value of the final normalized image.

### Setting Methods
#### As Josn Parameter

| Parent Json Object | Json Parameter Name | Value Type | 
| ------------------ | ------------------- | ---------- |
| NormalizationDefinition | Brightness | *int* |

**Value Range**  
    [-100, 100]

**Default Value**  
    0

**Example**  
```json
{
    "Brightness": 50,
}
```

#### As Struct Member

| Struct | Struct Member Name | Value Type | 
| ------ | ------------------ | ---------- |
| DCN_RuntimeSettings->normalizationSettings | brightness | *int* |

**Value Range**  
    [-100, 100]

**Default Value**  
    0

**Code Snippet**  
```cpp
// This is a c++ sample code.
ContentNormalizer::InitLicense("t0260NwAAAHV***************");
ContentNormalizer* normalizer = new ContentNormalizer();
DCN_RuntimeSettings settings;
int errorCode = normalizer->GetRuntimeSettings(&settings);
settings->normalizationSettings.brightness = 50;
char errorMessage[256];
errorCode = normalizer->UpdateRuntimeSettings(&settings, errorMessage, 256);
delete normalizer;
```

## ColourMode

## ContentLocalization

## ContentType

## Contrast

## EnableDeskewing

## EnablePerspectiveCorrection

## Name