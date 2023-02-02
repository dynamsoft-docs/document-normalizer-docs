---
layout: default-layout
title: iOS Protocol DCECameraStateListener - Dynamsoft Camera Enhancer
description: This is the documentation - iOS Protocol DCECameraStateListener page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, iOS Protocol DCECameraStateListener
needAutoGenerateSidebar: true
noTitleIndex: true
needGenerateH3Content: false
breadcrumbText: iOS Protocol DCECameraStateListener
---

# DCECameraStateListener

The interface to handle callback when camera state changes.

```objc
@protocol DCECameraStateListener <NSObject>
```

| Method | Type | Description |
| ------ | ---- | ----------- |
| [`stateChangeCallback`](#statechangecallback) | *required* | The callback method is triggered when **camera state** changes. |

## stateChangeCallback

The callback method is triggered when **camera state** changes.

```objc
- (void)stateChangeCallback:(EnumCameraState)cameraState;
```

**Parameters**

`cameraState`: The camera state. It includes `opened`, `opening`, `closed` and `closing`.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface ViewController ()<DCECameraStateListener>
- (void)configurationDCE{
   [_dce setCameraStateListener:self];
}
- (void)stateChangeCallback:(EnumCameraState)state{
   // Add your code to do when camera state changes.
}
```
2. 
```swift
class ViewController: UIViewController,DCECameraStateListener{
   func configurationDCE(){
          dce.setCameraStateListener(self)
   }
   func stateChangeCallback(EnumCameraState currentState){
          // Add your code to do when camera state changes.
   }
}
```
