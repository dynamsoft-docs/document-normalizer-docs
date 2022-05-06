---
layout: default-layout
title: Dynamsoft Document Normalizer for iOS - User Guide
description: This is the user guide of Dynamsoft Document Normalizer for iOS SDK.
keywords: user guide, iOS
needAutoGenerateSidebar: true
needGenerateH4Content: true
noTitleIndex: true
---

# Getting Started with iOS

## Requirements

- Operating systems:
  - macOS 10.11 and above.
  - iOS 9.0 and above.
- Environment: Xcode 7.1 - 11.5 and above.
- Recommended: macOS 10.15.4+, Xcode 11.5+, iOS 11+

## Installation

You can download the Dynamsoft Document Normalizer (DDN) SDK from the <a href="https://www.dynamsoft.com/document-normalizer/downloads/?utm_source=docs" target="_blank">Dynamsoft website</a> if you don't have the SDK installed yet.

After unzipping, the root directory of the DDN installation package is **DynamsoftDocumentNormalizer** (the `[INSTALLATION FOLDER]`). You can find the following **Frameworks** under the **[INSTALLATION FOLDER]\Frameworks** directory:

| File | Description |
|---------|-------------|
| `DynamsoftDocumentNormalizer.framework` <br /> `DynamsoftDocumentNormalizer.xcframework` | The Dynamsoft Document Normalizer SDK, including document normalizer related APIs. |
| `DynamsoftCore.framework` <br /> `DynamsoftCore.xcframework` | The core library of Dynamsoft's data capture SDKs, including common basic structure and license related APIs. |
| `DynamsoftIntermediateResult.framework` <br /> `DynamsoftIntermediateResult.xcframework` | The common intermediate result library of Dynamsoft's data capture SDKs, including all intermediate results produced in the process of decoding a barcode, recognizing a label or normalizing a document. |
| `DynamsoftImageProcessing.framework` <br /> `DynamsoftImageProcessing.xcframework` | The image processing library of Dynamsoft's data capture SDKs, including image processing algorithms and APIs. |
| `DynamsoftCameraEnhancer.framework` <br /> `DynamsoftCameraEnhancer.xcframework` | The Dynamsoft Camera Enhancer SDK, including camera control and frame preprocessing APIs.  |

## Build Your First Application

In this section, let's see how to create a HelloWorld app for normalizing documents from camera video input.

>Note:
>
> - Xcode 13.0 is used here in this guide.
> - You can get the source code of the HelloWord app from the following link
>   - [Objective-C](https://github.com/Dynamsoft/document-normalizer-mobile-samples/tree/main/ios/Objective-C/HelloWorld).
>   - [Swift](https://github.com/Dynamsoft/document-normalizer-mobile-samples/tree/main/ios/Swift/HelloWorld).

### Create a New Project

1. Open Xcode and select create a new project.

2. Select **iOS -> App** for your application.

3. Input your product name (Helloworld), interface (StoryBoard) and language (Objective-C/Swift). We currently do not support SwiftUI, so we apologize if this causes any inconvenience.

4. Click on the **Next** button and select the location to save the project.

5. Click on the **Create** button to finish.

### Include the Frameworks

You can add your downloaded frameworks into your project through the following steps:

1. Drag and drop the following frameworks into your Xcode project. Make sure to check Copy items if needed and Create groups to copy the framework into your project’s folder.

   - DynamsoftDocumentNormalizer.framework
   - DynamsoftCore.framework
   - DynamsoftIntermediateResult.framework
   - DynamsoftImageProcessing.framework
   - DynamsoftCameraEnhancer.framework

2. Click on the project settings then go to **General –> Frameworks, Libraries, and Embedded Content**. Set the **Embed** field to **Embed & Sign** for DynamsoftBarcodeReader and DynamsoftCameraEnhancer.
3. Import the headers in the ViewController file.

   ```objc
   #import <DynamsoftBarcodeReader/DynamsoftBarcodeReader.h>
   #import <DynamsoftCameraEnhancer/DynamsoftCameraEnhancer.h>
   ```

### Main ViewController for Realtime Detection of Quads

In the main view controller, your app will scan documents via video streaming and display the detect quadrilateral area on the screen.

#### Initialize License

1. Initialize the license first. It is suggested to initialize the license in `AppDelegate` file.

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   [DynamsoftCore initLicense:@"DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9" verificationDelegate:self];
   ```
   2. 
   ```swift
   ```

   >Note:  
   >  
   >- Network connection is required for the license to work.
   >- The license string here will grant you a time-limited trial license.
   >- If the license has expired, you can go to the <a href="https://www.dynamsoft.com/customer/license/trialLicense?utm_source=docs" target="_blank">customer portal</a> to request for an extension.

#### Get Prepared with the Camera Module

1. Be sure that you have included `DynamsoftCameraEnhancer.h` in your project before you start to work with `DynamsoftCameraEnhancer`.

   ```objc
   #import <DynamsoftCameraEnhancer/DynamsoftCameraEnhancer.h>
   ```

2. Create the instances of `CameraEnhancer` and `CameraView`.

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   @property(nonatomic, strong) DynamsoftCameraEnhancer *dce;
   @property(nonatomic, strong) DCECameraView *dceView;
   ...
   - (void)configurationDCE{
      _dceView = [DCECameraView cameraWithFrame:self.view.bounds];
      [self.view addSubview:_dceView];
      _dce = [[DynamsoftCameraEnhancer alloc] initWithView:_dceView];
   }
   ```
   2. 
   ```swift
   ```

#### Initialize Document Normalizer

1. Include and initialize the `DynamsoftDocumentNormalizer`, bind to the created `CameraEnhancer` instance.

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   @property(nonatomic, strong) DynamsoftDocumentNormalizer *ddn;
   ...
   - (void)configurationDDN{
      _ddn = [[DynamsoftDocumentNormalizer alloc] init];
   }
   ```
   2. 
   ```swift
   ```

2. Add `DetectResultListener` to your ViewController and register with the `DocumentNormalizer` instance to get detected quad results.

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   // Add DetectResultListener to the ViewController
   @interface ViewController ()<DetectResultListener>
   - (void)configurationDDN{
      _ddn = [[DynamsoftDocumentNormalizer alloc] init];
      // Bind the DocumentNormalizer and CameraEnhancer instance
      [_ddn setCameraEnhancer:_dce];
      [_ddn setDetectResultListener:self];
      [_ddn startDetecting];
   }
   ```
   2. 
   ```swift
   ```

3. Add configurations to start detecting or stop detecting when the view appear or disappear.

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   - (void)viewWillAppear:(BOOL)animated
   {
      [super viewWillAppear:animated];
      [[StaticClass instance].ddn startDetecting];
   }
   - (void)viewWillDisappear:(BOOL)animated
   {
      [super viewWillDisappear:animated];
      [[StaticClass instance].ddn stopDetecting];
   }
   ```
   2. 
   ```swift
   ```

#### Additional Steps in `ViewController`

When the detected quadrilateral results are satisfied, we can move on to mannually adjust the edge and normalize the document area. In this step, we will add a button on the main view to confirm and go to the quadrilateral editing view.

1. Add a button on the view.

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   - (void)configurationUI{
      CGFloat w = [[UIScreen mainScreen] bounds].size.width;
      CGFloat h = [[UIScreen mainScreen] bounds].size.height;
      CGFloat SafeAreaBottomHeight = [[UIApplication sharedApplication] statusBarFrame].size.height > 20 ? 34 : 0;
      confirmButton = [[UIButton alloc] initWithFrame:CGRectMake(w / 2 - 60, h - 170 - SafeAreaBottomHeight, 120, 120)];
      confirmButton.adjustsImageWhenDisabled = NO;
      [confirmButton setImage:[UIImage imageNamed:@"icon_capture"] forState:UIControlStateNormal];
      [confirmButton addTarget:self action:@selector(takePictures) forControlEvents:UIControlEventTouchUpInside];
      dispatch_async(dispatch_get_main_queue(), ^{
         [self.view addSubview:self->confirmButton];
      });
   }
   ```
   2. 
   ```swift
   ```

2. Set the flag to start quad edit activity.

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   - (void)takePictures{
      isview = true;
   }
   ```
   2. 
   ```swift
   ```

### QuadEditActivity for Interactive Editing of Quads

#### Initialize the Image Editor View

In this section, we are going to create a view that displays the original image and editable quadrilaterals. User can select adjust the edge of the quadrilateral before normalizing the document area.

1. Create a new empty activity named `QuadEditViewController`.

2. Include and initialize the `DCEImageEditorView` in the file `QuadEditViewController`.

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   - (void)setImageEditorView{
      // Initialize the instance of DCEImageEditorView.
      editorView = [[DCEImageEditorView alloc] initWithFrame:CGRectMake(0, 0, self.view.frame.size.width, self.view.frame.size.height)];
      // Set the image of the view.
      // The image that displayed on the DCEImageEditorView will be used as the original image for normalizing.
      [editorView setOriginalImage:[StaticClass instance].imageData];
      // Set the DCEImageEditorView as the subview.
      [self.view addSubview:editorView];
   }
   ```
   2. 
   ```swift
   ```

3. Add detected quadrilaterals on the `DCEImageEditorView`.

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   - (void)setImageEditorView{
      // Select the preset layer of DynamsoftDocumentNormalizer.
      layer = [editorView getDrawingLayer:`DDN_LAYER_ID`];
      // Create QuadDrawingItems with the detected quadrilateral results and add them to DDN layer.
      NSMutableArray<DrawingItem *> *array = [NSMutableArray array];
      for (iDetectedQuadResult *detectedQuadResult in [StaticClass instance].quadArr) {
         iQuadrilateral *quad = detectedQuadResult.location;
         QuadDrawingItem *quadItem = [[QuadDrawingItem alloc] initWithQuad:quad];
         [array addObject:quadItem];
      }
      layer.drawingItems = array;
   }
   ```
   2. 
   ```swift
   ```

#### Normalize With the Selected Quad

In the section, we will add code to get the user selected quadrilateral and normalize the document area based on the selected quad.

1. Add a **normalize** button on the view.

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   - (void)setButton{
      CGFloat w = [[UIScreen mainScreen] bounds].size.width;
      CGFloat h = [[UIScreen mainScreen] bounds].size.height;
      CGFloat SafeAreaBottomHeight = [[UIApplication sharedApplication] statusBarFrame].size.height > 20 ? 34 : 0;
      UIButton *button = [[UIButton alloc] initWithFrame:CGRectMake(w / 2 - 60, h - 170 - SafeAreaBottomHeight, 120, 120)];
      [button setImage:[UIImage imageNamed:@"icon_capture"] forState:UIControlStateNormal];
      [button addTarget:self action:@selector(takePictures)   forControlEvents:UIControlEventTouchUpInside];
      [self.view addSubview:button];
   }
   ```
   2. 
   ```swift
   ```

2. When the `Normalize` button is clicked, the image will be normalized with the selected quad and the result view controller will be launched.

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   - (void)startNormalize{
      // Get the selected QuadDrawingItem
      QuadDrawingItem *item = (QuadDrawingItem *)[editorView getSelectedDrawingItem];
      NSError *error = [NSError new];
      // Normalize the image based on the selected quad.
      iNormalizedImageResult *imageData = [[StaticClass instance].ddn normalizeBuffer:  [StaticClass instance].imageData quad:item.quad error:&error];
      // Get the image data of the normalized image.
      [StaticClass instance].binaryImage = imageData.image.toUIImage;
      // Go to the ViewController that displays the normalized image.
      dispatch_async(dispatch_get_main_queue(), ^{
         [self performSegueWithIdentifier:@"pushImageView" sender:nil];
      });
   }
   ```
   2. 
   ```swift
   ```

### ResultViewController for Displaying the Normalized Image

#### Diplay the Normalized Image

1. Create a new empty activity named `ResultViewController`.

2. Display the normalized image.

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   #import "ImageViewController.h"
   #import "StaticClass.h"
   @interface ImageViewController ()
   @end
   @implementation ImageViewController
   @synthesize imageView;
   - (void)viewDidLoad {
      [super viewDidLoad];
      [self setUI];
   }
   - (void)setUI{
      self.view.backgroundColor = [UIColor blackColor];
      CGFloat w = [[UIScreen mainScreen] bounds].size.width;
      CGFloat h = [[UIScreen mainScreen] bounds].size.height;
      imageView = [[UIImageView alloc] initWithFrame:CGRectMake(0, 0, w, h)];
      imageView.userInteractionEnabled = YES;
      imageView.contentMode = UIViewContentModeScaleAspectFit;
      [self->imageView setImage:[StaticClass instance].binaryImage];
      [self.view addSubview:self->imageView];
   }
   @end
   ```
   2. 
   ```swift
   ```

### Build and Run the Project

1. Select the device that you want to run your app on.
2. Run the project, then your app will be installed on your device.

> Note:
>
> - You can get the source code of the HelloWord app from the following link
>   - [Objective-C](https://github.com/Dynamsoft/document-normalizer-mobile-samples/tree/main/ios/Objective-C/HelloWorld).
>   - [Swift](https://github.com/Dynamsoft/document-normalizer-mobile-samples/tree/main/ios/Swift/HelloWorld).
