---
layout: default-layout
title: iOS DCEFeedback Class - Dynamsoft Document Normalizer Documents
description: This is the documentation - iOS DCEFeedback Class page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, iOS, DCEFeedback
needAutoGenerateSidebar: true
noTitleIndex: true
needGenerateH3Content: true
breadcrumbText: iOS DCEFeedback Class
---

# DCEFeedback

With DCEFeedback APIs, user can trigger feedback on the device to respond for some specific events.

```objc
@interface DCEFeedback : NSObject
```

| Method | Description |
| ------ | ----------- |
| [`vibrate`](#vibrate) | Trigger a vibration when the method is called. |
| [`beep`](#beep) | Trigger a beep when the method is called. |

## vibrate

Trigger a vibrate when the method is called.

```objc
+ (void)vibrate;
```

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
[DCEFeedback vibrate];
// For example, if `vibrate` is called in the TextResultCallback of DBR, the device will trigger a vibration each time when barcode result is detected.
- (void)textResultCallback:(NSInteger)frameId imageData:(iImageData *)imageData results:(NSArray<iTextResult *> *)results{
   [DCEFeedback vibrate];
}
```
2. 
```swift
DCEFeedback.vibrate
// For example, if `vibrate` is called in the TextResultCallback of DBR, the device will trigger a vibration each time when barcode result is detected.
func textResultCallback(_ frameId: Int, imageData: iImageData, results: [iTextResult]?) {
   DCEFeedback.beep()
}
```

## beep

Trigger a beep when the method is called.

```objc
+ (void)beep;
```

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
[DCEFeedback beep];
// For example, if `beep` is called in the TextResultCallback of DBR, the device will trigger a beep each time when barcode result is detected.
- (void)textResultCallback:(NSInteger)frameId imageData:(iImageData *)imageData results:(NSArray<iTextResult *> *)results{
   [DCEFeedback beep];
}
```
2. 
```swift
DCEFeedback.beep()
// For example, if `beep` is called in the TextResultCallback of DBR, the device will trigger a beep each time when barcode result is detected.
func textResultCallback(_ frameId: Int, imageData: iImageData, results: [iTextResult]?) {
   DCEFeedback.beep()
}
```
