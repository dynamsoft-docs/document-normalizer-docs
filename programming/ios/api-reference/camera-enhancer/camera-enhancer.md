---
layout: default-layout
title: iOS CameraEnhancer Class - Dynamsoft Document Normalizer Documents
description: This is the documentation - iOS API references - CameraEnhancer Class page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, iOS API references, CameraEnhancer Class
needAutoGenerateSidebar: true
noTitleIndex: true
needGenerateH3Content: true
breadcrumbText: iOS CameraEnhancer Class
---

# DynamsoftCameraEnhancer Class

The main class of `DynamsoftCameraEnhancer`. It contains APIs that enable user to:

- Implement basic camera control like open, close, change resolution, etc.
- Get frames from the video streaming.
- Enable advanced features including:
  - Frame filtering by sharpness
  - Frame filtering by sensor
  - Enhanced focus
  - Frame cropping
  - Auto zoom
  - Smart torch control

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface DynamsoftCameraEnhancer:NSObject<ImageSource>
```
2. 
```swift
class DynamsoftCameraEnhancer : NSObject, ImageSource
```

## Initialization Methods Summary

| Method | Description |
| ------ | ----------- |
| [`initWithView`](#initwithview) | Initialize the camera enhancer with the camera view |
| [`getVersion`](#getversion) | Get the SDK version. |
| [`cameraView`](#cameraview) | Bind a `DCECameraView` to the camera enhancer. |

## Basic Camera Control Methods Summary

| Method | Description |
| ------ | ----------- |
| [`getAllCameras`](#getallcameras) | Get all available cameras. This method returns a list of available camera IDs. |
| [`selectCameraWithPosition`](#selectcamerawithposition) | Select whether to use front-facing camera or back-facing camera. |
| [`getCameraPosition`](#getcameraposition) | Returns whether the front-facing camera or back-facing camera is selected. |
| [`selectCamera`](#selectcamera) | Select a camera from the camera list with the camera ID. |
| [`getSelectedCamera`](#getselectedcamera) | Get the camera ID of the current selected camera. |
| [`getCameraState`](#getcamerastate) | Get the state of the current selected camera. |
| [`open`](#open) | Turn on the current selected camera. |
| [`close`](#close) | Turn off the current selected camera. |
| [`turnOnTorch`](#turnontorch) | Turn on the torch. |
| [`turnOffTorch`](#turnofftorch) | Turn off the torch. |
| [`getFrameRate`](#getframerate) | Get the current frame rate. |
| [`setResolution`](#setresolution) | Set the resolution to the input value (if the input value is available for the device). |
| [`getResolution`](#getresolution) | Get the current resolution. |
| [`setZoom`](#setzoom) | Set the zoom factor. Once **setZoom** is triggered and approved, the zoom factor of the activated camera will immediately become the input value. |
| [`autoZoomRange`](#autozoomrange) | The property for getting/setting the range of auto zoom. |
| [`getMaxZoomFactor`](#getmaxzoomfactor) | Get the maximum available zoom factor. |
| [`setFocus`](#setfocus) | Set the focus position (value range from 0.0f to 1.0f) and trigger a focus at the configured position. |
| [`setFocus(subsequentFocusMode)`](#setfocussubsequentfocusmode) | Trigger a focus at the targeting point and set the subsequent focus mode after focused.  |
| [`setScanRegion`](#setscanregion) | Set the **scanRegion** with a [`iRegionDefinition`](region-definition.md) value. The frame will be cropped according to the scan region. |
| [`getScanRegion`](#getscanregion) | Get the scan region. |
| [`scanRegionVisible`](#scanregionvisible) | Set whether to display the **scanRegion** on the UI. |
| [`setCameraStateListener`](#setcamerastatelistener) | Add a `DCECameraStateListener` to receive notification when the camera state changes. |

## Frame Acquiring Methods Summary

| Method | Description |
| ------ | ----------- |
| [`getFrameFromBuffer`](#getframefrombuffer) | Get the latest frame from the buffer. The boolean value determines whether the fetched frame will be removed from the buffer. |
| [`addListener`](#addlistener) | Add a listener to the camera enhancer instance. |
| [`removeListener`](#removelistener) | Remove a previously added listener from the camera enhancer instance. |

## Enhanced Features Methods Summary

| Method | Description |
| ------ | ----------- |
| [`enableFeatures`](#enablefeatures) | Enable camera enhancer features by inputting [`EnumEnhancerFeatures`](enum-enhancer-features.md) values. |
| [`disableFeatures`](#disablefeatures) | Disable camera enhancer features by inputting [`EnumEnhancerFeatures`](enum-enhancer-features.md) values. |
| [`isFeatureEnabled`](#isfeatureenabled) | Check whether the input features are enabled. |

## Advanced Camera Control Methods Summary

| Method | Description |
| ------ | ----------- |
| [`updateAdvancedSettingsFromFile`](#updateadvancedsettingsfromfile) | Update the advanced camera controlling and video streaming processing parameters. This method enables you to update settings via a JSON file from the storage. |
| [`updateAdvancedSettingsFromString`](#updateadvancedsettingsfromstring) | Update the advanced camera controlling and video streaming processing parameters. This method enables you to update settings via a JSON string. |

## Initialization Methods Details

### initWithView

Initialize the camera enhancer with the `DCECameraView`.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (instancetype)initWithView:(DCECameraView *)view;
```
2. 
```swift
init(view: DCECameraView) -> DynamsoftCameraEnhancer
```

**Return Value**

The instance of `DynamsoftCameraEnhancer`.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
_dce = [[DynamsoftCameraEnhancer alloc] initWithView:_dceView];
```
2. 
```swift
let dce = DynamsoftCameraEnhancer.init(view: dceCameraView)
```

&nbsp;

### getVersion

Get the SDK version of Dynamsoft Camera Enhancer.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
+ (NSString*)getVersion;
```
2. 
```swift
class func getVersion() -> String
```

**Return Value**

A string value that indicates the version of DynamsoftCameraEnhancer SDK.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
NSString* version = [DynamsoftCameraEnhancer getVersion];
```
2. 
```swift
let version = DynamsoftCameraEnhancer.getVersion()
```

&nbsp;

### cameraView

Bind a `DCECameraView` to the camera enhancer.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (strong, nonatomic) DCECameraView *dceCameraView; 
```
2. 
```swift
var dceCameraView: DCECameraView { get set }
```

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
_dceView = [[DCECameraView alloc] initWithFrame:self.view.bounds]
[_dce setCameraView:_dceView];
```
2. 
```swift
let dceView = DCECameraView.init(frame self.view.bounds)
dce.cameraView = dceView
```

## Basic Camera Control Methods Details

### getAllCameras

Get the IDs of all available cameras.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (NSArray*)getAllCameras;
```
2. 
```swift
func getAllCameras() -> [String]
```

**Return Value**

An NSArray that includes all available cameras. Users can clearly read whether the camera is front-facing, back-facing, or external from the cameraID.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
NSArray<NSString*>* allCameras = [_dce getAllCameras];
```
2. 
```swift
let allCameraList = dce.getAllCameras()
```

&nbsp;

### selectCameraWithPosition

Select the camera position (front-facing or back-facing).

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (void)selectCameraWithPosition:(EnumCameraPosition)position error:(NSError * _Nullable * _Nullable)error;
```
2. 
```swift
func selectCameraWithPosition(_ position: EnumCameraPosition) throws
```

**Parameters**

`cameraPosition`: An `EnumCameraPosition` value that indicates front-facing or back-facing camera.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
[_dce selectCameraWithPosition:EnumCameraPositionBack error: &error];
```
2. 
```swift
try? dce.selectCameraWithPosition(EnumCameraPosition.back)
```

&nbsp;

### getCameraPosition

Returns whether the front-facing camera or back-facing camera is selected.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (EnumCameraPosition) getCameraPosition;
```
2. 
```swift
func getCameraPosition() -> EnumCameraPosition
```

**Return Value**

An `EnumCameraPosition` value that indicates front-facing or back-facing camera.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
EnumCameraPosition cameraPosition = [_dce getCameraPosition];
```
2. 
```swift
let cameraPosition = dce.getCameraPosition()
```

&nbsp;

### selectCamera

Select camera by `cameraID`. The camera will be selected and further camera control settings will be applied to this camera. When the selected camera is changed via this method, the settings will be inherited by the newly selected camera.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (void)selectCamera:(NSString*)cameraId error:(NSError * _Nullable * _Nullable)error;
```
2. 
```swift
func selectCamera(_ cameraId: String) throws
```

**Parameters**

`cameraID`: A `String` value that listed in the `cameraIDList` returned by `getAllCameras`. The method will have no effects if the input value does not exist in the `cameraIDList`.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
[_dce selectCamera:@"BACK_FACING_CAMERA" error: &error];
```
2. 
```swift
try? dce.selectCamera("BACK_FACING_CAMERA")
```

**Remarks**

- There is always a back-facing camera be defined as a default camera. If the user doesn't select any camera via `selectCamera`, the default camera will be considered as the selected camera.
- If there is no opened camera, the method `selectCamera` will not open any camera.
- If there is an opened camera and the opened camera's ID exactly equals the input ID, the method `selectCamera` will make no changes.
- If there is an opened camera and the opened camera's ID is different from the input ID, the method `selectCamera` will close the currently opened camera and then open a new camera by the input ID.

&nbsp;

### getSelectedCamera

Get the ID of the currently selected camera.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (NSString*)getSelectedCamera;
```
2. 
```swift
func getSelectedCamera() -> String
```

**Return Value**

The ID of the current selected camera.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
NSString* cameraID = [_dce getSelectedCamera];
```
2. 
```swift
let selectedCamera = dce.getSelectedCamera()
```

&nbsp;

### getCameraState

Get the state of the currently selected camera.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (EnumCameraState*)getCameraState;
```
2. 
```swift
func getCameraState() -> EnumCameraState
```

**Return Value**

One of the preset camera state in Enumeration [`EnumCameraState`](enum-camera-state.md).

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
EnumCameraState state = [_dce getCameraState];
```
2. 
```swift
let cameraState = dce.getCameraState()
```

&nbsp;

### open

- Turn on the selected camera if a camera has been selected via `selectCamera`.
- Turn on the default camera if no camera is selected via `selectCamera`.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (void)open;
```
2. 
```swift
func open()
```

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
[_dce open];
```
2. 
```swift
dce.open()
```

&nbsp;

### close

- Turn off the selected camera if a camera has been selected via `selectCamera`.
- Turn off the default camera if no camera is selected via `selectCamera`.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (void)close;
```
2. 
```swift
func close()
```

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
[_dce close];
```
2. 
```swift
dce.close()
```

&nbsp;

### turnOnTorch

Turn on the torch (if the torch of the mobile device is available).

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (void)turnOnTorch;
```
2. 
```swift
func turnOnTorch()
```

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
[_dce turnOnTorch];
```
2. 
```swift
dce.turnOnTorch()
```

&nbsp;

### turnOffTorch

Turn off the torch.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (void)turnOffTorch;
```
2. 
```swift
func turnOffTorch()
```

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
[_dce turnOffTorch];
```
2. 
```swift
dce.turnOffTorch()
```

### getFrameRate

Get the current frame rate.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (NSInteger)getFrameRate;
```
2. 
```swift
func getFrameRate() -> Int32
```

**Return Value**

The current frame rate.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
NSInteger frameRate = [_dce getFrameRate];
```
2. 
```swift
let frameRate = dce.getFrameRate()
```

&nbsp;

### setResolution

Input one of the preset resolution value in Enumeration `Resolution`. The camera enhancer will try to set the resolution to the target value or the closest available value below the target value.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (void)setResolution:(EnumResolution)resolution;
```
2. 
```swift
func setResolution(_ resolution: EnumResolution)
```

**Parameters**

`resolution`: One of the int value that preset in Enumeration [`EnumResolution`](enum-resolution.md).

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
[_dce setResolution:EnumRESOLUTION_1080P];
```
2. 
```swift
dce.setResolution(EnumResolution.EnumRESOLUTION_1080P)
```

&nbsp;

### getResolution

Get the current resolution.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (NSString*)getResolution;
```
2. 
```swift
func getResolution() -> Stringß
```

**Return Value**

The size of the current resolution.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
NSString* resolution = [_dce getResolution];
```
2. 
```swift
let resolution = dce.getResolution()
```

&nbsp;

### setZoom

Set the zoom factor. Once `setZoom` is triggered and approved, the zoom factor of the activated camera will immediately become the input value.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (Void)setZoom:(CGFloat)factor
```
2. 
```swift
func setZoom(_ factor: CGFloat)
```

**Parameters**

`factor`: The target zoom factor.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
[_dce setZoom:3.0f];
```
2. 
```swift
dce.setZoom(3.0)
```

&nbsp;

### autoZoomRange

The property for getting/setting the range of auto zoom.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) UIFloatRange autoZoomRange;
```
2. 
```swift
var autoZoomRange: UIFloatRange { get set }
```

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
[_dce setAutoZoomRange:UIFloatRangeMake(1.5,4)];
UIFloatRange currentZoomRange = [_dce autoZoomRange];
```
2. 
```swift
dce.autoZoomRange = UIFloatRange(minimum:1.5, maximum: 4)
let currentZoomRange = dce.autoZoomRange()
```

&nbsp;

### getMaxZoomFactor

Get the maximum available zoom factor.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (CGFloat)getMaxZoomFactor;
```
2. 
```swift
func getMaxZoomFactor() -> CGFloat
```

**Return Value**

A **CGFloat** value that indicates the maximum available zoom factor of the device.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
CGFloat maxZoomFactor = [_dce getMaxZoomFactor];
```
2. 
```swift
let maxZoomFactor = dce.getMaxZoomFactor()
```

&nbsp;

### setFocus

Set the focus position (value range from 0.0f to 1.0f) and trigger a focus at the configured position.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (Void)setFocus:(CGPoint)point;
```
2. 
```swift
func setFocus(_ point: CGPoint)
```

**Parameters**

`focusPosition`: A CGPoint that stores the x and y coordinate of the targeting focus position.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
CGPoint focusPoint = {0.4, 0.5};
[_dce setFocus:focusPoint];
```
2. 
```swift
let focusPoint = CGPoint(x:0.4, y:0.5)
dce.setFocus(focusPoint)
```

&nbsp;

### setFocus(subsequentFocusMode)

Trigger a focus at the targeting point and set the subsequent focus mode after focused.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (Void)setFocus:(CGPoint)focusPoint subsequentFocusMode:(EnumFocusMode)subsequentFocusMode; 
```
2. 
```swift
func setFocus(_ focusPoint: CGPoint, focusMode subsequentFocusMode: EnumFocusMode)
```

**Parameters**

`[in] focusPosition`: A `CGPoint` indicates the interest area.
`[in] subsequentFocusMode`: If you set the focus mode to `FM_LOCKED`, the focallength will be lock after the focus. Otherwise, the continuous auto focus that control by the hardware is still enabled.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
CGPoint focusPoint = {0.4, 0.5};
[_dce setFocus:focusPoint subsequentFocusMode:EnumFocusMode.FM_LOCKED];
```
2. 
```swift
let focusPoint = CGPoint(x:0.4, y:0.5)
dce.setFocus(focusPoint, subsequentFocusMode:EnumFocusMode.FM_LOCKEDD)
```

&nbsp;

### setScanRegion

Specify the `scanRegion`. The DCEFrames will be cropped according to the `scanRegion` before they are stored in the video buffer.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (void)setScanRegion:(RegionDefinition)scanRegion error:(NSError * _Nullable)error;
```
2. 
```swift
func setScanRegion(_ scanRegion: iRegionDefinition?) throws
```

**Parameters**

`scanRegion`: Use a [`iRegionDefinition`](region-definition.md) value to specify the scan region. The parameter will be optimized to the maximum or minimum available value if the input parameter is out of range. For more information, please view [`iRegionDefinition`](region-definition.md).

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
iRegionDefinition* scanRegion = [[iRegionDefinition alloc] init];
scanRegion.regionTop = 25;
scanRegion.regionBottom = 75;
scanRegion.regionLeft = 25;
scanRegion.regionRight = 75;
scanRegion.regionMeasuredByPercentage = 1
[_dce setScanRegion:scanRegion error: &error];
```
2. 
```swift
let scanRegion = iRegionDefinition()
scanRegion.regionTop = 25
scanRegion.regionBottom = 75
scanRegion.regionLeft = 25
scanRegion.regionRight = 75
scanRegion.regionMeasuredByPercentage = 1
try? dce.setScanRegion(scanRegion)
```

**Remarks**

- The region definition defines the region on the **camera view**. For each value of the class [`iRegionDefinition`](region-definition.md):
  - The `regionTop` is the distance between the **top** of the scan region and the **top** of the video frame.
  - The `regionBottom` is the distance between the **bottom** of the scan region and the **top** of the video frame.
  - The `regionLeft` is the distance between the **left** of the scan region and the **left** of the video frame.
  - The `regionRight` is the distance between the **right** of the scan region and the **left** of the video frame.

- When you trigger `setScanRegion`, the enhancer feature [`EF_FAST_MODE`](#enablefeatures) will be disabled.
- You will still get the original [`DCEFrame`](dceframe.md) from [`FrameOutputCallback`](protocol-dceframelistener.md) and cropped [`DCEFrame`](dceframe.md) from [`getFrameFromBuffer`](#getframefrombuffer). The `cropRegion` of [`DCEFrame`](dceframe.md) will be configured based on the **scanRegion** when `setScanRegion` is triggered.
- When you trigger `setScanRegion`, the [`scanRegionVisible`](#scanregionvisible) will be set to true automatically. If you don't want to display the **scanRegion** on the UI, please set the [`scanRegionVisible`](#scanregionvisible) to false manually.

&nbsp;

### getScanRegion

Get the current scan region settings.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (iRegionDefinition) getScanRegion
```
2. 
```swift
func getScanRegion() -> iRegionDefinition?
```

**Return Value**

The return value of `getScanRegion` is always the actual parameter of the `scanRegion`, which might be different from the user input parameter. If `scanRegion` is not configured or the method `setScanRegion` is not approved, the return value will be null.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
iRegionDefinition* myScanRegion = [[iRegionDefinition alloc] init];
myScanRegion = [_dce getScanRegion];
```
2. 
```swift
let scanRegion = iRegionDefinition()
scanRegion = dce.getScanRegion()
```

&nbsp;

### scanRegionVisible

Set whether to display the **scanRegion** on the UI. The default value of the property is false. When the property value is set to true, the scan region will be drawn on the UI. The **scanRegion** will not be displayed if its value is null.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (assign, nonatomic) BOOL scanRegionVisible;
```
2. 
```swift
var scanRegionVisible: Bool { get set }
```

&nbsp;

### setCameraStateListener

Set a `DCECameraStateListener` to receive notifications when the camera state changes.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (void) setCameraStateListener:(nonnull id<DCECameraStateListener>)listener;
```
2. 
```swift
func setCameraStateListener(_ listener: DCECameraStateListener?)
```

**Parameters**

`[in] listener`: A `DCECameraStateListener` object.

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

&nbsp;

## Frame Acquiring Methods Details

### getFrameFromBuffer

Get the latest frame from the buffer. The boolean value determines whether the fetched frame will be removed from the buffer.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (DCEFrame*)getFrameFromBuffer:(BOOL)keep;
```
2. 
```swift
func getFrameFromBuffer(_ iskeep: Bool) -> DCEFrame
```

**Parameters**

`Keep`: If set to `true`, the frame will be kept in the video buffer. Otherwise, it will be removed from the video buffer.

**Return Value**

The latest frame in the video buffer.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
dceFrame = [_dce getFrameFromBuffer:true];
```
2. 
```swift
let dceFrame = dce.getFrameFromBuffer()
```

&nbsp;

### addListener

Add a listener to the `CameraEnhancer` instance. This method will have no effect if the same listener is already added.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (void)addListener:(nonnull id<DCEFrameListener>)listener;
```
2. 
```swift
func addListener(_ listener: DCEFrameListener)
```

**Parameters**

`listener`: An object of `DCEFrameListener`. Its callback method `frameOutputCallback` will be available for users to make further operations on the captured video frame.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
[_dce addListener:self];
```
2. 
```swift
dce.addListener(self)
```

&nbsp;

### removeListener

Remove a previously added listener from the `CameraEnhancer` instance. This method will have no effect if there is no listener exists in `CameraEnhancer` instance.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (void)removeListener:(nonnull id<DCEFrameListener>)listener;
```
2. 
```swift
func removeListener(_ listener: DCEFrameListener)
```

**Parameters**

`listener`: The input listener will be removed from the Camera Enhancer instance.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
[_dce removeListener:self];
```
2. 
```swift
dce.removeListener(self)
```

&nbsp;

## Enhanced Features Methods Details

### enableFeatures

Enable camera enhancer features by inputting [`EnumEnhancerFeatures`](enum-enhancer-features.md) value.

The `EnumEnhancerFeatures` members:

|  Members | Value |
| -------- | ----- |
| `EnumFRAME_FILTER` | 0x01 |
| `EnumSENSOR_CONTROL` | 0x02 |
| `EnumENHANCED_FOCUS` | 0x04 |
| `EnumFAST_MODE` | 0x08 |
| `EnumAUTO_ZOOM` | 0x10 |
| `EnumSMART_TORCH` | 0x20 |

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (void)enableFeatures:(EnumEnhancerFeatures)features  error:(NSError * _Nullable * _Nullable)error;
```
2. 
```swift
func enableFeatures(_ enumEnhancerFeatures: Int) throws
```

**Parameters**

`enhancerFeatures`: The combined value of [`EnumEnhancerFeatures`](enum-enhancer-features.md).

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
[_dce enableFeatures:EnumFRAME_FILTER error: &error];
```
2. 
```swift
try? dce.enableFeatures(EnumEnhancerFeature.EnumFRAME_FILTER.rawValue)
```

**Remarks**

The enable action will not be approved if the license is invalid. If your input values include the features that have been already enabled, these features will keep the enabled status.

&nbsp;

### disableFeatures

Disable camera enhancer features by inputting [`EnumEnhancerFeatures`](enum-enhancer-features.md) values.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (void)disableFeatures:(EnumEnhancerFeatures)features;
```
2. 
```swift
func disableFeatures(_ enumEnhancerFeatures: Int)
```

**Parameters**

`enhancerFeatures`: The combined value of [`EnumEnhancerFeatures`](enum-enhancer-features.md).

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
[_dce disableFeatures:EnumFRAME_FILTER];
```
2. 
```swift
dce.disableFeatures(EnumEnhancerFeature.EnumFRAME_FILTER.rawValue)
```

**Remarks**

You can still disable the features even if the license is invalid. If your input values include the features that are not enabled, these features will keep the disabled status.

&nbsp;

### isFeatureEnabled

Check whether the input features are enabled.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (BOOL)isFeatureEnabled:(EnumEnhancerFeatures)features;
```
2. 
```swift
func isFeatureEnabled(_ enumEnhancerFeatures: Int) -> Bool
```

**Parameters**

`enhancerFeatures`: The combined value of [`EnumEnhancerFeatures`](enum-enhancer-features.md).

**Return Value**

A BOOL value refers to whether all the features you input are enabled.

- `True`: All the features you input are enabled.  
- `False`: There is at least one feature is not enabled among your input values.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
BOOL featureEnabled = [_dce isFeatureEnabled:EnumFRAME_FILTER];
```
2. 
```swift
let featureEnabled = dce.isFeatureEnabled(EnumEnhancerFeature.EnumFRAME_FILTER.rawValue)
```

**Remarks**

If the features you input are all enabled but don't cover all the enabled features, this method will still return `true`.

## Advanced Camera Control Methods Details

### updateAdvancedSettingsFromFile

Update the advanced camera controlling and video streaming processing parameters. This method enables you to update settings via a JSON file from the storage.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (BOOL)updateAdvancedSettingsFromFile:(NSString*)filePath error:(NSError * _Nullable * _Nullable)error NS_SWIFT_NAME(updateAdvancedSettingsFromFile(_:));

```
2. 
```swift
func updateAdvancedSettingsFromFile(_ filePath: String) throws
```

**Parameters**

`filePath`: The file path of the JSON file.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
[_dce updateAdvancedSettingsFromFile:@"Put your JSON file path here." error: &error];
```
2. 
```swift
try? dce.updateAdvancedSettingsFromFile("Put your JSON file path here.")
```

**Remarks**

You might need permission authority to enable the Camera Enhancer to read the file in your mobile storage.

&nbsp;

### updateAdvancedSettingsFromString

Update the advanced camera controlling and video streaming processing parameters. This method enables you to update settings via a JSON string.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (BOOL)updateAdvancedSettingsFromString:(NSString*)JsonString error:(NSError * _Nullable * _Nullable)error;
```
2. 
```swift
func updateAdvancedSettingsFromString(_ JsonString: String) throws
```

**Parameters**

`jsonString`: A stringified JSON data.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
[_dce updateAdvancedSettingsFromString:@"Put your stringified JSON data here." error: &error];
```
2. 
```swift
try? dce.updateAdvancedSettingsFromString("Put your stringified JSON data here.")
```
