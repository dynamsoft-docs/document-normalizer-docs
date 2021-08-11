---
title: Dynamsoft Content Normalizer - DCN_FurtherModes Struct
keywords: dcn_furthermodes, struct, api, api reference, c, c language, c++, cplusplus, dcn, documentation
description: Dynamsoft Content Normalizer - DCN_FurtherModes Struct
---


# DCN_FurtherModes
Defines a struct to configure the further modes for controlling image processing stage in content normalization.

```cpp
typedef struct tagDCNFurtherModes  DCN_FurtherModes
```  

## Attributes
  
| Attribute | Type |
|---------- | ---- |
| [`colourConversionModes`](#colourconversionmodes) | [`ColourConversionMode`]({{ site.common_enumerations }}colour-conversion-mode.html)[8] |
| [`grayscaleEnhancementModes`](#grayscaleenhancementmodes) | [`GrayscaleEnhancementMode`]({{ site.common_enumerations }}grayscale-enhancement-mode.html)[8] |
| [`grayscaleTransformationModes`](#grayscaletransformationmodes) | [`GrayscaleTransformationMode`]({{ site.common_enumerations }}grayscale-transformation-mode.html)[8] |
| [`textureDetectionModes`](#texturedetectionmodes) | [`TextureDetectionMode`]({{ site.common_enumerations }}texture-detection-mode.html)[8] |
| [`reserved`](#reserved) | *char\[128\]* |


&nbsp;

### colourConversionModes
Sets the mode and priority for converting colour image to grayscale image.
```cpp
ColourConversionMode colourConversionModes[8]
```
- **Value range**   
    Each array item can be any one of the [`ColourConversionMode`]({{ site.common_enumerations }}colour-conversion-mode.html) Enumeration items.
      
- **Default value**   
    [CICM_GENERAL,CICM_SKIP,CICM_SKIP,CICM_SKIP,CICM_SKIP,CICM_SKIP,CICM_SKIP,CICM_SKIP]
    
- **Remarks**   
    The array index represents the priority of the item. The smaller index is, the higher priority is.

&nbsp;

### grayscaleEnhancementModes
Sets the mode and priority for enhancing grayscale image.
```cpp
GrayscaleEnhancementMode grayscaleEnhancementModes[8]
```

- **Value range**   
    Each array item can be any one of the [`GrayscaleEnhancementMode`]({{ site.common_enumerations }}grayscale-enhancement-mode.html) Enumeration items.
      
- **Default value**   
    [GEM_GENERAL,GEM_SKIP,GEM_SKIP,GEM_SKIP,GEM_SKIP,GEM_SKIP,GEM_SKIP,GEM_SKIP]
    
- **Remarks**   
    The array index represents the priority of the item. The smaller index is, the higher priority is.

&nbsp;

### grayscaleTransformationModes
Sets the mode and priority for grayscale transformation.
```cpp
GrayscaleTransformationMode grayscaleTransformationModes[8]
```

- **Value range**   
    Each array item can be any one of the [`GrayscaleTransformationMode`]({{ site.common_enumerations }}grayscale-transformation-mode.html) Enumeration items.
      
- **Default value**   
    [GTM_ORIGINAL,GTM_SKIP,GTM_SKIP,GTM_SKIP,GTM_SKIP,GTM_SKIP,GTM_SKIP,GTM_SKIP]
    
- **Remarks**   
    The array index represents the priority of the item. The smaller index is, the higher priority is.

&nbsp;

### textureDetectionModes
Sets the mode and priority for texture detection.
```cpp
TextureDetectionMode textureDetectionModes[8]
```

- **Value range**   
    Each array item can be any one of the [`TextureDetectionMode`]({{ site.common_enumerations }}texture-detection-mode.html) Enumeration items.
      
- **Default value**   
    [TDM_GENERAL_WIDTH_CONCENTRATION,TDM_SKIP,TDM_SKIP,TDM_SKIP,TDM_SKIP,TDM_SKIP,TDM_SKIP,TDM_SKIP]
    
- **Remarks**   
    The array index represents the priority of the item. The smaller index is, the higher priority is.

&nbsp;


### reserved
Reserved memory for struct. The length of this array indicates the size of the memory reserved for this struct.
```cpp
char reserved[128]
```
