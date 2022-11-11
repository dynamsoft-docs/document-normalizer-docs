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
static void initLicense(String license, android.content.Contex contex, LicenseVerificationListener listener)
```

**Parameters**

`[in] license` The license key.
`[in] contex` The interface to global information about an application environment.
`[in] listener` The listener that handles callback when the license server returns.

**Code Snippet**

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
