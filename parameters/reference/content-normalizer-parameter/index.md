---
title: Dynamsoft Content Normalizer - ContentNormalizerParameter Object
keywords: parameters, reference, dcn, documentation
description: Dynamsoft Content Normalizer - ContentNormalizerParameter Object
---


# ContentNormalizerParameter Object

## BinarizationModes

## ColourConversionModes

## ExecutePhases

## GrayscaleEnhancementModes

## GrayscaleTransformationModes

## InteriorAngleRange
Sets the quadrilateral interior angle range.

### Setting Methods
#### As Json Parameter

| Parent Json Object | Json Parameter Name | Value Type | 
| ------------------ | ------------------- | ---------- |
| ContentNormalizerParameter | InteriorAngleRange | *int array* |

**Value Range**    
    Format: [`minInteriorAngleValue`, `maxInteriorAngleValue`]    
    Allowed value range:   
        &emsp;&emsp;For `minInteriorAngleValue` / `maxInteriorAngleValue`: [0, 180]  

**Default Value**   
    [70, 110]

**Example**  
```json
{
    "InteriorAngleRange": [60, 120],
}
```

#### As Struct Member

| Struct | Struct Member Name | Value Type | 
| ------ | ------------------ | ---------- |
| DCN_RuntimeSettings | interiorAngleRange | *int array* |

**Value Range**    
    Format: [`minInteriorAngleValue`, `maxInteriorAngleValue`]    
    Allowed value range:   
        &emsp;&emsp;For `minInteriorAngleValue` / `maxInteriorAngleValue`: [0, 180]  

**Default Value**   
    [70, 110]

**Code Snippet**  
```cpp
// This is a c++ sample code.
ContentNormalizer::InitLicense("t0260NwAAAHV***************");
ContentNormalizer* normalizer = new ContentNormalizer();
DCN_RuntimeSettings settings;
int errorCode = normalizer->GetRuntimeSettings(&settings);
settings->interiorAngleRange[0] = 60;
settings->interiorAngleRange[1] = 120;
char errorMessage[256];
errorCode = normalizer->UpdateRuntimeSettings(&settings, errorMessage, 256);
delete normalizer;
```


## MaxThreadCount

## MinimalHorizontalSideLength
Sets the minimal horizontal side length of the quadrilateral. 

### Setting Methods
#### As Json Parameter

| Parent Json Object | Json Parameter Name | Value Type | 
| ------------------ | ------------------- | ---------- |
| ContentNormalizerParameter | MinimalHorizontalSideLength | *int array* |

**Value Range**    
    Format: [`minimalSideLength`, `ByPercentage`]    
    Allowed value range:   
        &emsp;&emsp;For `minimalSideLength`: `ByPercentage`=0: [1, 0x7fffffff], `ByPercentage`=1: [1, 100]   
        &emsp;&emsp;For `ByPercentage`: [0, 1]   

**Default Value**   
    [15, 1]

**Example**  
```json
{
    "MinimalHorizontalSideLength": [200, 0],
}
```

#### As Struct Member

| Struct | Struct Member Name | Value Type | 
| ------ | ------------------ | ---------- |
| DCN_RuntimeSettings | minimalHorizontalSideLength | *int array* |

**Value Range**    
    Format: [`minimalSideLength`, `ByPercentage`]    
    Allowed value range:   
        &emsp;&emsp;For `minimalSideLength`: `ByPercentage`=0: [1, 0x7fffffff], `ByPercentage`=1: [1, 100]   
        &emsp;&emsp;For `ByPercentage`: [0, 1]   

**Default Value**   
    [15, 1]

**Code Snippet**  
```cpp
// This is a c++ sample code.
ContentNormalizer::InitLicense("t0260NwAAAHV***************");
ContentNormalizer* normalizer = new ContentNormalizer();
DCN_RuntimeSettings settings;
int errorCode = normalizer->GetRuntimeSettings(&settings);
settings->minimalHorizontalSideLength[0] = 200;
settings->minimalHorizontalSideLength[1] = 0;
char errorMessage[256];
errorCode = normalizer->UpdateRuntimeSettings(&settings, errorMessage, 256);
delete normalizer;
```

## MinimalVerticalSideLength
Sets the minimal vertical side length of the quadrilateral. 

### Setting Methods
#### As Json Parameter

| Parent Json Object | Json Parameter Name | Value Type | 
| ------------------ | ------------------- | ---------- |
| ContentNormalizerParameter | MinimalVerticalSideLength | *int array* |

**Value Range**    
    Format: [`minimalSideLength`, `ByPercentage`]    
    Allowed value range:   
        &emsp;&emsp;For `minimalSideLength`: `ByPercentage`=0: [1, 0x7fffffff], `ByPercentage`=1: [1, 100]   
        &emsp;&emsp;For `ByPercentage`: [0, 1]   

**Default Value**   
    [15, 1]

**Example**  
```json
{
    "MinimalVerticalSideLength": [200, 0],
}
```

#### As Struct Member

| Struct | Struct Member Name | Value Type | 
| ------ | ------------------ | ---------- |
| DCN_RuntimeSettings | minimalVerticalSideLength | *int array* |

**Value Range**    
    Format: [`minimalSideLength`, `ByPercentage`]    
    Allowed value range:   
        &emsp;&emsp;For `minimalSideLength`: `ByPercentage`=0: [1, 0x7fffffff], `ByPercentage`=1: [1, 100]   
        &emsp;&emsp;For `ByPercentage`: [0, 1]   

**Default Value**   
    [15, 1]

**Code Snippet**  
```cpp
// This is a c++ sample code.
ContentNormalizer::InitLicense("t0260NwAAAHV***************");
ContentNormalizer* normalizer = new ContentNormalizer();
DCN_RuntimeSettings settings;
int errorCode = normalizer->GetRuntimeSettings(&settings);
settings->minimalVerticalSideLength[0] = 200;
settings->minimalVerticalSideLength[1] = 0;
char errorMessage[256];
errorCode = normalizer->UpdateRuntimeSettings(&settings, errorMessage, 256);
delete normalizer;
```

## Name
Sets the unique name of the ContentNormalizerParameter object.

### Setting Methods
#### As Json Parameter

| Parent Json Object | Json Parameter Name | Value Type | 
| ------------------ | ------------------- | ---------- |
| ContentNormalizerParameter | Name | *string* |

**Value Range**  
    Any unique string.

**Example**  
```json
{
    "Name": "CN_1",
}
```

**Remarks**   
    It must be a unique name.

## NormalizationDefinitionName

## QuadrilateralDetectionModes

## ScaleDownThreshold

## TextureDetectionModes

## Timeout
