---
layout: default-layout
title: Dynamsoft Document Normalizer Android API Reference - DocumentNormalizer initialization
description: This page shows DocumentNormalizer initialization methods of Dynamsoft Document Normalizer for Android SDK.
keywords: DocumentNormalizer, initialization, api reference, android
needAutoGenerateSidebar: true
noTitleIndex: true
---

# Initialization Methods

  | Method               | Description |
  |----------------------|-------------|
  | [`DocumentNormalizer`](#documentnormalizer) | Initialization of `DocumentNormalizer` object.|

---

## DocumentNormalizer

Initialization of `DocumentNormalizer` object.

```java
DocumentNormalizer() throws DocumentNormalizerException
```

**Exceptions**

[`DocumentNormalizerException`](document-normalizer-exception.md)

**Code Snippet**

```java
try {
    DocumentNormalizer normalizer = new DocumentNormalizer();
} catch (DocumentNormalizerException e) {
    Log.i("DDN", "The error code is: " + e.getErrorCode());
}
```
