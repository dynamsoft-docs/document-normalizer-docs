---
layout: default-layout
title: Class DCVCameraEnhancer (Android) - Dynamsoft Document Normalizer Xamarin.Forms API Reference
description: This is the page of Android Class DCVCameraEnhancer of Dynamsoft Document Normalizer Xamarin.Forms SDK.
keywords: initLicense, DCVCameraEnhancer, api reference, Xamarin.Forms
needAutoGenerateSidebar: true
noTitleIndex: true
pageStartVer: 1.0
---

# DDNXamarin.Droid.DCVCameraEnhancer

The class that implements interface [`ICameraEnhancer`](camera-enhancer.md) on Android end.

## How to Use

Add the following code in the **MainActivity.cs** of your project to implement `ICameraEnhancer` with `DCVCameraEnhancer`.

```csharp
protected override void OnCreate(Bundle savedInstanceState)
{
    ...
    LoadApplication(new App(new DCVCameraEnhancer(this), new DCVDocumentNormalizer(), new DCVLicenseManager(this)));
}
```

## Methods Summary

| Method | Description |
|--------|-------------|
| `Open` | Turn on the current selected camera. Implements [`Open`](camera-enhancer.md#open). |
| `Close` | Turn off the current selected camera. Implements [`Close`](camera-enhancer.md#close). |
| `TurnOnTorch` | Turn on the torch. Implements [`TurnOnTorch`](camera-enhancer.md#turnontorch). |
| `TurnOffTorch` | Turn off the torch. Implements [`TurnOffTorch`](camera-enhancer.md#turnofftorch). |
