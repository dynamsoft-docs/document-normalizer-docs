---
title: Dynamsoft Content Normalizer - DCN_Result Struct
keywords: dcn_result, struct, api, api reference, c, c language, c++, cplusplus, dcn, documentation
description: Dynamsoft Content Normalizer - DCN_Result Struct
---


# DCN_Result
Defines a struct to store DCN result.

## Typedefs
```cpp
typedef struct tagDCNResult  DCN_Result
```  
  
---
  

## Attributes
  
| Attribute | Type |
|---------- | ---- |
| [`sourceImage`](#sourceimage) | [`ImageData`]({{ site.c_cpp_common_struct }}image-data.html) |
| [`normalizedImage`](#normalizedimage) | [`ImageData`]({{ site.c_cpp_common_struct }}image-data.html) \* |
| [`sourceImageContentQuad`](#sourceimagecontentquad) | [`Quadrilateral`]({{ site.c_cpp_common_struct }}quadrilateral.html) \* |
| [`normalizedImageContentQuad`](#normalizedimagecontentquad) | [`Quadrilateral`]({{ site.c_cpp_common_struct }}quadrilateral.html) \* |
| [`sourceImageCandidateQuadArray`](#sourceimagecandidatequadarray) | [`Quadrilateral`]({{ site.c_cpp_common_struct }}quadrilateral.html) \*\* |
| [`candidateQuadrilateralCount`](#candidatequadrilateralcount) | *int* |
| [`transformationMatrix`](#transformationmatrix) | *float \[9\]* |
| [`invertedTransformationMatrix`](#invertedtransformationmatrix) | *float \[9\]* |
| [`reserved`](#reserved) | *char \[64\]* |


### sourceImage
The source image buffer pointer.  

```cpp
ImageData* sourceImage
```

- **Default value**   
    NULL

&nbsp;


### normalizedImage
The normalized image buffer pointer.

```cpp
ImageData* normalizedImage
```

- **Default value**   
    NULL

&nbsp;


### sourceImageContentQuad
The content quadrilateral struct pointer in the source image.

```cpp
Quadrilateral* sourceImageContentQuad
```

- **Default value**   
    NULL

&nbsp;


### normalizedImageContentQuad
The content quadrilateral struct pointer in the normalized image.

```cpp
Quadrilateral* normalizedImageContentQuad
```

- **Default value**   
    NULL

&nbsp;


### sourceImageCandidateQuadArray
The detected candidate quadrilateral array pointer in the source image.

```cpp
Quadrilateral** sourceImageCandidateQuadArray
```

- **Default value**   
    NULL

&nbsp;


### candidateQuadrilateralCount
The detected candidate quadrilateral count.

```cpp
int candidateQuadrilateralCount
```

- **Default value**   
    0

&nbsp;


### transformationMatrix
The transformation matrix for transforming coordinates in the source image to the normalized image. 

```cpp
float transformationMatrix[9]
```

- **Default value**   
    NULL

&nbsp;


### invertedTransformationMatrix
The inverted transformation matrix for transforming coordinates in the normalized image to the source image.

```cpp
float invertedTransformationMatrix[9]
```

- **Default value**   
    NULL

&nbsp;


### reserved
Reserved memory for struct. The length of this array indicates the size of the memory reserved for this struct.
```cpp
char reserved[64]
```
