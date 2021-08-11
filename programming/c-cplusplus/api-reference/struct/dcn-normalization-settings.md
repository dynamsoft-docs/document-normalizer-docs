---
title: Dynamsoft Content Normalizer - DCN_NormalizationSettings Struct
keywords: dcn_normalizationsettings, struct, api, api reference, c, c language, c++, cplusplus, dcn, documentation
description: Dynamsoft Content Normalizer - DCN_NormalizationSettings Struct
---


# DCN_NormalizationSettings
Defines a struct to configure the normalization settings.

```cpp
typedef struct tagDCNNormalizationSettings  DCN_NormalizationSettings
```  

## Attributes
  
| Attribute | Type |
|---------- | ---- |
| [`contentType`](#contenttype) | [`ContentType`]({{ site.enumerations }}content-type.html) |
| [`localizationMode`](#localizationmode) | [`ContentBoundaryLocalizationMode`]({{ site.enumerations }}content-boundary-localization-mode.html) |
| [`contentBoundaryQuad`](#contentboundaryquad) | [`Quadrilateral`]({{ site.c_cpp_common_struct}}quadrilateral.html) |
| [`targetContentPageSize`](#targetcontentpagesize) | *int\[2\]* |
| [`enablePerspectiveCorrenction`](#enableperspectivecorrenction) | *int* |
| [`enableDeskewing`](#enabledeskewing) | *int* |
| [`colourMode`](#colourmode) | [`ImageColourMode`]({{ site.enumerations }}image-colour-mode.html) |
| [`contrast`](#contrast) | *int* |
| [`brightness`](#brightness) | *int* |
| [`reserved`](#reserved) | *char\[64\]* |


&nbsp;

### contentType
Sets the content type to normalize.
```cpp
ContentType contentType
```
- **Value range**   
    The value can be any one of the [`ContentType`]({{ site.enumerations }}content-type.html) Enumeration items.
      
- **Default value**   
    CT_DOCUMENT
    

&nbsp;

### localizationMode
Sets the content boundary localization mode.
```cpp
ContentBoundaryLocalizationMode localizationMode
```

- **Value range**   
    The value can be any one of the [`ContentBoundaryLocalizationMode`]({{ site.enumerations }}content-boundary-localization-mode.html) Enumeration items.
      
- **Default value**   
    CBLM_AUTO_DETECTION

&nbsp;

### contentBoundaryQuad
Stores the content boundary quadrilateral.
```cpp
Quadrilateral contentBoundaryQuad
```

&nbsp;

### targetContentPageSize
Sets the target content page size (width x height in millimeters).
```cpp
int targetContentPageSize[2]
```

- **Value range**   
    Format: [`targetPageWidth`, `targetPageHeight`]    
    Allowed value range:   
        &emsp;&emsp;For `targetPageWidth` / `targetPageHeight`: [-1, 0x7fffffff] 
      
- **Default value**   
    [-1, -1]

&nbsp;


### enablePerspectiveCorrenction
Sets enable perspective correction or not.
```cpp
int enablePerspectiveCorrenction
```
- **Value range**   
    [0, 1]
      
- **Default value**   
    1

&nbsp;


### enableDeskewing
Sets enable de-skewing or not.
```cpp
int enableDeskewing
```
- **Value range**   
    [0, 1]
      
- **Default value**   
    1

&nbsp;

### colourMode
Sets the target colour mode for normalized image
```cpp
ImageColourMode colourMode
```
- **Value range**   
    The value can be any one of the [`ImageColourMode`]({{ site.enumerations }}image-colour-mode.html) Enumeration items.
      
- **Default value**   
    ICM_BINARY
    
&nbsp;

### contrast
Sets the contrast value for the normalized image.
```cpp
int contrast
```
- **Value range**   
    [-100, 100]
      
- **Default value**   
    0
    
&nbsp;

### brightness
Sets the brightness value for the normalized image.
```cpp
int brightness
```
- **Value range**   
    [-100, 100]
      
- **Default value**   
    0
    
&nbsp;

### reserved
Reserved memory for struct. The length of this array indicates the size of the memory reserved for this struct.
```cpp
char reserved[64]
```
