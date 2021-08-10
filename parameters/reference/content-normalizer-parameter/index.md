---
title: Dynamsoft Content Normalizer - ContentNormalizerParameter Object
keywords: parameters, reference, dcn, documentation
description: Dynamsoft Content Normalizer - ContentNormalizerParameter Object
---


# ContentNormalizerParameter Object

## BinarizationModes
Sets the mode array for binarization. 

### Arguments
- [`Mode`](#mode)
- [`BinarizationThreshold`](#binarizationthreshold)
- [`BlockSizeX`](#blocksizex)
- [`BlockSizeY`](#blocksizey)
- [`EnableFillBinaryVacancy`](#enablefillbinaryvacancy)
- [`MorphOperation`](#morphoperation)
- [`MorphShape`](#morphshape)
- [`MorphOperationKernelSizeX`](#morphoperationkernelsizex)
- [`MorphOperationKernelSizeY`](#morphoperationkernelsizey)
- [`ThresholdCompensation`](#thresholdcompensation)

#### Mode

| Argument Name | Value Type | 
| ------------- | ---------- |
| Mode | *string* |

**Value Range**   
    Any one of the [`BinarizationMode`]({{ site.common_enumerations }}binarization-mode.html) items.

**Default Value**   
    "BM_LOCAL_BLOCK"


#### BinarizationThreshold

| Argument Name| Valid for Mode(s) | Value Type|
| ------------ | ----------------- | --------- |
| BinarizationThreshold | `BM_THRESHOLD` | *int* |

**Value Range**    
    [-1, 255]

**Default Value**   
    -1

#### BlockSizeX

| Argument Name| Valid for Mode(s) | Value Type|
| ------------ | ----------------- | --------- |
| BlockSizeX | `BM_LOCAL_BLOCK` | *int* |

**Value Range**    
    [0, 1000]

**Default Value**   
    0

#### BlockSizeY

| Argument Name| Valid for Mode(s) | Value Type|
| ------------ | ----------------- | --------- |
| BlockSizeY | `BM_LOCAL_BLOCK` | *int* |

**Value Range**    
    [0, 1000]

**Default Value**   
    0

#### EnableFillBinaryVacancy

| Argument Name| Valid for Mode(s) | Value Type|
| ------------ | ----------------- | --------- |
| EnableFillBinaryVacancy | `BM_LOCAL_BLOCK` | *int* |

**Value Range**    
    [0, 1]

**Default Value**   
    1

#### MorphOperation

| Argument Name| Valid for Mode(s) | Value Type|
| ------------ | ----------------- | --------- |
| MorphOperation | `BM_LOCAL_BLOCK`<br>`BM_THRESHOLD` | *string* |

**Value Range**   
    "Erode"  
    "Dilate"  
    "Open"  
    "Close"

**Default Value**   
    "Close"

**Remarks**
- "Erode": Perform erosion process.
- "Dilate": Perform dilation process.
- "Open": Perform erosion first, then perform dilation.
- "Close": Perform dilation first, then perform erosion.

For more information, please check out [Image Processing in OpenCV - Morphological Transformations](https://docs.opencv.org/master/d9/d61/tutorial_py_morphological_ops.html) for reference.

#### MorphOperation

| Argument Name| Valid for Mode(s) | Value Type|
| ------------ | ----------------- | --------- |
| MorphOperation | `BM_LOCAL_BLOCK`<br>`BM_THRESHOLD` | *string* |

**Value Range**   
    "Rectangle"  
    "Cross"  
    "Ellipse"  

**Default Value**   
    "Rectangle"

#### MorphOperationKernelSizeX

| Argument Name| Valid for Mode(s) | Value Type|
| ------------ | ----------------- | --------- |
| MorphOperationKernelSizeX | `BM_LOCAL_BLOCK`<br>`BM_THRESHOLD` | *int* |

**Value Range**    
    [-1, 1000]

**Default Value**   
    -1

#### MorphOperationKernelSizeY

| Argument Name| Valid for Mode(s) | Value Type|
| ------------ | ----------------- | --------- |
| MorphOperationKernelSizeY | `BM_LOCAL_BLOCK`<br>`BM_THRESHOLD` | *int* |

**Value Range**    
    [-1, 1000]

**Default Value**   
    -1

#### ThresholdCompensation

| Argument Name| Valid for Mode(s) | Value Type|
| ------------ | ----------------- | --------- |
| ThresholdCompensation | `BM_LOCAL_BLOCK` | *int* |

**Value Range**    
    [-255, 255]

**Default Value**   
    -10

### Setting Methods
#### As Json Parameter

| Parent Json Object | Json Parameter Name | Value Type | 
| ------------------ | ------------------- | ---------- |
| ContentNormalizerParameter | BinarizationModes | *JSON object array* |

**Default Setting**   
```json
{
    "BinarizationModes":[
        {
            "Mode": "BM_LOCAL_BLOCK"
        }
    ],
}
```

**Example**  
```json
{
    "BinarizationModes": [
    {
        "Mode": "BM_LOCAL_BLOCK",
        "BlockSizeX": 51,
        "BlockSizeY": 51,
        "EnableFillBinaryVacancy": 0
    },
    {
        "Mode": "BM_THRESHOLD",
        "BinarizationThreshold": 120, 
        "MorphOperation": "Close",
        "MorphShape": "Rectangle",
        "MorphOperationKernelSizeX": 3,
        "MorphOperationKernelSizeY": 3
    }
    ]
}
```

#### As Struct Member

| Struct | Struct Member Name | Value Type | 
| ------ | ------------------ | ---------- |
| DCN_RuntimeSettings | binarizationModes | [`QuadrilateralDetectionMode`]({{ site.enumerations }}quadrilateral-detection-mode.html) array |

**Value Range**    
    Each array item can be any one of the [`BinarizationMode`]({{ site.common_enumerations }}binarization-mode.html) Enumeration items.

**Default Value**   
    [BM_LOCAL_BLOCK,BM_SKIP,BM_SKIP,BM_SKIP,BM_SKIP,BM_SKIP,BM_SKIP,BM_SKIP]

**Code Snippet**  
```cpp
// This is a c++ sample code.
ContentNormalizer::InitLicense("t0260NwAAAHV***************");
ContentNormalizer* normalizer = new ContentNormalizer();
DCN_RuntimeSettings settings;
int errorCode = normalizer->GetRuntimeSettings(&settings);
settings->binarizationModes[0] = BM_LOCAL_BLOCK;
settings->binarizationModes[1] = BM_THRESHOLD;
char errorMessage[256];
errorCode = normalizer->UpdateRuntimeSettings(&settings, errorMessage, 256);
delete normalizer;
```

## ColourConversionModes

## ExecutePhases
Sets the string array for specifying the phase(s) to be executed.

### Setting Methods
#### As Json Parameter

| Parent Json Object | Json Parameter Name | Value Type | 
| ------------------ | ------------------- | ---------- |
| ContentNormalizerParameter | ExecutePhases | *string array* |

**Value Range**    
    An array item can be any one of the [`ExecutePhase`]({{ site.enumerations }}execute-phase.html) Enumeration items.

**Default Value**   
    ["EP_ALL"]

**Example**  
```json
{
    "ExecutePhases": ["EP_QUAD_DETECTION", "EP_BASIC_NORMALIZATION"],
}
```

#### As Struct Member

| Struct | Struct Member Name | Value Type | 
| ------ | ------------------ | ---------- |
| DCN_RuntimeSettings | executePhases | *int* |

**Value Range**    
    A combined value of [`ExecutePhase`]({{ site.enumerations }}execute-phase.html) Enumeration items.

**Default Value**   
    EP_ALL

**Code Snippet**  
```cpp
// This is a c++ sample code.
ContentNormalizer::InitLicense("t0260NwAAAHV***************");
ContentNormalizer* normalizer = new ContentNormalizer();
DCN_RuntimeSettings settings;
int errorCode = normalizer->GetRuntimeSettings(&settings);
settings->executePhases = EP_QUAD_DETECTION | EP_BASIC_NORMALIZATION;
char errorMessage[256];
errorCode = normalizer->UpdateRuntimeSettings(&settings, errorMessage, 256);
delete normalizer;
```


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
Sets the maximum number of threads the algorithm will use to normalize content.

### Setting Methods
#### As Json Parameter

| Parent Json Object | Json Parameter Name | Value Type | 
| ------------------ | ------------------- | ---------- |
| ContentNormalizerParameter | MaxThreadCount | *int* |

**Value Range**  
    [1, 4]

**Default Value**  
    4

**Example**  
```json
{
    "MaxThreadCount": 4,
}
```

#### As Struct Member

| Struct | Struct Member Name | Value Type | 
| ------ | ------------------ | ---------- |
| DCN_RuntimeSettings | maxThreadCout | *int* |

**Value Range**  
    [1, 4]

**Default Value**  
    4

**Code Snippet**  
```cpp
// This is a c++ sample code.
ContentNormalizer::InitLicense("t0260NwAAAHV***************");
ContentNormalizer* normalizer = new ContentNormalizer();
DCN_RuntimeSettings settings;
int errorCode = normalizer->GetRuntimeSettings(&settings);
settings->maxThreadCout = 1;
char errorMessage[256];
errorCode = normalizer->UpdateRuntimeSettings(&settings, errorMessage, 256);
delete normalizer;
```

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
Sets the name of a NormalizationDefinition Object. 

### Setting Methods
#### As Json Parameter

| Parent Json Object | Json Parameter Name | Value Type | 
| ------------------ | ------------------- | ---------- |
| ContentNormalizerParameter | NormalizationDefinitionName | *string* |

**Value Range**  
    Any defined NormalizationDefinition object name.

**Example**  
```json
{
    "NormalizationDefinitionName": "ND_1",
}
```

**Remarks**   
    The NormalizationDefinition with specified object name must be defined.

## QuadrilateralDetectionModes
Sets the mode array for quadrilateral detection.

### Arguments
- [`Mode`](#mode)

#### Mode
| Argument Name | Value Type | 
| ------------- | ---------- |
| Mode | *string* |

**Value Range**   
    Any one of the [`QuadrilateralDetectionMode`]({{ site.enumerations }}quadrilateral-detection-mode.html) items.

**Default Value**   
    "QDM_LINE_BASED_DETECTION"

### Setting Methods
#### As Json Parameter

| Parent Json Object | Json Parameter Name | Value Type | 
| ------------------ | ------------------- | ---------- |
| ContentNormalizerParameter | QuadrilateralDetectionModes | *JSON object array* |

**Default Setting**   
```json
{
    "QuadrilateralDetectionModes":[
        {
            "Mode": "QDM_LINE_BASED_DETECTION"
        }
    ],
}
```

**Example**  
```json
{
    "QuadrilateralDetectionModes":[
        {
            "Mode": "QDM_MARGIN_BASED_DETECTION"
        },
        {
            "Mode": "QDM_LINE_BASED_DETECTION"
        }
    ],
}
```

#### As Struct Member

| Struct | Struct Member Name | Value Type | 
| ------ | ------------------ | ---------- |
| DCN_RuntimeSettings | detectionModes | [`QuadrilateralDetectionMode`]({{ site.enumerations }}quadrilateral-detection-mode.html) array |

**Value Range**    
    Each array item can be any one of the [`QuadrilateralDetectionMode`]({{ site.enumerations }}quadrilateral-detection-mode.html) Enumeration items.

**Default Value**   
    [QDM_LINE_BASED_DETECTION,QDM_SKIP_DETECTION,QDM_SKIP_DETECTION,QDM_SKIP_DETECTION,QDM_SKIP_DETECTION,QDM_SKIP_DETECTION,QDM_SKIP_DETECTION,QDM_SKIP_DETECTION]

**Code Snippet**  
```cpp
// This is a c++ sample code.
ContentNormalizer::InitLicense("t0260NwAAAHV***************");
ContentNormalizer* normalizer = new ContentNormalizer();
DCN_RuntimeSettings settings;
int errorCode = normalizer->GetRuntimeSettings(&settings);
settings->detectionModes[0] = QDM_MARGIN_BASED_DETECTION;
settings->detectionModes[1] = QDM_LINE_BASED_DETECTION;
char errorMessage[256];
errorCode = normalizer->UpdateRuntimeSettings(&settings, errorMessage, 256);
delete normalizer;
```

## ScaleDownThreshold
Sets the threshold for the image shrinking.

**Remarks**   
If the shorter edge size is larger than the given value, the library will calculate the required height and width and shrink the image to that size before normalization. Otherwise, it will perform content normalization on the original image.

### Setting Methods
#### As Json Parameter

| Parent Json Object | Json Parameter Name | Value Type | 
| ------------------ | ------------------- | ---------- |
| ContentNormalizerParameter | ScaleDownThreshold | *int* |

**Value Range**  
    [512, 0x7fffffff]

**Default Value**  
    2048

**Example**  
```json
{
    "ScaleDownThreshold": 4096,
}
```

#### As Struct Member

| Struct | Struct Member Name | Value Type | 
| ------ | ------------------ | ---------- |
| DCN_RuntimeSettings | scaleDownThreshold | *int* |

**Value Range**  
    [512, 0x7fffffff]

**Default Value**  
    2048

**Code Snippet**  
```cpp
// This is a c++ sample code.
ContentNormalizer::InitLicense("t0260NwAAAHV***************");
ContentNormalizer* normalizer = new ContentNormalizer();
DCN_RuntimeSettings settings;
int errorCode = normalizer->GetRuntimeSettings(&settings);
settings->scaleDownThreshold = 4096;
char errorMessage[256];
errorCode = normalizer->UpdateRuntimeSettings(&settings, errorMessage, 256);
delete normalizer;
```

## TextureDetectionModes

## Timeout
Sets the maximum amount of time (in milliseconds) should be spent on normalizing the content per page. 

**Remarks**   
It does not include the time taken to load/decode an image (Tiff, PNG, etc.) from disk into memory.   

### Setting Methods
#### As Json Parameter

| Parent Json Object | Json Parameter Name | Value Type | 
| ------------------ | ------------------- | ---------- |
| ContentNormalizerParameter | Timeout | *int* |

**Value Range**  
    [0, 0x7fffffff]

**Default Value**  
    10000

**Example**  
```json
{
    "Timeout": 20000,
}
```

#### As Struct Member

| Struct | Struct Member Name | Value Type | 
| ------ | ------------------ | ---------- |
| DCN_RuntimeSettings | timeout | *int* |

**Value Range**  
    [0, 0x7fffffff]

**Default Value**  
    10000

**Code Snippet**  
```cpp
// This is a c++ sample code.
ContentNormalizer::InitLicense("t0260NwAAAHV***************");
ContentNormalizer* normalizer = new ContentNormalizer();
DCN_RuntimeSettings settings;
int errorCode = normalizer->GetRuntimeSettings(&settings);
settings->timeout = 20000;
char errorMessage[256];
errorCode = normalizer->UpdateRuntimeSettings(&settings, errorMessage, 256);
delete normalizer;
```
