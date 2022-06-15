---
layout: default-layout
title: TextFilterModes
keywords: TextFilterModes, parameters, reference, documentation
description: Dynamsoft Document Normalizer Parameter Reference - TextFilterModes
---

# TextFilterModes

`TextFilterModes` is used to control how to filter texts on an image. It currently consists of a single mode.

## Candidate Mode List

- TFM_GENERAL_CONTOUR

### TFM_GENERAL_CONTOUR

Filters text using the general algorithm based on contour. This mode has the following arguments for further customization.

- [IfEraseTextZone](#iferasetextzone)
- [MinImageDimension](#minimagedimension)
- [Sensitivity](#sensitivity)

## Setting Methods

### As JSON Parameter

`TextFilterModes` as a JSON parameter is a JSON Object array defined as below.

| Parent Json Object | Key Name | Key Value |
| ------------------ | ------------------- | ---------- |
| ImageParameter | TextFilterModes | A JSON Object array while each Object is defined as below |

| Key Name | Key Value | Description |
| -------- | --------- | ----------- |
| Mode | Any one in Candidate Mode List as string | (Required) Specifies a mode for text filtering.  |
| IfEraseTextZone | A number from value range of IfEraseTextZone | (Optional) Sets the Argument [IfEraseTextZone](#iferasetextzone). |
| MinImageDimension | A number from value range of MinImageDimension | (Optional) Sets the Argument [MinImageDimension](#minimagedimension). |
| Sensitivity | A number from value range of Sensitivity | (Optional) Sets the Argument [Sensitivity](#sensitivity). |

**Default Value**

```json
{
    "TextFilterModes": [
        {
            "Mode": "TFM_GENERAL_CONTOUR", 
            "IfEraseTextZone": 0,
            "MinImageDimension": 65536,
            "Sensitivity": 0
        }
    ]
}
```

**JSON Parameter Example**

```json
{
    "TextFilterModes": [
        {
            "Mode": "TFM_GENERAL_CONTOUR", 
            "Sensitivity": 5
        }
    ]
}
```

## Candidate Argument List

- [IfEraseTextZone](#iferasetextzone)
- [MinImageDimension](#minimagedimension)
- [Sensitivity](#sensitivity)

### IfEraseTextZone

Sets whether to erase the detected text zone.

| Value Type | Value Range | Default Value | Valid For |
| ---------- | ----------- | ------------- | --------- |
| *int* | [0, 1] | 0 | TFM_GENERAL_CONTOUR |

**Remarks**

- 0: Do not erase the text zone.
- 1: Erase the text zone.

### MinImageDimension

Sets the minimum image dimension (in pixels) to enable text filtering.

| Value Type | Value Range | Default Value | Valid For |
| ---------- | ----------- | ------------- | --------- |
| *int* | [65536, 0x7fffffff] | 65536 | TFM_GENERAL_CONTOUR |

**Remarks**

The library will enable the region pre-detection feature only when the image dimension is larger than the given value.  

### Sensitivity

Sets the sensitivity used for text filtering.

| Value Type | Value Range | Default Value | Valid For |
| ---------- | ----------- | ------------- | --------- |
| *int* | [0, 9] | 0 | TFM_GENERAL_CONTOUR |

**Remarks**

- 0: automatically set by the library.
- A larger value means the library will take more effort to filter text.
