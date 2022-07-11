---
layout: default-layout
title: Dynamsoft Document Normalizer Android API Reference - Interface DetectResultListener
description: This the interface DetectResultListener page of Dynamsoft Document Normalizer for Android SDK.
keywords: DetectResultListener, interface, android
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
---

# DetectResultListener

`DetectResultListener` is the interface to handle callbacks when the detection results are returned.

```java
interface com.dynamsoft.ddn.DetectResultListener
```

| Method | Description |
| ------ | ----------- |
| `detectResultCallback` | The callback method to handle the detection results returned by the library. |

## detectResultCallback

The callback method to handle the detection results returned by the library.

```java
void detectResultCallback(int frameId, ImageData imageData, DetectedQuadResult[] detectResults);
```

**Parameters**

`[in] frameId`: The ID of the frame.  
`[in] imgData`: The image data of frame.  
`[in] detectResults`: Detected results of the frame.

**Code Snippet**

```java
DetectResultListener detectResultListener = new DetectResultListener() {
    @Override
    public void detectResultCallback(int frameId, ImageData imageData, DetectedQuadResult[] textResults) {
        // Add your code
    }
};
```
