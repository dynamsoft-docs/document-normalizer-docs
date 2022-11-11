---
layout: default-layout
title: Interface ILicenseManager - Dynamsoft Document Normalizer Xamarin.Forms API Reference
description: This is the page of interface ILicenseManager of Dynamsoft Document Normalizer Xamarin.Forms SDK.
keywords: initLicense, ILicenseManager, DocumentNormalizer, api reference, Xamarin.Forms
needAutoGenerateSidebar: true
noTitleIndex: true
pageStartVer: 1.0
---

# Interface ILicenseManager

The interface `ILicenseManager` unlocks the Dynamsoft SDK with a purchased full license or a provided trial license to allow you to develop your application.

```csharp
interface DDNXamarin.ILicenseManager
```

## Methods

| Method               | Description |
|----------------------|-------------|
| [`InitLicense`](#initlicense) | Read the license key and activate the SDK. |

---

### InitLicense

Read the license key and activate the SDK.

```csharp
void InitLicense(string license, ILicenseVerificationListener licenseListener);
```

**Parameters**

`[in] license`: The license key.
`[in] licenseListener`: The listener that handles callback when the license server returns.

**Code Snippet**

```csharp
public partial class App : Application, ILicenseVerificationListener
{
    public App(ICameraEnhancer enhancer, IDocumentNormalizer normalizer, ILicenseManager manager)
    {
        ...
        licenseManager = manager;
        licenseManager.InitLicense("Put your license here.", this);
        ...
    }
    public void LicenseVerificationCallback(bool isSuccess, string msg)
    {
        // Add code to execute when license server returns.
    }
}
```
