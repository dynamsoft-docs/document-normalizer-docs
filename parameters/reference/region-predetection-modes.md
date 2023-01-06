---
layout: default-layout
title: RegionPredetectionModes
keywords: RegionPredetectionModes, parameters, reference, documentation
description: Dynamsoft Document Normalizer Parameter Reference - RegionPredetectionModes
---

# RegionPredetectionModes

`RegionPredetectionModes` controls how to find a region of interest (ROI) within the image or frame. It consists of one or more modes, each mode representing a different way to find a region of interest.

## Candidate Mode List

- RPM_AUTO
- RPM_GENERAL
- RPM_GENERAL_RGB_CONTRAST
- RPM_GENERAL_GRAY_CONTRAST
- RPM_GENERAL_HSV_CONTRAST
- RPM_MANUAL_SPECIFICATION

### RPM_AUTO

Lets the library automatically choose an algorithm to detect the region of interest(s).

### RPM_GENERAL

Takes the whole image as a region of interest.

### RPM_GENERAL_RGB_CONTRAST

Detects the ROI using the general algorithm based on RGB colour contrast. This mode has the following arguments for further customization.

- [ImageParameterName](#imageparametername)
- [MinImageDimension](#minimagedimension)
- [RelativeRegions](#relativeregions)
- [Sensitivity](#sensitivity)
- [SpatialIndexBlockSize](#spatialindexblocksize)

### RPM_GENERAL_GRAY_CONTRAST

Detects the ROI using the general algorithm based on gray contrast. This mode has the following arguments for further customization.

- [ImageParameterName](#imageparametername)
- [MinImageDimension](#minimagedimension)
- [RelativeRegions](#relativeregions)
- [Sensitivity](#sensitivity)
- [SpatialIndexBlockSize](#spatialindexblocksize)

### RPM_GENERAL_HSV_CONTRAST

Detects the ROI using the general algorithm based on HSV colour contrast. This mode has the following arguments for further customization.

- [AspectRatioRange](#aspectratiorange )
- [FindAccurateBoundary](#findaccurateboundary)
- [ForeAndBackgroundColours](#foreandbackgroundcolours)
- [HeightRange](#heightrange)
- [ImageParameterName](#imageparametername)
- [MinImageDimension](#minimagedimension)
- [RelativeRegions](#relativeregions)
- [Sensitivity](#sensitivity)
- [SpatialIndexBlockSize](#spatialindexblocksize)
- [WidthRange](#widthrange)

### RPM_MANUAL_SPECIFICATION

Defines the ROI directly by specifying the region coordinates. This mode has the following arguments for further customizing.

- [FirstPoint](#firstpoint)
- [FourthPoint](#fourthpoint)
- [ImageParameterName](#imageparametername)
- [MeasuredByPercentage](#measuredbypercentage)
- [RelativeRegions](#relativeregions)
- [SecondPoint](#secondpoint)
- [ThirdPoint](#thirdpoint)

## Setting Methods

### As JSON Parameter

`RegionPredetectionModes` as a JSON parameter is a JSON Object array defined as below.

| Parent Json Object | Key Name | Key Value |
| ------------------ | ------------------- | ---------- |
| ImageParameter | RegionPredetectionModes | A JSON Object array while each Object is defined as below |

| Key Name | Key Value | Description |
| -------- | --------- | ----------- |
| Mode | Any one in Candidate Mode List as string | (Required) Specifies a mode to find a region.  |
| AspectRatioRange | A string from value range of AspectRatioRange | (Optional) Sets the Argument [AspectRatioRange](#aspectratiorange). |
| FindAccurateBoundary | A number from value range of FindAccurateBoundary | (Optional) Sets the Argument [FindAccurateBoundary](#findaccurateboundary). |
| ForeAndBackgroundColours | A string from value range of ForeAndBackgroundColours | (Optional) Sets the Argument [ForeAndBackgroundColours](#foreandbackgroundcolours). |
| HeightRange | A string from value range of HeightRange | (Optional) Sets the Argument [HeightRange](#heightrange). |
| ImageParameterName | A string from value range of ImageParameterName | (Optional) Sets the Argument [ImageParameterName](#imageparametername). |
| MinImageDimension | A number from value range of MinImageDimension | (Optional) Sets the Argument [MinImageDimension](#minimagedimension). |
| RelativeRegions | A string from value range of RelativeRegions | (Optional) Sets the Argument [RelativeRegions](#relativeregions). |
| Sensitivity | A number from value range of Sensitivity | (Optional) Sets the Argument [Sensitivity](#sensitivity). |
| SpatialIndexBlockSize | A number from value range of SpatialIndexBlockSize | (Optional) Sets the Argument [SpatialIndexBlockSize](#spatialindexblocksize). |
| WidthRange | A string from value range of WidthRange | (Optional) Sets the Argument [WidthRange](#widthrange). |

**Default Value**

```json
{
    "RegionPredetectionModes":[
        {
            "Mode": "RPM_GENERAL"
        }
    ]
}
```

**JSON Parameter Example**

```json
{
    "RegionPredetectionModes": [
        {
            "Mode": "RPM_GENERAL_RGB_CONTRAST", 
            "Sensitivity": 5
        },
        {
            "Mode": "RPM_GENERAL_HSV_CONTRAST", 
            "WidthRange": "[100, 200]"
        }
    ]
}
```

## Candidate Argument List

- [AspectRatioRange](#aspectratiorange )
- [FindAccurateBoundary](#findaccurateboundary)
- [FirstPoint](#firstpoint)
- [ForeAndBackgroundColours](#foreandbackgroundcolours)
- [FourthPoint](#fourthpoint)
- [HeightRange](#heightrange)
- [ImageParameterName](#imageparametername)
- [MeasuredByPercentage](#measuredbypercentage)
- [MinImageDimension](#minimagedimension)
- [RelativeRegions](#relativeregions)
- [SecondPoint](#secondpoint)
- [Sensitivity](#sensitivity)
- [SpatialIndexBlockSize](#spatialindexblocksize)
- [ThirdPoint](#thirdpoint)
- [WidthRange](#widthrange)

### AspectRatioRange

Specifies a set (or multiple sets) of aspect ratio range for filtering the predetected region.

| Value Type | Value Range | Default Value | Valid For |
| ---------- | ----------- | ------------- | --------- |
| *string* | A string value representing aspect ratio range sets. | "" | RPM_GENERAL_HSV_CONTRAST |

**Remarks**

- A set of aspect ratio range is defined as [`MinAspectRatio`, `MaxAspectRatio`].
- Using a "";"" to separate multiple sets.
- Value range of `MinAspectRatio`, `MaxAspectRatio`: [1,10000]
- Aspect ratio equals to *height/width\*100*, while the height and width is from the bounding rectangle of the predetected region.

### FindAccurateBoundary

Sets whether to enable finding accurate boundary.

| Value Type | Value Range | Default Value | Valid For |
| ---------- | ----------- | ------------- | --------- |
| *int* | [0, 1] | 0 | `RPM_GENERAL_HSV_CONTRAST` |

**Remarks**

- 0: disable.
- 1: enable.

### FirstPoint

Sets the first point of the region, which is usually the top-left corner.

| Value Type | Value Range | Default Value | Valid For |
| ---------- | ----------- | ------------- | --------- |
| *int array* | A value representing a point | [0, 0] | RPM_MANUAL_SPECIFICATION |

**Remarks**

- A point is defined as [`x-coordinate`, `y-coordinate`].
- When [MeasuredByPercentage](#measuredbypercentage) = 0, the valid value range for `x-coordinate` and `y-coordinate` is [0, 0x7fffffff].
- When [MeasuredByPercentage](#measuredbypercentage) = 1, the valid value range for `x-coordinate` and `y-coordinate` is [0, 100].

### ForeAndBackgroundColours

Specifies a set (or multiple sets) of the foreground and background colours used for region predetection algorithm.

| Value Type | Value Range | Default Value | Valid For |
| ---------- | ----------- | ------------- | --------- |
| *string* | A string value representing one or more colour sets. | "" | RPM_GENERAL_HSV_CONTRAST |

**Remarks**

- This argument is **mandatory** for RPM_GENERAL_HSV_CONTRAST mode. If there is no manual setting, no region can be detected.
- A set of the foreground and background colours is defined as [`ForegroundColour`, `BackgroundColour`, `Tolerance`].
- Using a "";"" to separate multiple sets.
- `ForegroundColour`and `BackgroundColour` are the Hue values in the HSV colour space for defining the foreground and background colours of the regions you want to predetect. The value -1 means black, gray, white.
- `Tolerance` is the allowable deviation of the Hue value defined by `ForegroundColour`.
- Value range of `ForegroundColour`, `BackgroundColour`: [-1,360]
- Value range of `Tolerance`: [0, 360]

### FourthPoint

Sets the fourth point of the region, which is usually the top-left corner.

| Value Type | Value Range | Default Value | Valid For |
| ---------- | ----------- | ------------- | --------- |
| *int array* | A value representing a point | [0, 0] | RPM_MANUAL_SPECIFICATION |

**Remarks**

- A point is defined as [`x-coordinate`, `y-coordinate`].
- When [MeasuredByPercentage](#measuredbypercentage) = 0, the valid value range for `x-coordinate` and `y-coordinate` is [0, 0x7fffffff].
- When [MeasuredByPercentage](#measuredbypercentage) = 1, the valid value range for `x-coordinate` and `y-coordinate` is [0, 100].

### HeightRange

Specifies a set (or multiple sets) of height range for filtering the predetected region.

| Value Type | Value Range | Default Value | Valid For |
| ---------- | ----------- | ------------- | --------- |
| *string* | A string value representing height range sets. | "" | RPM_GENERAL_HSV_CONTRAST |

**Remarks**

- A set of height is defined as [`MinHeight`, `MaxHeight`].
- Using a "";"" to separate multiple sets.
- Value range of `MinHeight`, `MaxHeight`: [1, 0x7fffffff]
- The height value is the height of the bounding rectangle of the predetected region.

### ImageParameterName

Specifies the name of ImageParameter Object which defines the parameters used for predetected region results.

| Value Type | Value Range | Default Value | Valid For |
| ---------- | ----------- | ------------- | --------- |
| *string* | A string value representing the name of an ImageParameter Object. | "" | RPM_GENERAL_HSV_CONTRAST<br>RPM_GENERAL_RGB_CONTRAST<br>RPM_GENERAL_GRAY_CONTRAST<br>RPM_MANUAL_SPECIFICATION |

**Remarks**

Definition of An [ImageParameter Object](../parameter-organization-structure.md#imageparameter-object).

### MeasuredByPercentage

Sets whether or not to use percentages to measure the coordinate.

| Value Type | Value Range | Default Value | Valid For |
| ---------- | ----------- | ------------- | --------- |
| *int* | [0, 1] | 1 | RPM_MANUAL_SPECIFICATION |

### MinImageDimension

Sets the minimum image dimension (in pixels) to enable region pre-detection.

| Value Type | Value Range | Default Value | Valid For |
| ---------- | ----------- | ------------- | --------- |
| *int* | [16384, 0x7fffffff] | 262144 | RPM_GENERAL_HSV_CONTRAST<br>RPM_GENERAL_RGB_CONTRAST<br>RPM_GENERAL_GRAY_CONTRAST |

**Remarks**

The library will enable the region pre-detection feature only when the image dimension is larger than the given value.  

### RelativeRegions

Sets the regions relative to the predetected region.  

| Value Type | Value Range | Default Value | Valid For |
| ---------- | ----------- | ------------- | --------- |
| *string* | A string value representing one or more regions. | "" | RPM_GENERAL_HSV_CONTRAST<br>RPM_GENERAL_RGB_CONTRAST<br>RPM_GENERAL_GRAY_CONTRAST<br>RPM_MANUAL_SPECIFICATION |

**Remarks**

- Each region need to be defined as [`Left`, `Top`, `Right`, `Bottom`, `Index`]. If you want to define multiple regions, you can use a "";"" to separate them.
- `Left`, `Top`, `Right`, `Bottom` are four percentage values relative to top-left corner of the predetected region.
- `Index` means the index of a specific colour set in [`ForeAndBackgroundColours`](#foreandbackgroundcolours) which the current region is applied to. If the value of `index` is set to -1, the current region will be applied to all colour sets in [`ForeAndBackgroundColours`](#foreandbackgroundcolours).
- Value range of `Left`, `Top`, `Right`, `Bottom`: [-10000,10000]
- Value range of `Index`: [-1, 0x7fffffff]

### SecondPoint

Sets the second point of the region, which is usually the top-left corner.

| Value Type | Value Range | Default Value | Valid For |
| ---------- | ----------- | ------------- | --------- |
| *int array* | A value representing a point | [0, 0] | RPM_MANUAL_SPECIFICATION |

**Remarks**

- A point is defined as [`x-coordinate`, `y-coordinate`].
- When [MeasuredByPercentage](#measuredbypercentage) = 0, the valid value range for `x-coordinate` and `y-coordinate` is [0, 0x7fffffff].
- When [MeasuredByPercentage](#measuredbypercentage) = 1, the valid value range for `x-coordinate` and `y-coordinate` is [0, 100].

### Sensitivity

Sets the sensitivity used for region predetection algorithm.

| Value Type | Value Range | Default Value | Valid For |
| ---------- | ----------- | ------------- | --------- |
| *int* | [1, 9] | 1 | RPM_GENERAL_HSV_CONTRAST<br>RPM_GENERAL_RGB_CONTRAST<br>RPM_GENERAL_GRAY_CONTRAST |

**Remarks**

A larger value means the library will take more effort to detect regions.  

### SpatialIndexBlockSize
Sets the spatial index block size used for region predetection algorithm.

| Value Type | Value Range | Default Value | Valid For |
| ---------- | ----------- | ------------- | --------- |
| *int* | [1, 32] | 5 | RPM_GENERAL_HSV_CONTRAST<br>RPM_GENERAL_RGB_CONTRAST<br>RPM_GENERAL_GRAY_CONTRAST |

**Remarks**

The block size used for region predetection would be 2 to the power of N. The allowed values of SpatialIndexBlockSize is the power number (N=1,2,3...).

### ThirdPoint

Sets the third point of the region, which is usually the top-left corner.

| Value Type | Value Range | Default Value | Valid For |
| ---------- | ----------- | ------------- | --------- |
| *int array* | A value representing a point | [0, 0] | RPM_MANUAL_SPECIFICATION |

**Remarks**

- A point is defined as [`x-coordinate`, `y-coordinate`].
- When [MeasuredByPercentage](#measuredbypercentage) = 0, the valid value range for `x-coordinate` and `y-coordinate` is [0, 0x7fffffff].
- When [MeasuredByPercentage](#measuredbypercentage) = 1, the valid value range for `x-coordinate` and `y-coordinate` is [0, 100].

### WidthRange

Specifies a set (or multiple sets) of width range for filtering the predetected region.

| Value Type | Value Range | Default Value | Valid For |
| ---------- | ----------- | ------------- | --------- |
| *string* | A string value representing width range sets. | "" | RPM_GENERAL_HSV_CONTRAST |

**Remarks**

- A set of width is defined as [`MinWidth`, `MaxWidth`].
- Using a "";"" to separate multiple sets.
- Value range of `MinWidth`, `MaxWidth`: [1, 0x7fffffff]
- The width value is the width of the bounding rectangle of the predetected region.
