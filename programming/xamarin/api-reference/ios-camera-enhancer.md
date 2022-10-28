---
layout: default-layout
title: Class DCVCameraEnhancer (iOS) - Dynamsoft Document Normalizer Xamarin.Forms API Reference
description: This is the page of iOS Class DCVCameraEnhancer of Dynamsoft Document Normalizer Xamarin.Forms SDK.
keywords: initLicense, DCVCameraEnhancer, api reference, Xamarin.Forms
needAutoGenerateSidebar: true
noTitleIndex: true
pageStartVer: 1.0
---

# DDNXamarin.iOS.DCVCameraEnhancer

The class that implements interface [`ICameraEnhancer`](camera-enhancer.md) on iOS end.

## How to Use

Add the following code in the **AppDelegate.cs** of your project to implement `ICameraEnhancer` with `DCVCameraEnhancer`.

```csharp
public override bool FinishedLaunching(UIApplication app, NSDictionary options)
{
    LoadApplication(new App(new DCVCameraEnhancer(), new DCVDocumentNormalizer(), new DCVLicenseManager()));
}
```

## Methods Summary

| Method | Description |
|--------|-------------|
| [`Open`](camera-enhancer.md#open) | Turn on the current selected camera. |
| [`Close`](camera-enhancer.md#close) | Turn off the current selected camera. |
| [`TurnOnTorch`](camera-enhancer.md#turnontorch) | Turn on the torch. |
| [`TurnOffTorch`](camera-enhancer.md#turnofftorch) | Turn off the torch. |
