---
layout: default-layout
title: Interface ILicenseVerificationListener - Dynamsoft Document Normalizer Xamarin.Forms API Reference
description: This is the page of interface ILicenseVerificationListener of Dynamsoft Document Normalizer Xamarin.Forms SDK.
keywords: ILicenseVerificationListener, interface, Xamarin.Forms
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
pageStartVer: 1.0
---

# ILicenseVerificationListener

`ILicenseVerificationListener` is the interface to handle callback when using [`initLicense`](license-manager.md#initlicense).

```csharp
interface DDNXamarin.ILicenseVerificationListener
```

| Method | Description |
| ------ | ----------- |
| `LicenseVerificationCallback` | The callback of license server. |

## LicenseVerificationCallback

```csharp
void LicenseVerificationCallback(bool isSuccess, string msg);
```

**Parameters**

`[in] isSuccess` Whether the license verification was successful.  
`[in] msg` The error message from license server.

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
