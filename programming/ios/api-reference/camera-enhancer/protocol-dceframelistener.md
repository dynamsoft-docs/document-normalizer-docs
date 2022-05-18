---
layout: default-layout
title: Dynamsoft Camera Enhancer - iOS Protocol DCEFrameListener
description: This is the documentation - iOS Protocol DCEFrameListener page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, iOS Protocol DCEFrameListener
needAutoGenerateSidebar: true
noTitleIndex: true
needGenerateH3Content: false
breadcrumbText: iOS Protocol DCEFrameListener
---

# DCEFrameListener

The protocol to handle callback when previewed frame callback is returned.

```objc
@protocol CameraEnhancerListener <NSObject>
```

| Method | Type | Description |
| ------ | ---- | ----------- |
| [`frameOutPutCallback`](#frameoutputcallback) | *required* | Callback when the `DCEFrame` is output. |

## frameOutPutCallback

Callback when the `DCEFrame` is output.

```objc
- (void)frameOutPutCallback:(DCEFrame*)frame timeStamp:(NSTimeInterval)timeStamp;
```

**Parameters**

`frame`: The parameter is the original `DCEFrame` with detailed frame information. View more in [`DCEFrame`]({{ site.ios-api-auxiliary }}dceframe.html) class.  
`timeStamp`: The time stamp that records when the DCEFrame is output. 

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
[_dce addListener:self];

- (void)frameOutPutCallback:(DCEFrame *)frame timeStamp:(NSTimeInterval)timeStamp{
    // TODO add your code
}
```
2. 
```swift
dce.addListener(self)

func frameOutPutCallback(_ frame: DCEFrame, timeStamp: TimeInterval){
    // TODO add your code
}
```

**See also**

- [`DCEFrame`]({{ site.ios-api-auxiliary }}dceframe.html)
