---
layout: default-layout
title: iOS Protocol DCEPhotoListener
description: This is the documentation - iOS Protocol DCEPhotoListener page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, iOS Protocol DCEPhotoListener
needAutoGenerateSidebar: true
noTitleIndex: true
needGenerateH3Content: false
breadcrumbText: iOS Protocol DCEPhotoListener
---

# DCEPhotoListener

The interface that provide method for capturing photo from the camera.

```objc
@protocol DCEPhotoListener <NSObject>
```

| Method | Type | Description |
| ------ | ---- | ----------- |
| [`photoOutputCallback`](#photooutputcallback) | *required* | The callback method for user to receive the captured photo. |

## photoOutputCallback

The callback method for user to receive the captured photo. User can complete the method by adding code to execute with the capture image.

```objc
- (void)photoOutputCallback:(NSData *)jpegBytes;
```

**Parameters**

`jpegBytes` The byte data of the captured image.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface ViewController ()<DCEPhotoListener>
- (void)configurationDCE(){
   // When you trigger takePhote method, the library firstly capture a photo
   // When the photo is captured and stored in memory, it will be processed by DBR
   [_dce takePhoto:self]
}
- (void)photoOutputCallback:(NSData *)jpegBytes{
   // Add your code to execute when photo is captured.
   // For example, you can use Dynamsoft Barcode Reader (DBR) to decode the byte image.
   NSArray<iTextResult*> *barcodeResults = [_dbr decodeFileInMemory:jpegBytes error:nil];
}
```
2. 
```swift
class ViewController: UIViewController, DCEPhotoListener {
   func configurationDCE(){
          // When you trigger takePhote method, the library firstly capture a photo
          // When the photo is captured and stored in memory, it will be processed by DBR
          dce.takePhoto()
   }
   func photoOutputCallback(_ jpegByte: Data){
          // Add your code to execute when photo is captured.
          // For example, you can use Dynamsoft Barcode Reader (DBR) to decode the byte image.
          let barcodeResults = try? dbr.decodeFileInMemory(jpegByte)
   }
}
```
