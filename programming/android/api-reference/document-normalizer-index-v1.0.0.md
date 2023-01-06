---
layout: default-layout
title: Dynamsoft Document Normalizer Android API Reference - DocumentNormalizer Methods
description: This page shows DocumentNormalizer methods of Dynamsoft Document Normalizer for Android SDK.
keywords: methods, DocumentNormalizer, api reference, android
needAutoGenerateSidebar: true
noTitleIndex: true
breadcrumbText: DocumentNormalizer Class
pageStartVer: 1.0
---

# DocumentNormalizer Class

This is the main class of Dynamsoft Document Normalizer(DDN) SDK. It supports quad detection and image normalization for still pictures and live video.

Common detections include:

- Document boundary detection
- Table boundary detection

Common normalizations include:

- Border crop
- Deskew
- Perspective correction
- Colour mode
- Brightness and Contrast


```java
class com.dynamsoft.ddn.DocumentNormalizer
```

## Initialize Methods

  | Method               | Description |
  |----------------------|-------------|
  | [`DocumentNormalizer`](document-normalizer-init.md#documentnormalizer) | Initialization of `DocumentNormalizer` object.|

## Video Detecting Methods

  | Method               | Description |
  |----------------------|-------------|
  | [`setCameraEnhancer`](document-normalizer-video.md#setcameraenhancer) | Bind a Camera Enhancer instance to the Document Normalizer.  |
  | [`startDetecting`](document-normalizer-video.md#startdetecting) | Start the document quad detection thread in the video streaming scenario. |
  | [`stopDetecting`](document-normalizer-video.md#stopdetecting) | Stop the document quad detection thread in the video streaming scenario.  |
  | [`setDetectResultListener`](document-normalizer-video.md#setdetectresultlistener) | Set callback interface to process detection results generated during frame detecting. |

## Detect and Normalize Methods

  | Method               | Description |
  |----------------------|-------------|
  | [`detectQuad(buffer)`](document-normalizer-normalizing.md#detectquadbuffer) | Detect quad from the memory buffer containing image pixels in defined format. |
  | [`detectQuad(file)`](document-normalizer-normalizing#detectquadfile) | Detect quad from an image file. |
  | [`detectQuad(bitmap)`](document-normalizer-normalizing#detectquadbitmap) | Detect quad from a bufferd image(bitmap). |
  | [`normalize(buffer)`](document-normalizer-normalizing#normalizebuffer) | Normalize image from the memory buffer containing image pixels in defined format. |
  | [`normalize(file)`](document-normalizer-normalizing#normalizefile) | Normalize an image file. |
  | [`normalize(bitmap)`](document-normalizer-normalizing#normalizebitmap) | Normalize a buffered image(bitmap). |
  
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
