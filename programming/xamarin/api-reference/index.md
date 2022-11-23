---
layout: default-layout
title: Dynamsoft Document Normalizer Xamarin.Forms API Reference - Main Page
description: This is the main page of Dynamsoft Document Normalizer for Xamarin.Forms SDK API Reference.
keywords: api reference, Xamarin.Forms
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: Xamarin.Forms API Reference
noTitleIndex: true
---

# API Reference - Xamarin.Forms

## namespace DDNXamarin

### Primary Interfaces

| Interface | Description |
| --------------- | ----------- |
| [`Interface IDocumentNormalizer`](document-normalizer.md) | The interface that includes document boundary detecting and image normalizing methods. |
| [`Interface ICameraEnhancer`](camera-enhancer.md) | The interface that includes camera control methods. |

### Auxiliary Classes/Interfaces

| Class/Interface | Description |
| --------------- | ----------- |
| [`Class Quadrilateral`](quadrilateral.md) | The class that stores the information of quadrilateral coordinates. |
| [`Class ImageData`](image-data.md) | The class that stores image data. |
| [`Class DetectedQuadResult`](detected-quad-result.md) | The class that stores the information of the detected quads. |
| [`Class NormalizedImageResult`](normalized-image-result.md) | The class that stores the information of normalized results. |
| [`Class DCVCameraView`](camera-view.md) | A view class that enables users to display video streaming. |
| [`Class DCVImageEditorView`](image-editor-view.md) | A view class for users to add editable UI elements on a static image. |
| [`Interface ILicenseManager`](license-manager.md) | The interface that includes license activation methods. |
| [`Interface ILicenseVerificationListener`](license-verification-listener.md) | The interface that handles callback when license server returns. |
| [`Interface IDetectResultListener`](detect-result-listener.md) | The interface that handles callback when quad results are detected. |

### Enumerations

| Class | Description |
| ----- | ----------- |
| [`EnumImagePixelFormat`](enum-image-pixel-format.md) | The enumeration that indicates the image pixel format. |

## namespace DCVXamarin.Droid

| Class | Description |
| --------------- | ----------- |
| [`Class DocumentNormalizer`](droid-document-normalizer.md) | The class that implements `IDocumentNormalizer` methods on Android end. |
| [`Class CameraEnhancer`](droid-camera-enhancer.md) | The class that implements `ICameraEnhancer` methods on Android end. |
| [`Class LicenseManager`](droid-license-manager.md) | The class that implements `ILicenseManager` methods on Android end. |

## namespace DCVXamarin.iOS

| Class | Description |
| --------------- | ----------- |
| [`Class DocumentNormalizer`](ios-document-normalizer.md) | The class that implements `IDocumentNormalizer` methods on iOS end. |
| [`Class CameraEnhancer`](ios-camera-enhancer.md) | The class that implements `ICameraEnhancer` methods on iOS end. |
| [`Class LicenseManager`](ios-license-manager.md) | The class that implements `ILicenseManager` methods on iOS end. |
