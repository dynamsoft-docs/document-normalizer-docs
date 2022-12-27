---
layout: default-layout
title: Android DCEPhotoListener - Dynamsoft Document Normalizer Documents
description: This is the documentation - DCEPhotoListener page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, DCEPhotoListener
needAutoGenerateSidebar: true
noTitleIndex: true
needGenerateH3Content: true
breadcrumbText: DCEPhotoListener
---

# DCEPhotoListener

The interface that provide method for capturing photo from the camera.

```java
interface com.dynamsoft.dce.DCEPhotoListener
```

| Functions | Description |
| --------- | ----------- |
| [`photoOutputCallback`](#photooutputcallback) | The callback method for user to receive the captured photo. |

## photoOutputCallback

The callback method for user to receive the captured photo. User can complete the method by adding code to execute with the capture image.

```java
photoOutputCallback(byte[] bytes)
```

**Parameters**

`bytes`: The byte data of the captured image.

**Code Snippet**

```java
// Create an instance of DCEPhotoListener
DCEPhotoListener photoListener = new DCEPhotoListener() {
    @Override
    public void photoOutputCallback(byte[] bytes) {
        // Add your code to execute when photo is captured.
        // For example, you can use Dynamsoft Barcode Reader (DBR) to decode the byte image.
        try {
            BarcodeReader mReader = new BarcodeReader();
            mReader.decodeFileInMemory(bytes);
        } catch (BarcodeReaderException e) {
            e.printStackTrace();
        }
    }
};
// Since you have configured the photoOutputCallback.
// When you trigger takePhote method, the library firstly capture a photo
// When the photo is captured and stored in memory, it will be processed by DBR
mCameraEnhancer.takePhoto(photoListener);
```
