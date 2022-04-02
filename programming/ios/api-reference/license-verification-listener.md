---
layout: default-layout
title: Dynamsoft Document Normalizer iOS API Reference - Interface LicenseVerificationListener
description: This is the interface LicenseVerificationListener page of Dynamsoft Document Normalizer for iOS SDK.
keywords: LicenseVerificationListener, interface, ios
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
pageStartVer: 1.0
---

# LicenseVerificationListener

`LicenseVerificationListener` is the interface to handle callback when using [`initLicense`](license-manager.md#initlicense).

```objc
@protocol LicenseVerificationListener
```

| Method | Description |
| ------ | ----------- |
| `licenseVerificationCallback` | The callback of license server. |

## licenseVerificationCallback

```objc
-(void)licenseVerificationCallback:(BOOL)isSuccess error:(NSError * _Nullable)error;
```

**Parameters**

[in] `isSuccess`: Whether the license verification was successful.  
[in] `error`: The error message from license server.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
[DynamsoftLicenseManager initLicense:@"Put your license here" verificationDelegate: self];
- (void)licenseVerificationCallback:(BOOL)isSuccess error:(NSError *)error{
}
```
2. 
```swift
DynamsoftLicenseManager.initLicense("Put your license here", verificationDelegate: self)
func licenseVerificationCallback(_ isSuccess: Bool, error: Error?) {
}
```
