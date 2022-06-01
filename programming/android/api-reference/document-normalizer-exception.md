---
layout: default-layout
title: Dynamsoft Document Normalizer Android API Reference - DocumentNormalizerException Class
description: This page shows the DocumentNormalizerException Class of Dynamsoft Document Normalizer for Android SDK.
keywords: DocumentNormalizerException, class, api reference, android
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# DocumentNormalizerException

Exception for signalling document normalizer errors.

```java
class com.dynamsoft.ddn.DocumentNormalizerException;
```

| Method | Type | Description |
|--------|------|-------------|
| [`getErrorCode`](#geterrorcode)| *int* | Get the error code |

## getErrorCode

**Return Value**

This method returns the DDN error code. Please view more about the error code in [`EnumErrorCode`]({{site.enumerations}}error-code.html)

**Code Snippet**

```java
try {
    DocumentNormalizer normalizer = new DocumentNormalizer();
    QuadDetectionResult[] results = normalizer.detect("Your file path");
} catch (DocumentNormalizerException e) {
    Log.i("Detect", "The error code is: " + e.getErrorCode());
}
```
