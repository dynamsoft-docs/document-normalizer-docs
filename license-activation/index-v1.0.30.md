---
layout: default-layout
title: License initialization - Dynamsoft Document Normalizer
description: This is the documentation - License initialization page of Dynamsoft Document Normalizer.
keywords:  Document Normalizer, License initialization
needAutoGenerateSidebar: true
breadcrumbText: License Initialization
---

# License initialization

## Get a trial key

- A free public trial license is available for every new device for first use of Dynamsoft Document Normalizer. The public trial license is the default key used in samples. You can also find the public trial license on the following parts of this page.
- If your free key is expired, please visit <a href="https://www.dynamsoft.com/customer/license/trialLicense?product=ddn&utm_source=docs" target="_blank">Private Trial License Page</a> to get a 30-day trial extension.

## Get a full license

- [Contact us](https://www.dynamsoft.com/company/contact/)  to purchase a full license

## Initialize the license

The following code snippets are using the public trial license to initialize the license. You can replace the public trial license with your own license key.

<div class="sample-code-prefix"></div>
>- JavaScript
>- Java-Android
>- Objective-C
>- Swift
>- C
>- C++
>
>1. 
```javascript
Dynamsoft.DDN.DocumentNormalizer.license = "DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9";
```     
2. 
```java
LicenseManager.initLicense("DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9", MainActivity.this, new LicenseVerificationListener() {
   @Override
   public void licenseVerificationCallback(boolean isSuccess, CoreException error) {
      if(!isSuccess){
         error.printStackTrace();
      }
   }
});
```
3. 
```objc
[DynamsoftLicenseManager initLicense:@"DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9" verificationDelegate: self];
- (void)licenseVerificationCallback:(BOOL)isSuccess error:(NSError *)error{
   // Add your code to execute when license verification call back is handled.
}
```
4. 
```swift
DynamsoftLicenseManager.initLicense("DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9", verificationDelegate: self)
func licenseVerificationCallback(_ isSuccess: Bool, error: Error?) {
   // Add your code to execute when license verification call back is handled.
}
```
5. 
```c
char errorMessage[256];
DC_InitLicense("DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwNSJ9", errorMessage, 256);
```
6. 
```cpp
char errorMessage[256];
CLicenseManager::InitLicense("DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwNSJ9", errorMessage, 256);
```
