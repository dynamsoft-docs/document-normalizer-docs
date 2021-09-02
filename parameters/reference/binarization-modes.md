---
title: Dynamsoft Document Normalizer Parameter Reference - BinarizationModes
keywords: binarizationmodes, parameters, reference, ddn, documentation
description: Dynamsoft Document Normalizer Parameter Reference - BinarizationModes
needGenerateH3Content: true
---


# BinarizationModes
Sets the mode array for binarization. 

## Mode Properties

### `BM_LOCAL_BLOCK`
Binarizes the image based on the local block.

#### Valid Argument
- [`BlockSizeX`](#blocksizex)
- [`BlockSizeY`](#blocksizey)
- [`EnableFillBinaryVacancy`](#enablefillbinaryvacancy)
- [`MorphOperation`](#morphoperation)
- [`MorphShape`](#morphshape)
- [`MorphOperationKernelSizeX`](#morphoperationkernelsizex)
- [`MorphOperationKernelSizeY`](#morphoperationkernelsizey)
- [`ThresholdCompensation`](#thresholdcompensation)

### `BM_THRESHOLD`
Binarizes the image based on a given threshold.

#### Valid Argument
- [`BinarizationThreshold`](#binarizationthreshold)
- [`MorphOperation`](#morphoperation)
- [`MorphShape`](#morphshape)
- [`MorphOperationKernelSizeX`](#morphoperationkernelsizex)
- [`MorphOperationKernelSizeY`](#morphoperationkernelsizey)

## Setting Methods
### As Json Parameter

| Parent Json Object | Json Parameter Name | Value Type | 
| ------------------ | ------------------- | ---------- |
| DocumentNormalizerParameter | BinarizationModes | *JSON object array* |

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

### As Struct Member

| Struct | Struct Member Name | Value Type | 
| ------ | ------------------ | ---------- |
| DDN_RuntimeSettings | binarizationModes | [`BinarizationMode`]({{ site.common_enumerations }}binarization-mode.html) array |

**Value Range**    
    Each array item can be any one of the [`BinarizationMode`]({{ site.common_enumerations }}binarization-mode.html) Enumeration items.

**Default Value**   
    [BM_LOCAL_BLOCK,BM_SKIP,BM_SKIP,BM_SKIP,BM_SKIP,BM_SKIP,BM_SKIP,BM_SKIP]

**Code Snippet**  
```cpp
// This is a c++ sample code.
DocumentNormalizer::InitLicense("t0260NwAAAHV***************");
DocumentNormalizer* normalizer = new DocumentNormalizer();
DDN_RuntimeSettings settings;
int errorCode = normalizer->GetRuntimeSettings(&settings);
settings->binarizationModes[0] = BM_LOCAL_BLOCK;
settings->binarizationModes[1] = BM_THRESHOLD;
char errorMessage[256];
errorCode = normalizer->UpdateRuntimeSettings(&settings, errorMessage, 256);
delete normalizer;
```

## Arguments Reference   

- [`BinarizationThreshold`](#binarizationthreshold)
- [`BlockSizeX`](#blocksizex)
- [`BlockSizeY`](#blocksizey)
- [`EnableFillBinaryVacancy`](#enablefillbinaryvacancy)
- [`MorphOperation`](#morphoperation)
- [`MorphShape`](#morphshape)
- [`MorphOperationKernelSizeX`](#morphoperationkernelsizex)
- [`MorphOperationKernelSizeY`](#morphoperationkernelsizey)
- [`ThresholdCompensation`](#thresholdcompensation)


### BinarizationThreshold

| Argument Name| Valid for Mode(s) | Value Type|
| ------------ | ----------------- | --------- |
| BinarizationThreshold | `BM_THRESHOLD` | *int* |

**Value Range**    
    [-1, 255]

**Default Value**   
    -1

### BlockSizeX

| Argument Name| Valid for Mode(s) | Value Type|
| ------------ | ----------------- | --------- |
| BlockSizeX | `BM_LOCAL_BLOCK` | *int* |

**Value Range**    
    [0, 1000]

**Default Value**   
    0

### BlockSizeY

| Argument Name| Valid for Mode(s) | Value Type|
| ------------ | ----------------- | --------- |
| BlockSizeY | `BM_LOCAL_BLOCK` | *int* |

**Value Range**    
    [0, 1000]

**Default Value**   
    0

### EnableFillBinaryVacancy

| Argument Name| Valid for Mode(s) | Value Type|
| ------------ | ----------------- | --------- |
| EnableFillBinaryVacancy | `BM_LOCAL_BLOCK` | *int* |

**Value Range**    
    [0, 1]

**Default Value**   
    1

### MorphOperation

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

### MorphShape

| Argument Name| Valid for Mode(s) | Value Type|
| ------------ | ----------------- | --------- |
| MorphShape | `BM_LOCAL_BLOCK`<br>`BM_THRESHOLD` | *string* |

**Value Range**   
    "Rectangle"  
    "Cross"  
    "Ellipse"  

**Default Value**   
    "Rectangle"

### MorphOperationKernelSizeX

| Argument Name| Valid for Mode(s) | Value Type|
| ------------ | ----------------- | --------- |
| MorphOperationKernelSizeX | `BM_LOCAL_BLOCK`<br>`BM_THRESHOLD` | *int* |

**Value Range**    
    [-1, 1000]

**Default Value**   
    -1

### MorphOperationKernelSizeY

| Argument Name| Valid for Mode(s) | Value Type|
| ------------ | ----------------- | --------- |
| MorphOperationKernelSizeY | `BM_LOCAL_BLOCK`<br>`BM_THRESHOLD` | *int* |

**Value Range**    
    [-1, 1000]

**Default Value**   
    -1

### ThresholdCompensation

| Argument Name| Valid for Mode(s) | Value Type|
| ------------ | ----------------- | --------- |
| ThresholdCompensation | `BM_LOCAL_BLOCK` | *int* |

**Value Range**    
    [-255, 255]

**Default Value**   
    -10
