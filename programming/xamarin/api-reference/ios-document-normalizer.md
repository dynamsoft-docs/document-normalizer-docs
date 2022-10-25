---
layout: default-layout
title: Class DCVDocumentNormalizer (iOS) - Dynamsoft Document Normalizer Xamarin.Forms API Reference
description: This is the page of iOS Class DCVDocumentNormalizer of Dynamsoft Document Normalizer Xamarin.Forms SDK.
keywords: initLicense, DCVDocumentNormalizer, api reference, Xamarin.Forms
needAutoGenerateSidebar: true
noTitleIndex: true
pageStartVer: 1.0
---

# DDNXamarin.iOS.DCVDocumentNormalizer

The class that implements interface [`IDocumentNormalizer`](license-manager.md) on iOS end.

## How to Use

Add the following code in the **AppDelegate.cs** of your project to implement `IDocumentNormalizer` with `DCVDocumentNormalizer`.

```csharp
public override bool FinishedLaunching(UIApplication app, NSDictionary options)
{
    LoadApplication(new App(new DCVCameraEnhancer(), new DCVDocumentNormalizer(), new DCVLicenseManager()));
}
```

## Methods Summary

| Method | Description |
|--------|-------------|
| `SetCameraEnhancer` | Sets an instance of ImageSource to get images. Implements [`IDocumentNormalizer.SetCameraEnhancer`](document-normalizer.md#setcameraenhancer). |
| `StartDetecting` | Start the document quad detection thread in the video streaming scenario. Implements [`IDocumentNormalizer.StartDetecting`](document-normalizer.md#startdetecting). |
| `StopDetecting` | Stop the document quad detection thread in the video streaming scenario. Implements [`IDocumentNormalizer.StopDetecting`](document-normalizer.md#stopdetecting). |
| `AddResultListener` | Set callback interface to process detection results generated during frame detecting. Implements [`AddResultListener`](document-normalizer.md#addresultlistener). |
| `DetectQuad(ImageData)` | Detect quad from the memory buffer containing image pixels in defined format. Implements [`DetectQuad(ImageData)`](document-normalizer.md#detectquadimagedata). |
| `DetectQuad(File)` | Detect quad from an image file. Implements [`DetectQuad(File)`](document-normalizer.md#detectquadfile). |
| `Normalize(ImageData)` | Normalize image from the memory buffer containing image pixels in defined format. Implements [`Normalize(ImageData)`](document-normalizer.md#normalizeimagedata). |
| `Normalize(File)` | Normalize an image file. Implements [`Normalize(File)`](document-normalizer.md#normalizefile). |
| `InitRuntimeSettingsFromFile` | Initialize runtime settings with the settings in a given JSON file. Implements [`InitRuntimeSettingsFromFile`](document-normalizer.md#initruntimesettingsfromfile). |
| `InitRuntimeSettings` | Initialize runtime settings with the settings in a given JSON string. Implements [`InitRuntimeSettings`](document-normalizer.md#initruntimesettings). |
| `OutputRuntimeSettingsToFile` | Output runtime settings to a settings file (JSON file). Implements [`OutputRuntimeSettingsToFile`](document-normalizer.md#outputruntimesettingstofile). |
| `OutputRuntimeSettings` | Output runtime settings to a string. Implements [`OutputRuntimeSettings`](document-normalizer.md#outputruntimesettings). |
| `SaveToFile` | Save a `NormalizedImageResult` to the targeting file path. Implements [`SaveToFile`](document-normalizer.md#savetofile). |
| `GetVersion` | Get version information of SDK. Implements [`GetVersion`](document-normalizer.md#getversion). |
