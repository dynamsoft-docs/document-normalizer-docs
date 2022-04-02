---
layout: default-layout
title: Dynamsoft Document Normalizer Android API Reference - Interface LicenseVerificationListener
description: This is the interface LicenseVerificationListener page of Dynamsoft Document Normalizer for Android SDK.
keywords: LicenseVerificationListener, interface, android
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
pageStartVer: 1.0
---

# LicenseVerificationListener

`LicenseVerificationListener` is the interface to handle callback when using [`initLicense`](license-manager.md#initlicense).

```java
interface com.dynamsoft.core.LicenseVerificationListener
```

| Method | Description |
| ------ | ----------- |
| `licenseVerificationCallback` | The callback of license server. |

## licenseVerificationCallback

```java
void licenseVerificationCallback(boolean isSuccess, Exception error);
```

**Parameters**

`[in] isSuccess`: Whether the license verification was successful.  
`[in] error`: The error message from license server.

**Code Snippet**

```java
LicenseVerificationListener licenseListener = new LicenseVerificationListener() {
    @Override
    public void licenseVerificationCallback(boolean isSuccess, Exception error) {
        // Add your code
    }
};
```
