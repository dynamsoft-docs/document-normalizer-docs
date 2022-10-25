---
layout: default-layout
title: Class DCVLicenseManager (iOS) - Dynamsoft Document Normalizer Xamarin.Forms API Reference
description: This is the page of iOS Class DCVLicenseManager of Dynamsoft Document Normalizer Xamarin.Forms SDK.
keywords: initLicense, DCVLicenseManager, DocumentNormalizer, api reference, Xamarin.Forms
needAutoGenerateSidebar: true
noTitleIndex: true
pageStartVer: 1.0
---

# DDNXamarin.iOS.DCVLicenseManager

The class that implements interface [`ILicenseManager`](license-manager.md) on iOS end.

## How to Use

Add the following code in the **AppDelegate.cs** of your project to implement `ILicenseManager` with `DCVLicenseManager`.

```csharp
public override bool FinishedLaunching(UIApplication app, NSDictionary options)
{
    LoadApplication(new App(new DCVCameraEnhancer(), new DCVDocumentNormalizer(), new DCVLicenseManager()));
}
```

## Methods Summary

| Method               | Description |
|----------------------|-------------|
| `InitLicense` | Read the license key and activate the SDK. Implements [`InitLicense`](license-manager.md#initlicense). |
