---
layout: default-layout
title: Dynamsoft Document Normalizer iOS API Reference - LicenseManager class
description: This page shows LicenseManager class of Dynamsoft Document Normalizer for iOS SDK.
keywords: initLicense, LicenseManager, DocumentNormalizer, api reference, ios
needAutoGenerateSidebar: true
noTitleIndex: true
pageStartVer: 1.0
---

# LicenseManager

The LicenseManager class unlocks the Dynamsoft SDK with a purchased full license or a provided trial license to allow you to develop your application.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface DynamsoftLicenseManager
```
2. 
```swift
class DynamsoftLicenseManager : NSObject
```

## Methods

  | Method               | Description |
  |----------------------|-------------|
  | [`initLicense`](#initlicense) | Read the license key and activate the SDK. |

  ---

### initLicense

Read the license key and activate the SDK.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
+(void)initLicense:(NSString*)license verificationDelegate:(nonnull id<LicenseVerificationListener>)listener)
```
2. 
```swift
class func initLicense(_ license: String, verificationDelegate connectionDelegate: Any?)
```

**Parameters**

`[in] license`: The license key.  
`[in] listener`: The listener that handles callback when the license server returns.

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
