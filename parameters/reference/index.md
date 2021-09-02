---
title: Dynamsoft Document Normalizer - Parameter Reference
keywords: parameters, reference, ddn, documentation
description: Dynamsoft Document Normalizer - Parameter Reference
---

# Parameter Reference

## Parameter References

- [`BinarizationModes`]({{ site.parameter_reference }}binarization-modes.html)
- [`Brightness`]({{ site.parameter_reference }}brightness.html)
- [`ColourConversionModes`]({{ site.parameter_reference }}colour-conversion-modes.html)
- [`ColourMode`]({{ site.parameter_reference }}colour-mode.html)
- [`Contrast`]({{ site.parameter_reference }}contrast.html)
- [`EnableDeskewing`]({{ site.parameter_reference }}enable-deskewing.html)
- [`EnablePerspectiveCorrection`]({{ site.parameter_reference }}enable-perspective-correction.html)
- [`ExecutePhases`]({{ site.parameter_reference }}execute-phases.html)
- [`GrayscaleEnhancementModes`]({{ site.parameter_reference }}grayscale-enhancement-modes.html)
- [`GrayscaleTransformationModes`]({{ site.parameter_reference }}grayscale-transformation-modes.html)
- [`InteriorAngleRange`]({{ site.parameter_reference }}interior-angle-range.html)
- [`MaxThreadCount`]({{ site.parameter_reference }}max-thread-count.html)
- [`MinimalHorizontalSideLength`]({{ site.parameter_reference }}minimal-horizontal-side-length.html)
- [`MinimalVerticalSideLength`]({{ site.parameter_reference }}minimal-vertical-side-length.html)
- [`QuadrilateralDetectionModes`]({{ site.parameter_reference }}quadrilateral-detection-modes.html)
- [`ScaleDownThreshold`]({{ site.parameter_reference }}scale-down-threshold.html)
- [`TargetContentPageSize`]({{ site.parameter_reference }}target-content-page-size.html)
- [`TextureDetectionModes`]({{ site.parameter_reference }}texture-detection-modes.html)
- [`Timeout`]({{ site.parameter_reference }}timeout.html)


## JSON Object Reference
### DocumentNormalizerParameter Object

| Parameter Name | Description |
| -------------- | ----------- |
| [`DocumentNormalizerParameter.Name`]({{ site.parameter_content_normalizer }}#name) | The unique name of the DocumentNormalizerParameter object. |
| [`DocumentNormalizerParameter.Timeout`]({{ site.parameter_content_normalizer }}#timeout) | The maximum amount of time (in milliseconds) should be spent on normalizing the content per page. |
| [`DocumentNormalizerParameter.MaxThreadCount`]({{ site.parameter_content_normalizer }}#maxthreadcount) | The maximum number of threads the algorithm will use to normalize content. |
| [`DocumentNormalizerParameter.ScaleDownThreshold`]({{ site.parameter_content_normalizer }}#scaledownthreshold) | The threshold for the image shrinking. |
| [`DocumentNormalizerParameter.ColourConversionModes`]({{ site.parameter_content_normalizer }}#colourconversionmodes) | The mode array for converting a colour image to a grayscale image. |
| [`DocumentNormalizerParameter.GrayscaleTransformationModes`]({{ site.parameter_content_normalizer }}#grayscaletransformationmodes) | The mode array for the grayscale image conversion. |
| [`DocumentNormalizerParameter.GrayscaleEnhancementModes`]({{ site.parameter_content_normalizer }}#grayscaleenhancementmodes) | The mode array for the enhancing grayscale image before content normalization. |
| [`DocumentNormalizerParameter.BinarizationModes`]({{ site.parameter_content_normalizer }}#binarizationmodes) | The mode array for binarization. |
| [`DocumentNormalizerParameter.TextureDetectionModes`]({{ site.parameter_content_normalizer }}#texturedetectionmodes) | The mode array for texture detection. |
| [`DocumentNormalizerParameter.ExecutePhases`]({{ site.parameter_content_normalizer }}#executephases) | The string array for specifying the phase(s) to be executed. |
| [`DocumentNormalizerParameter.NormalizationDefinitionName`]({{ site.parameter_content_normalizer }}#normalizationdefinitionname) | The name of a NormalizationDefinition Object. |
| [`DocumentNormalizerParameter.QuadrilateralDetectionModes`]({{ site.parameter_content_normalizer }}#quadrilateraldetectionmodes) | The mode array for quadrilateral detection. |
| [`DocumentNormalizerParameter.MinimalHorizontalSideLength`]({{ site.parameter_content_normalizer }}#minimalhorizontalsidelength) | The minimal horizontal side length of the quadrilateral. |
| [`DocumentNormalizerParameter.MinimalVerticalSideLength`]({{ site.parameter_content_normalizer }}#minimalverticalsidelength) | The minimal vertical side length of the quadrilateral. |
| [`DocumentNormalizerParameter.InteriorAngleRange`]({{ site.parameter_content_normalizer }}#interioranglerange) | The quadrilateral interior angle range. |


### NormalizationDefinition Object

| Parameter Name | Description |
| -------------- | ----------- |
| [`NormalizationDefinition.Name`]({{ site.parameter_normalization_definition }}#name) | The unique name of the NormalizationDefinition object. |
| [`NormalizationDefinition.ContentType`]({{ site.parameter_normalization_definition }}#contenttype) | The target content type to be normalized. | 
| [`NormalizationDefinition.ContentLocalization`]({{ site.parameter_normalization_definition }}#contentlocalization) | The localization of content to be normalized. | 
| [`NormalizationDefinition.TargetContentPageSize`]({{ site.parameter_normalization_definition }}#targetcontentpagesize) | The target content page size (width x height in millimeters). | 
| [`NormalizationDefinition.EnablePerspectiveCorrection`]({{ site.parameter_normalization_definition }}#enableperspectivecorrection) | Enable perspective correction during normalization or not. | 
| [`NormalizationDefinition.EnableDeskewing`]({{ site.parameter_normalization_definition }}#enabledeskewing) | Enable de-skewing during normalization or not. | 
| [`NormalizationDefinition.ColourMode`]({{ site.parameter_normalization_definition }}#colourmode) | The target colour mode of the final normalized image. | 
| [`NormalizationDefinition.Brightness`]({{ site.parameter_normalization_definition }}#brightness) | The target brightness value of the final normalized image. | 
| [`NormalizationDefinition.Contrast`]({{ site.parameter_normalization_definition }}#contrast) | The target contrast value of the final normalized image. | 
