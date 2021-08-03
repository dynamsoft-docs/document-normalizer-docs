---
title: Dynamsoft Content Normalizer - Parameter Reference
keywords: parameters, reference, dcn, documentation
description: Dynamsoft Content Normalizer - Parameter Reference
---

# Parameter Reference

## ContentNormalizerParameter Object

| Parameter Name | Description |
| -------------- | ----------- |
| `ContentNormalizerParameter.Name` | The unique name of the ContentNormalizerParameter object. |
| `ContentNormalizerParameter.Timeout` | The maximum amount of time (in milliseconds) should be spent on normalizing the content per page. |
| `ContentNormalizerParameter.MaxThreadCount` | The maximum number of threads the algorithm will use to normalize content. |
| `ContentNormalizerParameter.ScaleDownThreshold` | The threshold for the image shrinking. |
| `ContentNormalizerParameter.ColourConversionModes` | The mode array for converting a colour image to a grayscale image. |
| `ContentNormalizerParameter.GrayscaleTransformationModes` | The mode array for the grayscale image conversion. |
| `ContentNormalizerParameter.GrayscaleEnhancementModes` | The mode array for the enhancing grayscale image before content normalization. |
| `ContentNormalizerParameter.BinarizationModes` | The mode array for binarization. |
| `ContentNormalizerParameter.TextureDetectionModes` | The mode array for texture detection. |
| `ContentNormalizerParameter.ExecutePhases` | The string array for specifying the phase(s) to be executed. |
| `ContentNormalizerParameter.NormalizationDefinitionName` | The name of a NormalizationDefinition Object. |
| `ContentNormalizerParameter.QuadrilateralDetectionModes` | The mode array for quadrilateral detection. |
| `ContentNormalizerParameter.MinimalHorizontalSideLength` | The minimal horizontal side length of the quadrilateral. |
| `ContentNormalizerParameter.MinimalVerticalSideLength` | The minimal vertical side length of the quadrilateral. |
| `ContentNormalizerParameter.InteriorAngleRange` | The quadrilateral interior angle range. |


## NormalizationDefinition Object

| Parameter Name | Description |
| -------------- | ----------- |
| `NormalizationDefinition.Name` | The unique name of the NormalizationDefinition object. |
| `NormalizationDefinition.ContentType` | The target content type to be normalized. | 
| `NormalizationDefinition.ContentLocalization` | The localization of content to be normalized. | 
| `NormalizationDefinition.TargetContentPageSize` | The target content page size (width x height in millimeters). | 
| `NormalizationDefinition.EnablePerspectiveCorrection` | Enable perspective correction during normalization or not. | 
| `NormalizationDefinition.EnableDeskewing` | Enable de-skewing during normalization or not. | 
| `NormalizationDefinition.ColourMode` | The target colour mode of the final normalized image. | 
| `NormalizationDefinition.Brightness` | The target brightness value of the final normalized image. | 
| `NormalizationDefinition.Contrast` | The target contrast value of the final normalized image. | 
