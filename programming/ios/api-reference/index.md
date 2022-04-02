---
layout: default-layout
title: Dynamsoft Document Normalizer iOS API Reference - Main Page
description: This is the main page of Dynamsoft Document Normalizer for iOS SDK API Reference.
keywords: api reference, ios
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: iOS API Reference
noTitleIndex: true
---

# API Reference - iOS

## DocumentNormalizer Class

This is the main class of Dynamsoft Document Normalizer(DDN) SDK. It supports quad detection and image normalization for still pictures and live video.

```objc
@interface DynamsoftDocumentNormalizer
```

## Initialize

| Method               | Description |
|----------------------|-------------|
| [`init`](document-normalizer-init.md#init) | Initialization of `DynamsoftDocumentNormalizer` object.|

## Video Detecting Methods

| Method               | Description |
|----------------------|-------------|
| [`setCameraEnhancer`](document-normalizer-video.md#setcameraenhancer) | Bind a Camera Enhancer instance to the Document Normalizer.  |
| [`startDetecting`](document-normalizer-video.md#startdetecting) | Start the document quad detection thread in the video streaming scenario. |
| [`stopDetecting`](document-normalizer-video.md#stopdetecting) | Stop the document quad detection thread in the video streaming scenario. |
| [`setDetectResultListener`](document-normalizer-video.md#setdetectresultlistener) | Set callback interface to process detection results generated during frame detecting. |

## Detect and Normalize Methods

| Method               | Description |
|----------------------|-------------|
| [`detectQuadFromBuffer`](document-normalizer-normalizing.md#detectquadfrombuffer) | Detect quad from the memory buffer containing image pixels in defined format. |
| [`detectQuadFromFile`](document-normalizer-normalizing.md#detectquadfromfile) | Detect quad from an image file. |
| [`detectQuadFromImage`](document-normalizer-normalizing.md#detectquadfromimage) | Detect quad from a bufferd image(uiimage). |
| [`normalizeBuffer`](document-normalizer-normalizing.md#normalizebuffer) | Normalize image from the memory buffer containing image pixels in defined format. |
| [`normalizeFile`](document-normalizer-normalizing.md#normalizefile) | Normalize an image file. |
| [`normalizeImage`](document-normalizer-normalizing.md#normalizeimage) | Normalize a buffered image(uiimage). |
  
## Runtime Settings Methods

| Method               | Description |
|----------------------|-------------|
| [`initRuntimeSettingsFromFile`](document-normalizer-settings.md#initruntimesettingsfromfile)  | Initialize runtime settings with the settings in a given JSON file. |
| [`initRuntimeSettingsFromString`](document-normalizer-settings.md#initruntimesettingsfromstring) | Initialize runtime settings with the settings in a given JSON string. |
| [`outputRuntimeSettingsToFile`](document-normalizer-settings.md#outputruntimesettingstofile) | Output runtime settings to a settings file (JSON file). |
| [`outputRuntimeSettings`](document-normalizer-settings.md#outputruntimesettings) | Output runtime settings to a string. |

## General Methods

| Method               | Description |
|----------------------|-------------|
| [`getVersion`](document-normalizer-general.md#getversion) | Get version information of SDK.|

## Auxiliary Classes

- [`iQuadrilateral`](quadrilateral.md)
- [`iImageData`](image-data.md)
- [`DynamsoftLicenseManager`](license-manager.md)
- [`iDetectedQuadResult`](detected-quad-result.md)
- [`iNormalizedImageResult`](normalized-image-result.md)

&nbsp;

## Interfaces

- [`LicenseVerificationListener`](license-verification-listener.md)
- [`DetectResultListener`](detect-result-listener.md)

&nbsp;

## Enumerations

&nbsp;

## Others

View the [Error Codes]({{ site.enumerations }}error-code.html)
