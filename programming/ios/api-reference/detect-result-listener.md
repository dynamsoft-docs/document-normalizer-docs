---
layout: default-layout
title: Dynamsoft Document Normalizer iOS API Reference - Interface DetectResultListener
description: This the interface DetectResultListener page of Dynamsoft Document Normalizer for iOS SDK.
keywords: DetectResultListener, interface, ios
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
---

# DetectResultListener

`DetectResultListener` is the protocol to handle callbacks when the detection results are returned.

```objc
@protocol DetectResultListener
```

| Method | Description |
| ------ | ----------- |
| `detectResultCallback` | The callback method to handle the detection results returned by the library. |

## detectResultCallback

The callback method to handle the detection results returned by the library.

```objc
- (void)detectResultCallback:(NSInteger)frameId frame:(iImageData*)imgData detectedResults:(NSArray<iDetectedQuadResult*>* _Nullable)detectedResults;
```

**Parameters**

`[in] frameId` The ID of the frame.  
`[in] imgData` The image data of frame.  
`[in] detectResults` Detected results of the frame.

**Code Snippet**

```objc
DetectResultListener detectResultListener = new DetectResultListener() {
    @Override
    public void detectResultCallback(int frameId, ImageData imageData, QuadDetectionResult[] textResults) {
        // Add your code
    }
};
```

