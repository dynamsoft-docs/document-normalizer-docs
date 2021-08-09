---
title: Dynamsoft Content Normalizer - Parameter Reference
keywords: parameters, reference, dcn, documentation
description: Dynamsoft Content Normalizer - Parameter Reference
---


# Parameter References

## Brightness
Sets the target brightness value of the final normalized image.

### Setting Methods
#### As Json Parameter

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
The target colour mode of the final normalized image.

### Setting Methods
#### As Json Parameter

| Parent Json Object | Json Parameter Name | Value Type | 
| ------------------ | ------------------- | ---------- |
| NormalizationDefinition | ColourMode | *string* |

**Value Range**  
    Any one of the ImageColourMode items.

**Default Value**  
    "ICM_BINARY"

**Example**  
```json
{
    "ColourMode": "ICM_COLOUR",
}
```

#### As Struct Member

| Struct | Struct Member Name | Value Type | 
| ------ | ------------------ | ---------- |
| DCN_RuntimeSettings->normalizationSettings | colourMode | [`ImageColourMode`]({{ site.enumerations }}image-colour-mode.html) |

**Value Range**  
    Any one of the ImageColourMode items.

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

## ContentLocalization
The localization of content to be normalized.

### Arguments
- [`Mode`](#mode)
- [`FirstPoint`](#firstpoint)
- [`SecondPoint`](#secondpoint)
- [`ThirdPoint`](#thirdpoint)
- [`FourthPoint`](#fourthpoint)

#### Mode

| Argument Name | Value Type | 
| ------------- | ---------- |
| Mode | *string* |

#### FirstPoint

| Argument Name | Valid for Modes | Value Type | 
| ------------- | ----------- | ---------- |
| FirstPoint | `CBLM_MANNUAL_SPECIFICATION` | *int array* |

#### SecondPoint

| Argument Name | Valid for Modes | Value Type | 
| ------------- | ----------- | ---------- |
| SecondPoint | `CBLM_MANNUAL_SPECIFICATION` | *int array* |

#### ThirdPoint

| Argument Name | Valid for Modes | Value Type | 
| ------------- | ----------- | ---------- |
| ThirdPoint | `CBLM_MANNUAL_SPECIFICATION` | *int array* |

#### FourthPoint

| Argument Name | Valid for Modes | Value Type | 
| ------------- | ----------- | ---------- |
| FourthPoint | `CBLM_MANNUAL_SPECIFICATION` | *int array* |

### Setting Methods
#### As Json Parameter

| Parent Json Object | Json Parameter Name | Value Type | 
| ------------------ | ------------------- | ---------- |
| NormalizationDefinition | ContentLocalization | *JSON Object* |

**Value Range**  
    Any one of the ImageColourMode items.

**Default Value**  
    "ICM_BINARY"

**Example**  
```json
{
    "ColourMode": "ICM_COLOUR",
}
```

#### As Struct Member

| Struct | Struct Member Name | Value Type | 
| ------ | ------------------ | ---------- |
| DCN_RuntimeSettings->normalizationSettings | colourMode | [`ImageColourMode`]({{ site.enumerations }}image-colour-mode.html) |

**Value Range**  
    Any one of the ImageColourMode items.

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

## ContentType

## Contrast

## EnableDeskewing

## EnablePerspectiveCorrection

## Name