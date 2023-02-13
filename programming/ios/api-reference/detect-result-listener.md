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

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (void)detectResultCallback:(NSInteger)frameId frame:(iImageData*)imgData detectedResults:(NSArray<iDetectedQuadResult*>* _Nullable)detectedResults;
```
2. 
```swift
func detectResultCallback(_ frameId: Int, imageData: iImageData, results: [iDetectedQuadResult])
```

**Parameters**

`[in] frameId`: The ID of the frame.  
`[in] imgData`: The image data of frame.  
`[in] detectResults`: Detected results of the frame.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (void)detectResultCallback:(NSInteger)frameId imageData:(nonnull iImageData *)imageData results:(nonnull NSArray<iDetectedQuadResult *> *)results {
    // Add your code to execute when quad results are detected. 
}
```
2. 
```swift
func detectResultCallback(_ frameId: Int, imageData: iImageData, results: [iDetectedQuadResult]) {
    // Add your code to execute when quad results are detected.
}
```