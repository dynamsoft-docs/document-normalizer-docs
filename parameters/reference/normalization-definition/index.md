---
title: Dynamsoft Content Normalizer - NormalizationDefinition Object
keywords: parameters, reference, dcn, documentation
description: Dynamsoft Content Normalizer - NormalizationDefinition Object
needGenerateH3Content: false
---


# NormalizationDefinition Object

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
Sets the target colour mode of the final normalized image.

### Setting Methods
#### As Json Parameter

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

#### As Struct Member

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

## ContentLocalization
Sets the localization of content to be normalized.

### Arguments
- [`SourceType`](#sourcetype)
- [`FirstPoint`](#firstpoint)
- [`SecondPoint`](#secondpoint)
- [`ThirdPoint`](#thirdpoint)
- [`FourthPoint`](#fourthpoint)

#### SourceType

| Argument Name | Value Type | 
| ------------- | ---------- |
| SourceType | *string* |

**Value Range**   
    Any one of the [`ContentBoundaryLocalizationMode`]({{ site.enumerations }}content-boundary-localization-mode.html) items.

**Default Value**   
    "CBLM_AUTO_DETECTION"

#### FirstPoint

| Argument Name | Valid for SourceType(s) | Value Type | 
| ------------- | ----------------------- | ---------- |
| FirstPoint | `CBLM_MANNUAL_SPECIFICATION` | *int array* |

**Value Range**    
    Format: [`x-coordinate`, `y-coordinate`]    
    Allowed value range:   
        &emsp;&emsp;For `x-coordinate` / `y-coordinate`: [-1, 0x7fffffff] 

**Default Value**   
    [-1, -1]

#### SecondPoint

| Argument Name | Valid for SourceType(s) | Value Type | 
| ------------- | ----------------------- | ---------- |
| SecondPoint | `CBLM_MANNUAL_SPECIFICATION` | *int array* |

**Value Range**    
    Format: [`x-coordinate`, `y-coordinate`]    
    Allowed value range:   
        &emsp;&emsp;For `x-coordinate` / `y-coordinate`: [-1, 0x7fffffff] 

**Default Value**   
    [-1, -1]

#### ThirdPoint

| Argument Name | Valid for SourceType(s) | Value Type | 
| ------------- | ----------------------- | ---------- |
| ThirdPoint | `CBLM_MANNUAL_SPECIFICATION` | *int array* |

**Value Range**    
    Format: [`x-coordinate`, `y-coordinate`]    
    Allowed value range:   
        &emsp;&emsp;For `x-coordinate` / `y-coordinate`: [-1, 0x7fffffff] 

**Default Value**   
    [-1, -1]

#### FourthPoint

| Argument Name | Valid for SourceType(s) | Value Type | 
| ------------- | ----------------------- | ---------- |
| FourthPoint | `CBLM_MANNUAL_SPECIFICATION` | *int array* |

**Value Range**    
    Format: [`x-coordinate`, `y-coordinate`]    
    Allowed value range:   
        &emsp;&emsp;For `x-coordinate` / `y-coordinate`: [-1, 0x7fffffff] 

**Default Value**   
    [-1, -1]
    
### Setting Methods
#### As Json Parameter

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

#### As Struct Member

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

## ContentType
Sets the target content type to be normalized.

### Setting Methods
#### As Json Parameter

| Parent Json Object | Json Parameter Name | Value Type | 
| ------------------ | ------------------- | ---------- |
| NormalizationDefinition | ContentType | *string* |

**Value Range**  
    Any one of the [`ContentType`]({{ site.enumerations }}content-type.html) items.

**Default Value**  
    "CT_DOCUMENT"

**Example**  
```json
{
    "ColourMode": "CT_TABLE",
}
```

#### As Struct Member

| Struct | Struct Member Name | Value Type | 
| ------ | ------------------ | ---------- |
| DCN_RuntimeSettings->normalizationSettings | contentType | [`ContentType`]({{ site.enumerations }}content-type.html) |

**Value Range**  
    Any one of the [`ContentType`]({{ site.enumerations }}content-type.html) items.

**Default Value**  
    `CT_DOCUMENT`

**Code Snippet**  
```cpp
// This is a c++ sample code.
ContentNormalizer::InitLicense("t0260NwAAAHV***************");
ContentNormalizer* normalizer = new ContentNormalizer();
DCN_RuntimeSettings settings;
int errorCode = normalizer->GetRuntimeSettings(&settings);
settings->normalizationSettings.contentType = CT_TABLE;
char errorMessage[256];
errorCode = normalizer->UpdateRuntimeSettings(&settings, errorMessage, 256);
delete normalizer;
```

## Contrast
Sets the target contrast value of the final normalized image.

### Setting Methods
#### As Json Parameter

| Parent Json Object | Json Parameter Name | Value Type | 
| ------------------ | ------------------- | ---------- |
| NormalizationDefinition | Contrast | *int* |

**Value Range**  
    [-100, 100]

**Default Value**  
    0

**Example**  
```json
{
    "Contrast": 50,
}
```

#### As Struct Member

| Struct | Struct Member Name | Value Type | 
| ------ | ------------------ | ---------- |
| DCN_RuntimeSettings->normalizationSettings | contrast | *int* |

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
settings->normalizationSettings.contrast = 50;
char errorMessage[256];
errorCode = normalizer->UpdateRuntimeSettings(&settings, errorMessage, 256);
delete normalizer;
```

## EnableDeskewing
Sets enable de-skewing during normalization or not.

### Setting Methods
#### As Json Parameter

| Parent Json Object | Json Parameter Name | Value Type | 
| ------------------ | ------------------- | ---------- |
| NormalizationDefinition | EnableDeskewing | *int* |

**Value Range**  
    [0, 1]

**Default Value**  
    1

**Example**  
```json
{
    "EnableDeskewing": 0,
}
```

#### As Struct Member

| Struct | Struct Member Name | Value Type | 
| ------ | ------------------ | ---------- |
| DCN_RuntimeSettings->normalizationSettings | enableDeskewing | *int* |

**Value Range**  
    [0, 1]

**Default Value**  
    1

**Code Snippet**  
```cpp
// This is a c++ sample code.
ContentNormalizer::InitLicense("t0260NwAAAHV***************");
ContentNormalizer* normalizer = new ContentNormalizer();
DCN_RuntimeSettings settings;
int errorCode = normalizer->GetRuntimeSettings(&settings);
settings->normalizationSettings.enableDeskewing = 0;
char errorMessage[256];
errorCode = normalizer->UpdateRuntimeSettings(&settings, errorMessage, 256);
delete normalizer;
```

## EnablePerspectiveCorrection
Sets enable perspective correction during normalization or not.

### Setting Methods
#### As Json Parameter

| Parent Json Object | Json Parameter Name | Value Type | 
| ------------------ | ------------------- | ---------- |
| NormalizationDefinition | EnablePerspectiveCorrection | *int* |

**Value Range**  
    [0, 1]

**Default Value**  
    1

**Example**  
```json
{
    "EnablePerspectiveCorrection": 0,
}
```

#### As Struct Member

| Struct | Struct Member Name | Value Type | 
| ------ | ------------------ | ---------- |
| DCN_RuntimeSettings->normalizationSettings | enablePerspectiveCorrection | *int* |

**Value Range**  
    [0, 1]

**Default Value**  
    1

**Code Snippet**  
```cpp
// This is a c++ sample code.
ContentNormalizer::InitLicense("t0260NwAAAHV***************");
ContentNormalizer* normalizer = new ContentNormalizer();
DCN_RuntimeSettings settings;
int errorCode = normalizer->GetRuntimeSettings(&settings);
settings->normalizationSettings.enablePerspectiveCorrection = 0;
char errorMessage[256];
errorCode = normalizer->UpdateRuntimeSettings(&settings, errorMessage, 256);
delete normalizer;
```

## Name
Sets the unique name of the NormalizationDefinition object.

### Setting Methods
#### As Json Parameter

| Parent Json Object | Json Parameter Name | Value Type | 
| ------------------ | ------------------- | ---------- |
| NormalizationDefinition | Name | *string* |

**Value Range**  
    Any unique string.

**Example**  
```json
{
    "Name": "ND_1",
}
```

**Remarks**   
    It must be a unique name.

## TargetContentPageSize
Sets the target content page size (width x height in millimeters).

### Setting Methods
#### As Json Parameter

| Parent Json Object | Json Parameter Name | Value Type | 
| ------------------ | ------------------- | ---------- |
| NormalizationDefinition | TargetContentPageSize | *int array* |

**Value Range**    
    Format: [`targetPageWidth`, `targetPageHeight`]    
    Allowed value range:   
        &emsp;&emsp;For `targetPageWidth` / `targetPageHeight`: [-1, 0x7fffffff] 

**Default Value**   
    [-1, -1]

**Example**  
```json
{
    "TargetContentPageSize": [210, 297],
}
```

#### As Struct Member

| Struct | Struct Member Name | Value Type | 
| ------ | ------------------ | ---------- |
| DCN_RuntimeSettings->normalizationSettings | targetContentPageSize | *int array* |

**Value Range**    
    Format: [`targetPageWidth`, `targetPageHeight`]    
    Allowed value range:   
        &emsp;&emsp;For `targetPageWidth` / `targetPageHeight`: [-1, 0x7fffffff] 

**Default Value**   
    [-1, -1]

**Code Snippet**  
```cpp
// This is a c++ sample code.
ContentNormalizer::InitLicense("t0260NwAAAHV***************");
ContentNormalizer* normalizer = new ContentNormalizer();
DCN_RuntimeSettings settings;
int errorCode = normalizer->GetRuntimeSettings(&settings);
settings->normalizationSettings.targetContentPageSize[0] = 210;
settings->normalizationSettings.targetContentPageSize[1] = 297;
char errorMessage[256];
errorCode = normalizer->UpdateRuntimeSettings(&settings, errorMessage, 256);
delete normalizer;
```


