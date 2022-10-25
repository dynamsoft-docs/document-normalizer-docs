---
layout: default-layout
title: Class DCVLicenseManager (Android) - Dynamsoft Document Normalizer Xamarin.Forms API Reference
description: This is the page of Android Class DCVLicenseManager of Dynamsoft Document Normalizer Xamarin.Forms SDK.
keywords: initLicense, DCVLicenseManager, DocumentNormalizer, api reference, Xamarin.Forms
needAutoGenerateSidebar: true
noTitleIndex: true
pageStartVer: 1.0
---

# DDNXamarin.Droid.DCVLicenseManager

The class that implements interface [`ILicenseManager`](license-manager.md) on Android end.

## How to Use

Add the following code in the **MainActivity.cs** of your project to implement `ILicenseManager` with `DCVLicenseManager`.

```csharp
protected override void OnCreate(Bundle savedInstanceState)
{
    ...
    LoadApplication(new App(new DCVCameraEnhancer(this), new DCVDocumentNormalizer(), new DCVLicenseManager(this)));
}
```

## Methods Summary

| Method               | Description |
|----------------------|-------------|
| `InitLicense` | Read the license key and activate the SDK. Implements [`InitLicense`](license-manager.md#initlicense). |
