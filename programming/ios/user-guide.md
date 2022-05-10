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
| ---- | ----------- |
| `DynamsoftDocumentNormalizer.framework` <br /> `DynamsoftDocumentNormalizer.xcframework` | The Dynamsoft Document Normalizer SDK, including document normalizer related APIs. |
| `DynamsoftCore.framework` <br /> `DynamsoftCore.xcframework` | The core library of Dynamsoft's data capture SDKs, including common basic structure and license related APIs. |
| `DynamsoftIntermediateResult.framework` <br /> `DynamsoftIntermediateResult.xcframework` | The common intermediate result library of Dynamsoft's data capture SDKs, including all intermediate results produced in the process of decoding a barcode, recognizing a label or normalizing a document. |
| `DynamsoftImageProcessing.framework` <br /> `DynamsoftImageProcessing.xcframework` | The image processing library of Dynamsoft's data capture SDKs, including image processing algorithms and APIs. |
| `DynamsoftCameraEnhancer.framework` <br /> `DynamsoftCameraEnhancer.xcframework` | The Dynamsoft Camera Enhancer SDK, including camera control and frame preprocessing APIs. |

## Build Your First Application

In this section, let's see how to create a HelloWorld app for normalizing documents from camera video input.

>Note:
>
> - Xcode 13.0 is used here in this guide.
> - You can get the source code of the HelloWord app from the following link
>   - [Objective-C](https://github.com/Dynamsoft/document-normalizer-mobile-samples/tree/main/ios/Objective-C/HelloWorld).
>   - [Swift](https://github.com/Dynamsoft/document-normalizer-mobile-samples/tree/main/ios/Swift/HelloWorld).

&nbsp;

### Create a New Project

1. Open Xcode and select create a new project.

2. Select **iOS -> App** for your application.

3. Input your product name (Helloworld), interface (StoryBoard) and language (Objective-C/Swift). We currently do not support SwiftUI, so we apologize if this causes any inconvenience.

4. Click on the **Next** button and select the location to save the project.

5. Click on the **Create** button to finish.

&nbsp;

### Include the Frameworks

You can add your downloaded frameworks into your project through the following steps:

1. Drag and drop the following frameworks into your Xcode project. Make sure to check Copy items if needed and Create groups to copy the framework into your project’s folder.

   - **DynamsoftDocumentNormalizer.framework**
   - **DynamsoftCore.framework**
   - **DynamsoftIntermediateResult.framework**
   - **DynamsoftImageProcessing.framework**
   - **DynamsoftCameraEnhancer.framework**

2. Click on the project settings then go to **General –> Frameworks, Libraries, and Embedded Content**. Set the **Embed** field to **Embed & Sign** for DynamsoftDocumentNormalizer and DynamsoftCameraEnhancer.

&nbsp;

### Main ViewController for Realtime Detection of Quads

In the main view controller, your app will scan documents via video streaming and display the detect quadrilateral area on the screen. First of all, import the headers in the ViewController file.

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   #import <DynamsoftDocumentNormalizer/DynamsoftDocumentNormalizer.h>
   #import <DynamsoftCameraEnhancer/DynamsoftCameraEnhancer.h>
   ```
   2. 
   ```swift
   import DynamsoftCameraEnhancer
   import DynamsoftDocumentNormalizer
   ```

#### Initialize License

Initialize the license first. It is suggested to initialize the license in `AppDelegate` file.

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
   DynamsoftCore.initLicense("DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9", self)
   ```

>Note:  
>  
>- Network connection is required for the license to work.
>- The license string here will grant you a time-limited trial license.
>- If the license has expired, you can go to the <a href="https://www.dynamsoft.com/customer/license/trialLicense?utm_source=docs" target="_blank">customer portal</a> to request for an extension.

#### Get Prepared with the Camera Module

Create the instances of `CameraEnhancer` and `CameraView`.

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   @property(nonatomic, strong) DynamsoftCameraEnhancer *dce;
   @property(nonatomic, strong) DCECameraView *dceView;
   ...
   - (void)configDCE{
          _dceView = [DCECameraView cameraWithFrame:self.view.bounds];
          [self.view addSubview:_dceView];
          _dce = [[DynamsoftCameraEnhancer alloc] initWithView:_dceView];
   }
   ```
   2. 
   ```swift
   private var dce: DynamsoftCameraEnhancer!
   private var dceView: DCECameraView!
   ...
   func configDCE() {
          dceView = DCECameraView(frame: view.bounds)
          view.addSubview(dceView)
          dce = DynamsoftCameraEnhancer(view: dceView)
   }
   ```

#### Initialize Document Normalizer

1. Include and initialize the `DynamsoftDocumentNormalizer`, bind to the created `CameraEnhancer` instance.

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   - (void)configDDN{
      [StaticClass instance].ddn = [DynamsoftDocumentNormalizer new];
      // Bind the DocumentNormalizer and CameraEnhancer instance
      [[StaticClass instance].ddn setCameraEnhancer:_dce];
   }
   ```
   2. 
   ```swift
   func configDDN() {
      StaticClass.instance.ddn = DynamsoftDocumentNormalizer()
      StaticClass.instance.ddn.setCameraEnhancer(dce)
   }
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
   ...
   - (void)configDDN{
      [StaticClass instance].ddn = [DynamsoftDocumentNormalizer new];
      [[StaticClass instance].ddn setCameraEnhancer:_dce];
      // Set the detect result listener first.
      [[StaticClass instance].ddn setDetectResultListener:self];
   }
   // Add detectResultCallback method in the view controller.
   - (void)detectResultCallback:(NSInteger)frameId imageData:(nonnull iImageData *)imageData results:(nonnull NSArray<iDetectedQuadResult *> *)results {
      // We will add code here to deal with the detection result and open another view controller.
   }
   ```
   2. 
   ```swift
   class ViewController: UIViewController, DetectResultListener{
      ...
      func configDDN() {
             StaticClass.instance.ddn = DynamsoftDocumentNormalizer()
             StaticClass.instance.ddn.setCameraEnhancer(dce)
             StaticClass.instance.ddn.setDetectResultListener(self)
      }
      func detectResultCallback(_ frameId: Int, imageData: iImageData, results: [iDetectedQuadResult]) {
             // We will add code here to deal with the detection result and open another view controller.
      }
   }
   ```

3. Add the methods to run when the view is loaded.

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   - (void)viewDidLoad {
      [super viewDidLoad];
      [self configDDN];
      [self configDCE];
      [self configUI];
   }
   ```
   2. 
   ```swift
   override func viewDidLoad() {
      super.viewDidLoad()
      configDDN()
      configDCE()
      configUI()
   }
   ```

4. Add configurations to start detecting or stop detecting when the view appear or disappear.

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
   override func viewWillAppear(_ animated: Bool) {
      super.viewWillAppear(animated)
      StaticClass.instance.ddn.startDetecting()
   }
   override func viewWillDisappear(_ animated: Bool) {
      super.viewWillDisappear(animated)
      StaticClass.instance.ddn.stopDetecting()
   }
   ```

#### Additional Steps in `ViewController`

When the detected quadrilateral results are satisfied, we can move on to mannually adjust the edge and normalize the document area. In this step, we will add a button on the main view to confirm and go to the quadrilateral editing view.

1. Add code in detectResultCallback to get detected quad results continuously. Once the "**start editing**" commend is triggered, the `QuadEditViewController` view will be launched.

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   - (void)detectResultCallback:(NSInteger)frameId imageData:(nonnull iImageData *)imageData results:(nonnull NSArray<iDetectedQuadResult *> *)results {
      if (isview && results) {
             isview = false;
             [StaticClass instance].quadArr = results;
             [StaticClass instance].imageData = imageData;
             dispatch_async(dispatch_get_main_queue(), ^{
                [self performSegueWithIdentifier:@"pushQuadEditView" sender:nil];
             });
      }
   }
   ```
   2. 
   ```swift
   func detectResultCallback(_ frameId: Int, imageData: iImageData, results: [iDetectedQuadResult]) {
      if startEditing && !results.isEmpty {
             startEditing = false
             StaticClass.instance.quadArr = results
             StaticClass.instance.imageData = imageData
             DispatchQueue.main.async(execute: { [self] in
                performSegue(withIdentifier: "pushQuadEditView", sender: nil)
             })
      }
   }
   ```

2. Add the button to trigger the "**start editing**" commend.

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   bool startEditing = false
   ...
   - (void)takePictures{
      startEditing = true;
   }
   // Configure the button on the UI.
   - (void)configUI{
      CGFloat w = [[UIScreen mainScreen] bounds].size.width;
      CGFloat h = [[UIScreen mainScreen] bounds].size.height;
      CGFloat SafeAreaBottomHeight = [[UIApplication sharedApplication] statusBarFrame].size.height > 20 ? 34 : 0;
      photoButton = [[UIButton alloc] initWithFrame:CGRectMake(w / 2 - 60, h - 100 - SafeAreaBottomHeight, 120, 60)];
      [photoButton setTitle:@"Capture" forState:UIControlStateNormal];
      [photoButton setBackgroundColor:[UIColor greenColor]];
      [photoButton addTarget:self action:@selector(takePictures) forControlEvents:UIControlEventTouchUpInside];
      dispatch_async(dispatch_get_main_queue(), ^{
             [self.view addSubview:self->photoButton];
      });
   }
   ```
   2. 
   ```swift
   private var startEditing = false
   ...
   @objc func takePictures() {
      startEditing = true
   }
   // Configure the button on the UI.
   func configUI() {
      let w = UIScreen.main.bounds.size.width
      let h = UIScreen.main.bounds.size.height
      let SafeAreaBottomHeight: CGFloat = UIApplication.shared.statusBarFrame.size.height > 20 ? 34 : 0
      let photoButton = UIButton(frame: CGRect(x: w / 2 - 60, y: h - 100 - SafeAreaBottomHeight, width: 120, height: 60))
      photoButton.setTitle("Capture", for: .normal)
      photoButton.backgroundColor = UIColor.green
      photoButton.addTarget(self, action: #selector(takePictures), for: .touchUpInside)
      DispatchQueue.main.async(execute: { [self] in
             view.addSubview(photoButton)
      })
   }
   ```

&nbsp;

### QuadEditViewController for Interactive Editing of Quads

#### Initialize the Image Editor View

In this section, we are going to create a view that displays the original image and editable quadrilaterals. User can select adjust the edge of the quadrilateral before normalizing the document area.

1. Create a new empty activity named `QuadEditViewController` and import `DynamsoftCameraEnhancer`.

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   #import <DynamsoftCameraEnhancer/DynamsoftCameraEnhancer.h>
   ```
   2. 
   ```swift
   import DynamsoftCameraEnhancer
   ```

2. Initialize the `DCEImageEditorView` in the file `QuadEditViewController`.

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   @implementation QuadEditViewController{
      DCEImageEditorView *editorView;
      DCEDrawingLayer* layer;
   }
   - (void)configImageEditorView {
      // Initialize the DCEImageEditorView.
      editorView = [[DCEImageEditorView alloc] initWithFrame:CGRectMake(0, 0, self.view.frame.size.width, self.view.frame.size.height)];
      // Set the image that will be normalized.
      [editorView setOriginalImage:[StaticClass instance].imageData];
      [self.view addSubview:editorView];
   }
   ```
   2. 
   ```swift
   private var editorView: DCEImageEditorView!
   private var layer: DCEDrawingLayer!
   func configImageEditorView() {
      // Initialize the DCEImageEditorView.
      editorView = DCEImageEditorView(frame: CGRect(x: 0, y: 0, width: view.frame.size.width, height: view.frame.size.height))
      // Set the image that will be normalized.
      editorView.setOriginalImage(StaticClass.instance.imageData)
      view.addSubview(editorView)
   }
   ```

3. Add detected quadrilaterals on the `DCEImageEditorView`.

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   @implementation QuadEditViewController{
      DCEImageEditorView *editorView;
      DCEDrawingLayer* layer;
   }
   - (void)configImageEditorView {
      ...
      // Select DDN_LAYER to display the quadrilateral of document areas.
      // The quadrilaterals that are displayed on the DCEImageEditorView can be edited on the UI.
      layer = [editorView getDrawingLayer:DDN_LAYER_ID];
      // Create an array of DrawingItems and assign it to the drawingItems property.
      NSMutableArray<DrawingItem *> *array = [NSMutableArray array];
      for (iDetectedQuadResult *detectedQuadResult in [StaticClass instance].quadArr) {
             iQuadrilateral *quad = detectedQuadResult.location;
             QuadDrawingItem *quadItem = [[QuadDrawingItem alloc] initWithQuad:quad];
             [array addObject:quadItem];
      }
      layer.drawingItems = array;
      [self.view addSubview:editorView];
   }
   ```
   2. 
   ```swift
   private var editorView: DCEImageEditorView!
   private var layer: DCEDrawingLayer!
   func configImageEditorView() {
      // Select DDN_LAYER to display the quadrilateral of document areas.
      // The quadrilaterals that are displayed on the DCEImageEditorView can be edited on the UI.
      layer = editorView.getDrawingLayer(Int(DDN_LAYER_ID))
      // Create an array of DrawingItems and assign it to the drawingItems property.
      var array: [DrawingItem]? = []
      for detectedQuadResult in StaticClass.instance.quadArr {
             let quad = detectedQuadResult.location
             let quadItem = QuadDrawingItem(quad: quad)
             array?.append(quadItem)
      }
      layer.drawingItems = array
      view.addSubview(editorView)
   }
   ```

#### Normalize the Image with the Selected Quad

In the section, we will add code to get the user selected quadrilateral and normalize the document area based on the selected quad.

1. Add a method to normalize the image.

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   - (void)normalizeImage{
      // Get the selected QuadDrawingItem
      QuadDrawingItem *item = (QuadDrawingItem *)[editorView getSelectedDrawingItem];
      if(nil == item) {
             item = (QuadDrawingItem *)layer.drawingItems[0];
      }
      NSError *error;
      // Normalize the image based on the selected quad.
      iNormalizedImageResult *imageData = [[StaticClass instance].ddn normalizeBuffer:[StaticClass instance].imageData quad:item.quad error:&error];
      // Get the image data of the normalized image.
      [StaticClass instance].resultImage = imageData.image.toUIImage;
      dispatch_async(dispatch_get_main_queue(), ^{
             [self performSegueWithIdentifier:@"pushResultView" sender:nil];
      });
   }
   ```
   2. 
   ```swift
   @objc func normalizeImage() {
      // Get the selected QuadDrawingItem
      var item = editorView.getSelectedDrawingItem() as? QuadDrawingItem
      if nil == item {
             item = layer.drawingItems?[0] as? QuadDrawingItem
      }
      // Normalize the image based on the selected quad.
      let imageData = try? StaticClass.instance.ddn.normalizeBuffer(StaticClass.instance.imageData, quad: item!.quad)
      // Get the image data of the normalized image.
      StaticClass.instance.resultImage = imageData?.image.toUIImage()
      DispatchQueue.main.async(execute: { [self] in
             performSegue(withIdentifier: "pushResultView", sender: nil)
      })
   }
   ```

2. Add a button on the view to trigger the normalization of the image and launch the `ResultViewController`.

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   - (void)configUI{
      CGFloat w = [[UIScreen mainScreen] bounds].size.width;
      CGFloat h = [[UIScreen mainScreen] bounds].size.height;
      CGFloat SafeAreaBottomHeight = [[UIApplication sharedApplication] statusBarFrame].size.height > 20 ? 34 : 0;
      UIButton *button = [[UIButton alloc] initWithFrame:CGRectMake(w / 2 - 60, h - 100 - SafeAreaBottomHeight, 120, 60)];
      [button setTitle:@"Normalize" forState:UIControlStateNormal];
      [button setBackgroundColor:[UIColor greenColor]];
      [button addTarget:self action:@selector(normalizeImage) forControlEvents:UIControlEventTouchUpInside];
      [self.view addSubview:button];
   }
   ```
   2. 
   ```swift
   func configUI() {
      let w = UIScreen.main.bounds.size.width
      let h = UIScreen.main.bounds.size.height
      let SafeAreaBottomHeight: CGFloat = UIApplication.shared.statusBarFrame.size.height > 20 ? 34 : 0
      let button = UIButton(frame: CGRect(x: w / 2 - 60, y: h - 100 - SafeAreaBottomHeight, width: 120, height: 60))
      button.setTitle("Normalize", for: .normal)
      button.backgroundColor = UIColor.green
      button.addTarget(self, action: #selector(normalizeImage), for: .touchUpInside)
      view.addSubview(button)
   }
   ```

3. In viewDidLoad, add all the methods to trigger when `QuadEditorViewController` is loaded.

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   - (void)viewDidLoad {
      [super viewDidLoad];
      [self configImageEditorView];
      [self configUI];
   }
   ```
   2. 
   ```swift
   override func viewDidLoad() {
      super.viewDidLoad()
      configImageEditorView()
      configUI()
   }
   ```

&nbsp;

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
   @interface ResultViewController ()
   @end
   @implementation ResultViewController
   @synthesize imageView;
   - (void)viewDidLoad {
      [super viewDidLoad];
      [self configResultView];
   }
   - (void)configResultView{
      self.view.backgroundColor = [UIColor blackColor];
      CGFloat w = [[UIScreen mainScreen] bounds].size.width;
      CGFloat h = [[UIScreen mainScreen] bounds].size.height;
      imageView = [[UIImageView alloc] initWithFrame:CGRectMake(0, 0, w, h)];
      imageView.userInteractionEnabled = YES;
      imageView.contentMode = UIViewContentModeScaleAspectFit;
      [imageView setImage:[StaticClass instance].resultImage];
      [self.view addSubview:self->imageView];
   }
   ```
   2. 
   ```swift
   class ResultViewController : UIViewController {
      private var imageView: UIImageView!
      override func viewDidLoad() {
             super.viewDidLoad()
             configResultView()
      }
      func configResultView() {
             view.backgroundColor = UIColor.black
             let w = UIScreen.main.bounds.size.width
             let h = UIScreen.main.bounds.size.height
             imageView = UIImageView(frame: CGRect(x: 0, y: 0, width: w, height: h))
             imageView.isUserInteractionEnabled = true
             imageView.contentMode = .scaleAspectFit
             imageView.image = StaticClass.instance.resultImage
             view.addSubview(imageView)
      }
   }
   ```

&nbsp;

### Build and Run the Project

1. Select the device that you want to run your app on.
2. Run the project, then your app will be installed on your device.

> Note:
>
> - You can get the source code of the HelloWord app from the following link
>   - [Objective-C](https://github.com/Dynamsoft/document-normalizer-mobile-samples/tree/main/ios/Objective-C/HelloWorld).
>   - [Swift](https://github.com/Dynamsoft/document-normalizer-mobile-samples/tree/main/ios/Swift/HelloWorld).
