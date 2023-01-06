---
layout: default-layout
title: Parameter Organization Structure
keywords: organization, parameters, documentation
description: Dynamsoft Document Normalizer - Parameter Organization Structure
---

# Parameter Organization Structure

This article introduces the organization structure of all parameters.

## Definitions

Dynamsoft Document Normalizer uses a template to organize parameters. A template is a `JSON` object which contains following keys:

| Key Name | Description |
| -------- | ----------- |
| GlobalParameter | A JSON Object which defines a [GlobalParameter Object](#globalparameter-object). |
| ImageParameterArray | A JSON Object array which defines multiple [ImageParameter Objects](#imageparameter-object). |
| NormalizerParameterArray | A JSON Object array which defines multiple [NormalizerParameter Objects](#normalizerparameter-object). |

### GlobalParameter Object

A GlobalParameter object contains following keys:

| Key Name | Description |
| -------- | ----------- |
| Name | (Required) A string value which specifies the name of current GlobalParameter object. |
| MaxTotalImageDimension | (Optional) Sets the parameter [MaxTotalImageDimension](reference/max-total-image-dimension.md). |

### ImageParameter Object

An ImageParameter object contains following keys:

| Key Name | Description |
| -------- | ----------- |
| Name | (Required) A string value which specifies the name of current ImageParameter object. The name value must be unique between all ImageParameter objects. |
| RegionPredetectionModes | (Optional) Sets the parameter [RegionPredetectionModes](reference/region-predetection-modes.md). |
| Timeout | (Optional) Sets the parameter [Timeout](reference/timeout.md). |
| ColourChannelUsageType | (Optional) Sets the parameter [ColourChannelUsageType](reference/colour-channel-usage-type.md). |
| MaxThreadCount | (Optional) Sets the parameter [MaxThreadCount](reference/max-thread-count.md). |
| ScaleDownThreshold | (Optional) Sets the parameter [ScaleDownThreshold](reference/scale-down-threshold.md). |
| ColourConversionModes | (Optional) Sets the parameter [ColourConversionModes](reference/colour-conversion-modes.md). |
| GrayscaleTransformationModes | (Optional) Sets the parameter [GrayscaleTransformationModes](reference/grayscale-transformation-modes.md). |
| GrayscaleEnhancementModes | (Optional) Sets the parameter [GrayscaleEnhancementModes](reference/grayscale-enhancement-modes.md). |
| BinarizationModes | (Optional) Sets the parameter [BinarizationModes](reference/binarization-modes.md). |
| TextureDetectionModes | (Optional) Sets the parameter [TextureDetectionModes](reference/texture-detection-modes.md). |
| TextFilterModes | (Optional) Sets the parameter [TextFilterModes](reference/text-filter-modes.md). |
| LineExtractionModes | (Optional) Sets the parameter [LineExtractionModes](reference/line-extraction-modes.md). |
| NormalizerParameterName | (Optional) A string value which is the name of a [NormalizerParameter Object](#normalizerparameter-object). |
| BaseImageParameterName | (Optional) A string value which is the name of an [ImageParameter Object](#imageparameter-object). When a parameter is not explicitly set in current ImageParameter Object, it will inherit the value from base ImageParameter Object. If BaseImageParameterName is also not set, this parameter is set with parameter's default value. |

### NormalizerParameter Object

A NormalizerParameter object contains following keys:

| Key Name | Description |
| -------- | ----------- |
| Name | (Required) A string value which specifies the name of current NormalizerParameter object. The name value must be unique between all NormalizerParameter objects. |
| ContentType | (Optional) Sets the parameter [ContentType](reference/content-type.md). |
| InteriorAngleRangeArray |  (Optional) Sets the parameter [InteriorAngleRangeArray](reference/interior-angle-range-array.md). |
| QuadrilateralDetectionModes | (Optional) Sets the parameter [QuadrilateralDetectionModes](reference/quadrilateral-detection-modes.md). |
| DeskewMode | (Optional) Sets the parameter [DeskewMode](reference/deskew-mode.md). |
| PageSize | (Optional) Sets the parameter [PageSize](reference/page-size.md). |
| ColourMode | (Optional) Sets the parameter [ColourMode](reference/colour-mode.md). |
| Brightness | (Optional) Sets the parameter [Brightness](reference/brightness.md). |
| Contrast | (Optional) Sets the parameter [Contrast](reference/contrast.md). |

## Example

```json
{
    "GlobalParameter":{
        "Name":"GP",
        "MaxTotalImageDimension":0
    },
    "ImageParameterArray":[
        {
            "Name":"IP-1",
            "RegionPredetectionModes":[
                {
                    "Mode": "RPM_GENERAL"
                }
            ],
            "Timeout": 10000,
            "ColourChannelUsageType": "CCUT_AUTO",
            "MaxThreadCount": 4,
            "ScaleDownThreshold": 2300,
            "ColourConversionModes":[
                {
                    "Mode": "CICM_GENERAL",
                    "BlueChannelWeight": -1,
                    "GreenChannelWeight": -1,
                    "RedChannelWeight": -1
                }
            ],
            "GrayscaleTransformationModes":[
                {
                    "Mode": "GTM_ORIGINAL"
                }
            ],
            "GrayscaleEnhancementModes": [
                {
                    "Mode": "GEM_GENERAL" 
                }
            ],
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
            ],
            "TextureDetectionModes":[
                {
                    "Mode": "TDM_GENERAL_WIDTH_CONCENTRATION",
                    "Sensitivity": 5
                }
            ],
            "TextFilterModes": [
                {
                    "Mode": "TFM_GENERAL_CONTOUR", 
                    "IfEraseTextZone": 0,
                    "MinImageDimension": 65536,
                    "Sensitivity": 0
                }
            ],
            "LineExtractionModes": [
                {
                    "Mode": "LEM_GENERAL" 
                }
            ],
            "NormalizerParameterName":"NP-1",
            "BaseImageParameterName":""  
        }
    ],
    "NormalizerParameterArray":[
        {
            "Name":"NP-1",
            "ContentType": "CT_DOCUMENT",
            "InteriorAngleRangeArray": [
                {
                    "MinValue": 70,
                    "MaxValue": 110
                }
            ],
            "QuadrilateralDetectionModes": [
                {
                    "Mode": "QDM_GENERAL" 
                }
            ],
            "DeskewMode": {
                "Mode": "DM_PERSPECTIVE_CORRECTION", 
                "ContentDirection": 0
            },
            "PageSize": [-1, -1],
            "ColourMode": "ICM_BINARY",
            "Brightness": 0,
            "Contrast": 0   
        }
    ]
}
```
