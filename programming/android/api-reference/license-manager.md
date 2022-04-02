---
layout: default-layout
title: Dynamsoft Document Normalizer Android API Reference - LicenseManager class
description: This page shows LicenseManager class of Dynamsoft Document Normalizer for Android SDK.
keywords: initLicense, LicenseManager, DocumentNormalizer, api reference, android
needAutoGenerateSidebar: true
noTitleIndex: true
pageStartVer: 1.0
---

# LicenseManager

The LicenseManager class unlocks the Dynamsoft SDK with a purchased full license or a provided trial license to allow you to develop your application.

```java
class com.dynamsoft.core.LicenseManager
```

## Methods

  | Method               | Description |
  |----------------------|-------------|
  | [`initLicense`](#initlicense) | Read the license key and activate the SDK. |

  ---

### initLicense

Read the license key and activate the SDK.

```java
static void initLicense(String license, LicenseVerificationListener listener)
```

**Parameters**

[in] `license`: The license key.
[in] `listener`: The listener that handles callback when the license server returns.

**Code Snippet**

```java
LicenseManager.initLicense("DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9", new LicenseVerificationListener() {
   @Override
   public void LicenseVerificationCallback(boolean isSuccess, Exception error) {
      if(!isSuccess){
         error.printStackTrace();
      }
   }
});
```
