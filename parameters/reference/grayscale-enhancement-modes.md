---
layout: default-layout
title: GrayscaleEnhancementModes
keywords: GrayscaleEnhancementModes, parameters, reference, documentation
description: Dynamsoft Document Normalizer Parameter Reference - GrayscaleEnhancementModes
---

# GrayscaleEnhancementModes

This parameter provides some image processing methods to enhance the quality of the grayscale image. By default, the library does no preprocessing method. Assume your image has distorted features that can be solved by common image processing methods, this parameter may help set the processing mode(s) for getting a higher quality grayscale image.  

It consisits of one or more modes, each mode is a way to implement the preprocessing algorithm.

## Candidate Mode List

- GEM_GENERAL
- GEM_GRAY_EQUALIZE
- GEM_GRAY_SMOOTH
- GEM_SHARPEN_SMOOTH

### GEM_GENERAL

Takes the un-preprocessed grayscale image for following operations.

### GEM_GRAY_EQUALIZE

Preprocesses the grayscale image using the gray equalization algorithm. This mode can be used for images with low contrast on content and background colour. This mode has the following arguments for further customizing.

- [Sensitivity](#sensitivity)

### GEM_GRAY_SMOOTH

Preprocesses the grayscale image using the gray smoothing algorithm. This mode can be used for for images with noise or texture. This mode has the following arguments for further customizing.

- [SmoothBlockSizeX](#smoothblocksizex)
- [SmoothBlockSizeY](#smoothblocksizey)

### GEM_SHARPEN_SMOOTH

Preprocesses the grayscale image using the sharpening and smoothing algorithm. This mode can be used for blur images. This mode has the following arguments for further customizing.

- [SmoothBlockSizeX](#smoothblocksizex)
- [SmoothBlockSizeY](#smoothblocksizey)
- [SharpenBlockSizeX](#sharpenblocksizex)
- [SharpenBlockSizeY](#sharpenblocksizey)
    
## Setting Methods

### As JSON Parameter

`GrayscaleEnhancementModes` as a JSON parameter is a JSON Object array defined as below.

| Parent Json Object | Key Name | Key Value |
| ------------------ | ------------------- | ---------- |
| ImageParameter | GrayscaleEnhancementModes | A JSON Object array while each Object is defined as below |

| Key Name | Key Value | Description |
| -------- | --------- | ----------- |
| Mode | Any one in Candidate Mode List as string | (Required) Sets a preprocessing mode.  |
| Sensitivity | A number from value range of Sensitivity | (Optional) Sets the Argument [Sensitivity](#sensitivity). |
| SmoothBlockSizeX | A number from value range of SmoothBlockSizeX | (Optional) Sets the Argument [SmoothBlockSizeX](#smoothblocksizex). |
| SmoothBlockSizeY | A number from value range of SmoothBlockSizeY | (Optional) Sets the Argument [SmoothBlockSizeY](#smoothblocksizey). |
| SharpenBlockSizeX | A number from value range of SharpenBlockSizeX | (Optional) Sets the Argument [SmoothBlockSizeX](#sharpenblocksizex). |
| SharpenBlockSizeY | A number from value range of SharpenBlockSizeY | (Optional) Sets the Argument [SmoothBlockSizeY](#sharpenblocksizey). |

**Default Value**

```json
{
    "GrayscaleEnhancementModes": [
        {
            "Mode": "GEM_GENERAL" 
        }
    ]
}
```

**JSON Parameter Example**

```json
{
    "GrayscaleEnhancementModes": [
        {
            "Mode": "GEM_GRAY_SMOOTH", 
            "SmoothBlockSizeX": 5,
            "SmoothBlockSizeY": 5
        },
        {
            "Mode": "GEM_GRAY_EQUALIZE", 
            "Sensitivity": 1
        }
    ]
}
```

## Candidate Argument List

- [Sensitivity](#sensitivity)
- [SmoothBlockSizeX](#smoothblocksizex)
- [SmoothBlockSizeY](#smoothblocksizey)
- [SharpenBlockSizeX](#sharpenblocksizex)
- [SharpenBlockSizeY](#sharpenblocksizey)

### Sensitivity

Sets the sensitivity to perform the equalization process. A larger value means a higher possibility that gray equalization will be activated.

| Value Type | Value Range | Default Value | Valid For |
| ---------- | ----------- | ------------- | --------- |
| *int* | [1, 9] | 5 | GEM_GRAY_EQUALIZE |

### SmoothBlockSizeX

Sets the horizontal block size(neighborhood pixel counts) for the smoothing process.

| Value Type | Value Range | Default Value | Valid For |
| ---------- | ----------- | ------------- | --------- |
| *int* | [3, 1000] | 3 | GEM_GRAY_SMOOTH<br>GEM_SHARPEN_SMOOTH |

### SmoothBlockSizeY

Sets the vertical block size(neighborhood pixel counts) for the smoothing process.

| Value Type | Value Range | Default Value | Valid For |
| ---------- | ----------- | ------------- | --------- |
| *int* | [3, 1000] | 3 | GEM_GRAY_SMOOTH<br>GEM_SHARPEN_SMOOT |

### SharpenBlockSizeX

Sets the horizontal block size(neighborhood pixel counts) for the sharpening process.

| Value Type | Value Range | Default Value |
| ---------- | ----------- | ------------- |
| *int* | [3, 1000] | 3 | GEM_SHARPEN_SMOOTH |

### SharpenBlockSizeY

Sets the vertical block size(neighborhood pixel counts) for the sharpening process.

| Value Type | Value Range | Default Value | Valid For |
| ---------- | ----------- | ------------- | --------- |
| *int* | [3, 1000] | 3 | GEM_SHARPEN_SMOOTH |
