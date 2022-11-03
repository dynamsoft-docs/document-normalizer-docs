---
layout: default-layout
title: License Activation - Dynamsoft Document Normalizer
keywords: license
breadcrumbText: License Activation
description: License Activation Page
---

# License Initialization

## Get a trial key

- A time-limited public trial license is available for every new device for first use of Dynamsoft Document Normalizer. You can find the public trial license on the following parts of this page.
- If your public trial key is expired, please visit <a href="https://www.dynamsoft.com/customer/license/trialLicense?product=ddn&utm_source=docs" target="_blank">Private Trial License Page</a> to get a 30-day trial extension.

## Get a full license

- [Contact us](https://www.dynamsoft.com/company/contact/)  to purchase a full license

## Initialize the license

The following code snippets are using the public trial license to initialize the license. You can replace the public trial license with your own license key.

<div class="sample-code-prefix"></div>
>- Java-Android
>- Objective-C
>- Swift
>- C
>- C++
>- JavaScript
>
>1. 
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
2. 
```objc
[DynamsoftLicenseManager initLicense:@"DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9" verificationDelegate: self];
- (void)licenseVerificationCallback:(BOOL)isSuccess error:(NSError *)error{
   // Add your code to execute when license verification call back is handled.
}
```
3. 
```swift
DynamsoftLicenseManager.initLicense("DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9", verificationDelegate: self)
func licenseVerificationCallback(_ isSuccess: Bool, error: Error?) {
   // Add your code to execute when license verification call back is handled.
}
```
4. 
```c
int errorCode = 0;
char szErrorMsg[256];
errorCode = DC_InitLicense("DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9", szErrorMsg, 256);
```
5. 
```cpp
int errorCode = 0;
char szErrorMsg[256];
errorCode = CLicenseManager::InitLicense("DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9", szErrorMsg, 256);
if (errorCode != DM_OK)
   cout << szErrorMsg << endl;
```
6. 
```js
Dynamsoft.DDN.DocumentNormalizer.license = "DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9";
```