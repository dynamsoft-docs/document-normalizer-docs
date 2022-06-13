---
layout: default-layout
title: BinarizationModes
keywords: binarizationmodes, parameters, reference, documentation
description: Dynamsoft Document Normalizer Parameter Reference - BinarizationModes
---


# BinarizationModes

This parameter helps control the binarization process, which converts a grayscale image to a binary image, and potentially result in a higher quality binary image. During binarization, the threshold is the key criteria. If a pixel's value is smaller than the threshold, it is set to 0. Otherwise, the pixel value is set to the maximum value (255 in the library). By default, the library automatically calculates the adaptive size of the neighbourhood area and then binarizes the grayscale image with the adaptive threshold based on a small neighbourhood area with an adaptive size around it.

It consists of one or more modes, each mode is a way to implement the binarization.

## Candidate Mode List

- BM_LOCAL_BLOCK
- BM_THRESHOLD

### BM_LOCAL_BLOCK

Binarizes the image for each pixel based on a threshold which is calculated based on a small region around said pixel. This mode has the following arguments for further customization:

- [`BlockSizeX`](#blocksizex)
- [`BlockSizeY`](#blocksizey)
- [`EnableFillBinaryVacancy`](#enablefillbinaryvacancy)
- [`MorphOperation`](#morphoperation)
- [`MorphOperationKernelSizeX`](#morphoperationkernelsizex)
- [`MorphOperationKernelSizeY`](#morphoperationkernelsizey)
- [`MorphShape`](#morphshape)
- [`ThresholdCompensation`](#thresholdcompensation)

### BM_THRESHOLD

Binarizes the image for each pixel based on a unified threshold. If the gray value of the pixel is less than the threshold, it will be black in the binary image, otherwise it will be white. This mode has the following arguments for further customization:

- [`BinarizationThreshold`](#binarizationthreshold)
- [`MorphOperation`](#morphoperation)
- [`MorphOperationKernelSizeX`](#morphoperationkernelsizex)
- [`MorphOperationKernelSizeY`](#morphoperationkernelsizey)
- [`MorphShape`](#morphshape)

## Setting Methods

### As Json Parameter

`BinarizationModes` as a JSON parameter is a JSON Object array defined as below.

| Parent Json Object | Key Name | Key Value |
| ------------------ | ------------------- | ---------- |
| ImageParameter | BinarizationModes | A JSON Object array while each Object is defined as below |

| Key Name | Key Value | Description |
| -------- | --------- | ----------- |
| Mode | Any one in Candidate Mode List as string | (Required) Sets a binarization mode.  |
| BinarizationThreshold | A number from value range of BinarizationThreshold | (Optional) Sets the Argument [BinarizationThreshold](#binarizationthreshold). |
| BlockSizeX | A number from value range of BlockSizeX | (Optional) Sets the Argument [BlockSizeX](#blocksizex). |
| BlockSizeY | A number from value range of BlockSizeY | (Optional) Sets the Argument [BlockSizeY](#blocksizey). |
| EnableFillBinaryVacancy | A number from value range of EnableFillBinaryVacancy | (Optional) Sets the Argument [EnableFillBinaryVacancy](#enablefillbinaryvacancy). |
| MorphOperation | A string from value range of MorphOperation | (Optional) Sets the Argument [MorphOperation](#morphoperation). |
| MorphOperationKernelSizeX | A number from value range of MorphOperationKernelSizeX | (Optional) Sets the Argument [MorphOperationKernelSizeX](#morphoperationkernelsizex). |
| MorphOperationKernelSizeY | A number from value range of MorphOperationKernelSizeY | (Optional) Sets the Argument [MorphOperationKernelSizeY](#morphoperationkernelsizey). |
| MorphShape | A number from value range of MorphShape | (Optional) Sets the Argument [MorphShape](#morphshape). |
| ThresholdCompensation | A number from value range of ThresholdCompensation | (Optional) Sets the Argument [ThresholdCompensation](#thresholdcompensation). |

**Default Value**

```json
{
    "BinarizationModes":[
        {
            "Mode": "BM_LOCAL_BLOCK",
            "BlockSizeX": 0,
            "BlockSizeY": 0,
            "EnableFillBinaryVacancy": 0,
            "MorphOperation": "Close",
            "MorphShape": "Rectangle",
            "MorphOperationKernelSizeX": -1,
            "MorphOperationKernelSizeY": -1,
            "ThresholdCompensation": 10
        }
    ]
}
```

**JSON Parameter Example**

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

## Candidate Argument List

- [`BinarizationThreshold`](#binarizationthreshold)
- [`BlockSizeX`](#blocksizex)
- [`BlockSizeY`](#blocksizey)
- [`EnableFillBinaryVacancy`](#enablefillbinaryvacancy)
- [`MorphOperation`](#morphoperation)
- [`MorphOperationKernelSizeX`](#morphoperationkernelsizex)
- [`MorphOperationKernelSizeY`](#morphoperationkernelsizey)
- [`MorphShape`](#morphshape)
- [`ThresholdCompensation`](#thresholdcompensation)

### BinarizationThreshold

Sets the binarization threshold.

| Value Type | Value Range | Default Value | Valid For |
| ---------- | ----------- | ------------- | --------- |
| *int* | [-1, 255] | -1 | BM_THRESHOLD |

**Remarks**
-1: The value will be set automatically by the SDK.

### BlockSizeX

Sets the horizontal block size for the binarization process.

| Value Type | Value Range | Default Value | Valid For |
| ---------- | ----------- | ------------- | --------- |
| *int* | [0, 1000] | 0 | BM_LOCAL_BLOCK |

**Remarks**
Block size refers to the size of a pixel neighborhood used to calculate a threshold value for the pixel.

- 0: the block size used for binarization will be set to a value which is calculated automatically.
- N:
  - 1 <= N <= 3: the block size used for binarization will be set to 3.
  - N > 3: the block size used for binarization will be set to N.

### BlockSizeY

Sets the vertical block size for the binarization process.

| Value Type | Value Range | Default Value | Valid For |
| ---------- | ----------- | ------------- | --------- |
| *int* | [0, 1000] | 0 | BM_LOCAL_BLOCK |

**Remarks**
Block size refers to the size of a pixel neighborhood used to calculate a threshold value for the pixel.

- 0: the block size used for binarization will be set to a value which is calculated automatically.
- N:
  - 1 <= N <= 3: the block size used for binarization will be set to 3.
  - N > 3: the block size used for binarization will be set to N.

### EnableFillBinaryVacancy

Sets whether to enable binary vacancy filling.

| Value Type | Value Range | Default Value | Valid For |
| ---------- | ----------- | ------------- | --------- |
| *int* | [0, 1] | 0 | BM_LOCAL_BLOCK |

**Remarks**

- 0: disable.
- 1: enable.

### MorphOperation

Sets the morph operation for the morphology process.

| Value Type | Value Range | Default Value |
| ---------- | ----------- | ------------- |
| *string* | "Erode"<br>"Dilate"<br>"Open"<br>"Close" | "Close" |

**Remarks**

- "Erode": Perform erosion process.
- "Dilate": Perform dilation process.
- "Open": Perform erosion first, then perform dilation.
- "Close": Perform dilation first, then perform erosion.

For more information, please check out [Image Processing in OpenCV - Morphological Transformations](https://docs.opencv.org/master/d9/d61/tutorial_py_morphological_ops.html) for reference.

### MorphOperationKernelSizeX

Sets the horizontal kernel size for the morphology process.

| Value Type | Value Range | Default Value |
| ---------- | ----------- | ------------- |
| *int* | [-1, 1000]  | -1 |

**Remarks**

- 0: The value will be set automatically by the SDK.
- -1: Skip the morph operation.

### MorphOperationKernelSizeY

 Sets the vertical kernel size for the morphology process.  

| Value Type | Value Range | Default Value |
| ---------- | ----------- | ------------- |
| *int* | [-1, 1000]  | -1 |

**Remarks**

- 0: The value will be set automatically by the SDK.
- -1: Skip the morph operation.

### MorphShape

 Sets the morph shape for the morphology process.  

| Value Type | Value Range | Default Value |
| ---------- | ----------- | ------------- |
| *string* | "Rectangle"<br>"Cross"<br>"Ellipse" | "Rectangle" |

### ThresholdCompensation

Constant subtracted from the mean or weighted mean used for calculating the threshold. Normally, it is positive but may be zero or negative as well.

| Value Type | Value Range | Default Value | Valid For |
| ---------- | ----------- | ------------- | --------- |
| *int* | [-255, 255] and -10000 | 10 | BM_LOCAL_BLOCK |

**Remarks**

- -10000: The library may try multiple values for current process.
