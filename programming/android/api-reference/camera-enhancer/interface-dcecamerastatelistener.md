---
layout: default-layout
title: Interface DCECameraStateListener - Dynamsoft Camera Enhancer
description: This is the documentation - DCECameraStateListener page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, DCECameraStateListener
needAutoGenerateSidebar: true
noTitleIndex: true
needGenerateH3Content: true
breadcrumbText: DCECameraStateListener
---

# DCECameraStateListener

The interface to handle callback when camera state changes.

```java
interface com.dynamsoft.dce.DCECameraStateListener
```

| Functions | Description |
| --------- | ----------- |
| [`stateChangeCallback`](#statechangecallback) | The callback method is triggered when **camera state** changes. |

## stateChangeCallback

The callback method is triggered when **camera state** changes.

```java
void stateChangeCallback(EnumCameraState currentState);
```

**Parameters**

`currentState`: The camera state. It includes `opened`, `opening`, `closed` and `closing`.

**Code Snippet**

```java
cameraEnhancer.setCameraStateListener(new DCECameraStateListener() {
    @Override
    public void stateChangeCallback(EnumCameraState currentState) {
        // Add your code to do when camera state changes
    }
});
```

**See also**

- [`setCameraStateListener`](../primary-api/camera-enhancer.md#setcamerastatelistener)
