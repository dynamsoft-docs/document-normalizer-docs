---
layout: default-layout
title: Dynamsoft Document Normalizer iOS API Reference - Video Detecting Methods
description: This page shows Video Detecting methods of Dynamsoft Document Normalizer for iOS SDK.
keywords: Video Detecting methods, DynamsoftCameraEnhancer, api reference, ios
needAutoGenerateSidebar: true
noTitleIndex: true
pageStartVer: 1.0
---


# Video Detecting Methods

> Note:
>  
> - You have to include `DynamsoftCameraEnhancer` when using **Video Detecting Methods**.  
> - `DynamsoftCameraEnhancer` provide APIs that help you quickly deploy a camera module and capture video streaming for document normalizer.  
> - Through **Video Detecting Methods** you can control whether to start video streaming document detecting and get the detection results.  

| Method | Description |
|--------|-------------|
| [`setImageSource`](#setimagesource) | Sets an instance of ImageSource to get images.  |
| [`startDetecting`](#startdetecting) | Start the document quad detection thread in the video streaming scenario. |
| [`stopDetecting`](#stopdetecting) | Stop the document quad detection thread in the video streaming scenario. |
| [`setDetectResultListener`](#setdetectresultlistener) | Set callback interface to process detection results generated during frame detecting. |

---

## setImageSource

Sets an instance of ImageSource to get images. `DynamsoftCameraEnhancer` is a specific implementation of ImageSource, which can help the Document Normalizer to acquire video frames continuously for recognition.

```objc
- (void)setImageSource:(ImageSource* _Nonnull)source;
```

**Parameters**

`[in] source`: An instance of ImageSource. If you are using `Dynamsoft Camera Enhancer`(DCE) to capture camera frames, pass an instance of `DynamsoftCameraEnhancer`.

**Code Snippet**

This code snippet displays a complete code on how to add CameraEnhancer to your project, start detecting and get detection results from the video streaming.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface ViewController ()<DetectResultListener>
@property(nonatomic, strong) DynamsoftDocumentNormalizer *ddn;
@property(nonatomic, strong) DynamsoftCameraEnhancer *dce;
@property(nonatomic, strong) DCECameraView *dceView;
@end
@implementation ViewController
- (void)viewDidLoad{
    [super viewDidLoad];
    [self configurationDDN];
}
- (void)configurationDDN{
    _ddn =  [[DynamsoftDocumentNormalizer alloc] init];
    _dceView = [DCECameraView cameraWithFrame:self.view.bounds];
    [self.view addSubview:_dceView];
    _dce = [[DynamsoftCameraEnhancer alloc] initWithView:_dceView];
    [_dce open];
    [_ddn setImageSource:_dce];
    [_ddn setDetectResultListener:self];
    [_ddn startDetecting];
}
- (void)detectResultCallback:(NSInteger)frameId imageData:(iImageData *)imageData results:(NSArray<iDetectQuadResult *> *)results{
    // Add your code to do when barcode result is returned.
}
```
2. 
```swift
class ViewController: UIViewController, DetectResultListener{
    var SafeAreaBottomHeight:CGFloat = UIApplication.shared.statusBarFrame.size.height > 20 ? 34 : 0
    var mainHeight = UIScreen.main.bounds.height
    var mainWidth = UIScreen.main.bounds.width
    var dce:DynamsoftCameraEnhancer! = nil
    var dceView:DCECameraView! = nil
    var ddn:DynamsoftDocumentNormalizer! = nil
    override func viewDidLoad() {
        super.viewDidLoad()
        configurationDDN()
    }
    func configurationDDN(){
        ddn = DynamsoftDocumentNormalizer()
        var barHeight = self.navigationController?.navigationBar.frame.height
        if UIApplication.shared.statusBarFrame.size.height <= 20 {
            barHeight = 20
        }
        dceView = DCECameraView(frame: CGRect(x: 0, y: barHeight!, width: mainWidth, height: mainHeight - SafeAreaBottomHeight - barHeight!))
        self.view.addSubview(dceView)
        dce = DynamsoftCameraEnhancer(view: dceView)
        dce.open()
        ddn.setImageSource(dce)
        ddn.setDetectResultListener(self)
        ddn.startDetecting()
    }
    func detectResultCallback(_ frameId: Int, imageData: iImageData, results: [iDetectQuadResult]?){
        // Add your code
    }
}
```

## startDetecting

Start the document quad detection thread in the video streaming scenario. Please be sure that you have bound a Camera Enhancer to the document normalizer before you trigger `startDetecting`.

```objc
-(void)startDetecting
```

**Code Snippet**

You can view the complete code snippet in [`setImageSource`](#setimagesource).

## stopDetecting

Stop the document quad detection thread in the video streaming scenario.

```objc
-(void)stopDetecting
```

**Code Snippet**

You can view the complete code snippet in [`setImageSource`](#setimagesource).

## setDetectResultListener

Set the callback interface to process detection results generated during frame detecting.

```objc
-(void)setDetectResultListener:(id<DetectResultListener>)detectResultListener;
```

**Parameters**

`[in] detectResultListener`: The Callback interface.

**Code Snippet**

You can view the complete code snippet in [`setImageSource`](#setimagesource).
