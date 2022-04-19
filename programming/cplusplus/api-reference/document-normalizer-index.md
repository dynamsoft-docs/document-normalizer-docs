---
layout: default-layout
title: CDocumentNormalizer Class
description: This page shows CDocumentNormalizer class definition of Dynamsoft Document Normalizer SDK C++ Edition.
keywords: methods, CDocumentNormalizer, api reference, c++
---

# CDocumentNormalizer Class

```c++
class dynamsoft::ddn::CDocumentNormalizer
```

| Method               | Description |
|----------------------|-------------|
| [`CDocumentNormalizer`](document-normalizer-init.md#cdocumentnormalizer) | Constructor of `CDocumentNormalizer` class.|
| [`~CDocumentNormalizer`](document-normalizer-init.md#cdocumentnormalizer-1) | Destructor of `CDocumentNormalizer` class.|
| [`DetectQuad`](document-normalizer-normalizing.md#detectquad) | Detects quad from source image. |
| [`FreeNormalizedImageResult`](document-normalizer-result.md#freenormalizedimageresult) | Releases memory allocated for CNormalizedImageResult. |
| [`FreeDetectedQuadResultArray`](document-normalizer-result.md#freedetectedquadresultarray) | Releases memory allocated for CDetectedQuadResultArray. |
| [`FreeString`](document-normalizer-result.md#freestring) | Releases memory allocated for a string. |
| [`GetErrorString`](document-normalizer-general.md#geterrorstring) | Returns the corresponding error message of the input error code. |
| [`GetVersion`](document-normalizer-general.md#getversion) | Returns the version info string of the SDK. |
| [`InitRuntimeSettingsFromFile`](document-normalizer-settings.md#initruntimesettingsfromfile)  | Initializes runtime settings with the settings in a given JSON file. |
| [`InitRuntimeSettingsFromString`](document-normalizer-settings.md#initruntimesettingsfromstring) | Initializes runtime settings with the settings in a given JSON string. |
| [`Normalize`](document-normalizer-normalizing.md#normalize) | Normalizes the source image. |
| [`OutputRuntimeSettingsToFile`](document-normalizer-settings.md#outputruntimesettingstofile) | Output runtime settings to a settings file (JSON file). |
| [`OutputRuntimeSettingsToString`](document-normalizer-settings.md#outputruntimesettingstostring) | Output runtime settings to a string. |
| [`SaveImageDataToFile`](document-normalizer-result.md#saveimagedatatofile) | Save the image data to a file. |
