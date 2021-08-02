---
title: Dynamsoft Content Normalizer - DCN_RuntimeSettings Struct
keywords: dcn_runtimesettings, struct, api, api reference, c, c language, c++, cplusplus, dcn, documentation
description: Dynamsoft Content Normalizer - DCN_RuntimeSettings Struct
---


# DCN_RuntimeSettings
Defines a struct to configure the content normalizer runtime settings. These settings control the content normalization process.

## Typedefs

```cpp
typedef struct tagDCNRuntimeSettings  DCN_RuntimeSettings
```  
  
---
  

## Attributes
  
| Attribute | Type |
|---------- | ---- |
| [`timeout`](#timeout) | *int* |
| [`maxThreadCount`](#maxthreadcount) | *int* |
| [`scaleDownThreshold`](#scaledownthreshold) | *int* |
| [`executePhases`](#executephases) | *int* |
| [`binarizationModes`](#binarizationmodes) | [`BinarizationMode`]({{ site.common_enumerations }}binarization-mode.html)[8] |
| [`furtherModes`](#furthermodes) | [`DCN_FurtherModes`](dcn-further-modes.md) |
| [`normalizationSettings`](#normalizationsettings) | [`DCN_NormalizationSettings`](dcn-normalization-settings.md) |
| [`detectionModes`](#detectionmodes) | [`QuadrilateralDetectionMode`]({{ site.enumerations }}quadrilateral-detection-mode.html)[8] |
| [`minHorizontalSideLength`](#minhorizontalsidelength) | *int\[2\]* |
| [`minVerticalSideLength`](#minverticalsidelength) | *int\[2\]* |
| [`interiorAngleRange`](#interioranglerange) | *int\[2\]* |
| [`reserved`](#reserved) | *char\[128\]* |


&nbsp;

### timeout
Sets the maximum amount of time (in milliseconds) should be spent on normalizing the content per page. 
```cpp
int timeout
```
- **Value range**   
    [0, 0x7fffffff]
      
- **Default value**   
    10000
    
- **Remarks**   
    If you want to stop normalizing contents after a certain period of time, you can use this parameter to set a timeout.

&nbsp;

### maxThreadCount
Sets the maximum number of threads the algorithm will use to normalize content.
```cpp
int maxThreadCount
```

- **Value range**   
    [1, 4]
      
- **Default value**   
    4

&nbsp;

### scaleDownThreshold
Sets the threshold for the image shrinking.
```cpp
int scaleDownThreshold
```

- **Value range**   
    [512, 0x7fffffff]
      
- **Default value**   
    2048
    
- **Remarks**   
    If the shorter edge size is larger than the given value, the library will calculate the required height and width and shrink the image to that size before normalization. Otherwise, it will perform content normalization on the original image.

&nbsp;

### executePhases
Sets the phases in [`ExecutePhase`]({{ site.enumerations }}execute-phase.html) to be executed. Phases in [`ExecutePhase`]({{ site.enumerations }}execute-phase.html) can be combined.
```cpp
int executePhases
```

- **Value range**   
    A combined value of [`ExecutePhase`]({{ site.enumerations }}execute-phase.html) Enumeration items.
      
- **Default value**   
    EP_ALL

&nbsp;


### binarizationModes
Sets the mode and priority for binarization.
```cpp
BinarizationMode binarizationModes[8]
```
- **Value range**   
    Each array item can be any one of the [`BinarizationMode`]({{ site.common_enumerations }}binarization-mode.html) Enumeration items.
      
- **Default value**   
    [BM_LOCAL_BLOCK,BM_SKIP,BM_SKIP,BM_SKIP,BM_SKIP,BM_SKIP,BM_SKIP,BM_SKIP]
    
- **Remarks**   
    The array index represents the priority of the item. The smaller index is, the higher priority is.

&nbsp;

### furtherModes
Sets further modes and stores them in a [`DCN_FurtherModes`](dcn-further-modes.md) struct.
```cpp
DCN_FurtherModes furtherModes
```

&nbsp;

### normalizationSettings
Sets the settings configuring the normalization and stores them in a [`DCN_NoramlizationSettings`](dcn-normalization-settings.md) struct.
```cpp
DCN_NoramlizationSettings normalizationSettings
```

&nbsp;

### detectionModes
Sets the mode and priority for detection quadrilaterals.
```cpp
QuadrilateralDetectionMode detectionModes[8]
```
- **Value range**   
    Each array item can be any one of the [`QuadrilateralDetectionMode`]({{ site.enumerations }}quadrilateral-detection-mode.html) Enumeration items.
      
- **Default value**   
    [QDM_LINE_BASED_DETECTION,QDM_SKIP_DETECTION,QDM_SKIP_DETECTION,QDM_SKIP_DETECTION,QDM_SKIP_DETECTION,QDM_SKIP_DETECTION,QDM_SKIP_DETECTION,QDM_SKIP_DETECTION]
    
- **Remarks**   
    The array index represents the priority of the item. The smaller index is, the higher priority is.

&nbsp;


### minHorizontalSideLength
Sets the minimal horizontal side length of the quadrilateral to detect. 
```cpp
int minHorizontalSideLength[2]
```
- **Value range**   
    Format: [`minimalSideLength`, `ByPercentage`]    
    Allowed value range:   
        &emsp;&emsp;For `minimalSideLength`: `ByPercentage`=0: [1, 0x7fffffff], `ByPercentage`=1: [1, 100]   
        &emsp;&emsp;For `ByPercentage`: [0, 1]   
     
      
- **Default value**   
    [15, 1]
    
&nbsp;

### minVerticalSideLength
Sets the minimal vertical side length of the quadrilateral to detect. 
```cpp
int minVerticalSideLength[2]
```
- **Value range**   
    Setting Format: [`minimalSideLength`, `ByPercentage`]    
    Allowed value range:   
        &emsp;&emsp;For `minimalSideLength`: `ByPercentage`=0: [1, 0x7fffffff], `ByPercentage`=1: [1, 100]   
        &emsp;&emsp;For `ByPercentage`: [0, 1]     

- **Default value**   
    [15, 1]
    
&nbsp;

### interiorAngleRange
The quadrilateral interior angle range. 
```cpp
int interiorAngleRange[2]
```
- **Value range**   
    Format: [`minInteriorAngleValue`, `maxInteriorAngleValue`]    
    Allowed value range:   
        &emsp;&emsp;For `minInteriorAngleValue` / `maxInteriorAngleValue`: [0, 180]    

- **Default value**   
    [70, 110]

- **Remarks**   
    A standard rectangle is a quadrilateral with four 90-degree angles.
    
&nbsp;


### reserved
Reserved memory for struct. The length of this array indicates the size of the memory reserved for this struct.
```cpp
char reserved[128]
```
