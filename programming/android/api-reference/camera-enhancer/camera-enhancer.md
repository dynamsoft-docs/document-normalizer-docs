---
layout: default-layout
title: Android CameraEnhancer Class - Dynamsoft Document Normalizer Documents
description: This is the documentation - Android API references - CameraEnhancer Class page of Dynamsoft Document Normalizer.
keywords:  Camera Enhancer, Android API references, CameraEnhancer Class
needAutoGenerateSidebar: true
noTitleIndex: true
needGenerateH3Content: true
breadcrumbText: Android CameraEnhancer Class
---

# CameraEnhancer Class

The main class of `CameraEnhancer` library. It contains APIs that enable user to:

- Implement basic camera control like open, close, change resolution, etc.
- Get frames from the video streaming.
- Enable advanced features including:
  - Frame filtering by sharpness
  - Frame filtering by sensor
  - Enhanced focus
  - Frame cropping
  - Auto zoom
  - Smart torch control

```java
class com.dynamsoft.dce.CameraEnhancer
```

## Initialization Methods Summary

| Method | Description |
| ------ | ----------- |
| [`CameraEnhancer`](#cameraenhancer) | Initialize the `CameraEnhancer`. |
| [`getVersion`](#getversion) | Get the SDK version. |

## Basic Camera Control Methods Summary

| Method | Description |
| ------ | ----------- |
| [`getAllCameras`](#getallcameras) | Get all available cameras. This method returns a list of available camera IDs. |
| [`selectCamera(EnumCameraPosition)`](#selectcameraenumcameraposition) | Select whether to use front-facing camera or back-facing camera. |
| [`getCameraPosition`](#getcameraposition) | Returns whether the front-facing camera or back-facing camera is selected. |
| [`selectCamera(String)`](#selectcamerastring) | Select a camera from the camera list with the camera ID. |
| [`getSelectedCamera`](#getselectedcamera) | Get the camera ID of the current selected camera. |
| [`getCameraState`](#getcamerastate) | Get the state of the currently selected camera. |
| [`open`](#open) | Turn on the current selected camera. |
| [`close`](#close) | Turn off the current selected camera. |
| [`turnOnTorch`](#turnontorch) | Turn on the torch. |
| [`turnOffTorch`](#turnofftorch) | Turn off the torch. |
| [`getFrameRate`](#getframerate) | Get the current frame rate. |
| [`getResolutionList`](#getresolutionlist) | Get all available resolutions. |
| [`setResolution`](#setresolution) | Set the resolution to the input value (if the input value is available for the device). |
| [`getResolution`](#getresolution) | Get the current resolution. |
| [`setZoom`](#setzoom) | Set the zoom factor. Once `setZoom` is triggered and approved, the zoom factor of the actived camera will immediately become the input value. |
| [`setAutoZoomRange`](#setautozoomrange) | Set the range of auto zoom. |
| [`getAutoZoomRange`](#getautozoomrange) | Get the range of auto zoom. |
| [`setFocus`](#setfocus) | Focus once at the input position. |
| [`setFocus(subsequentFocusMode)`](#setfocussubsequentfocusmode) | Trigger a focus at the targeting point and set the subsequent focus mode after focused.  |
| [`setScanRegion`](#setscanregion) | Set the scan region with a RegionDefinition value. The frame will be cropped according to the scan region. |
| [`getScanRegion`](#getscanregion) | Get the scan region. |
| [`setScanRegionVisible`](#setscanregionvisible) | Set whether to display the **scanRegion** on the UI. |
| [`getScanRegionVisible`](#getscanregionvisible) | Get whether the **scanRegion** will be displayed on the UI. |
| [`setCameraStateListener`](#setcamerastatelistener ) | Add a [`DCECameraStateListener`](interface-dcecamerastatelistener.md) to receive notification when the camera state changes. |

## Frame Acquiring Methods Summary

| Method | Description |
| ------ | ----------- |
| [`getFrameFromBuffer`](#getframefrombuffer) | Get the latest frame from the buffer. The boolean value determines whether the fetched frame will be removed from the buffer. |
| [`addListener`](#addlistener) | Add a listener to the camera enhancer instance. |
| [`removeListener`](#removelistener) | Remove a previously added listener from the camera enhancer instance. |
| [`takePhoto`](#takephoto) | Take a photo from the camera and save the image in the memory. |

## Enhanced Features Methods Summary

| Method | Description |
| ------ | ----------- |
| [`enableFeatures`](#enablefeatures) | Enable camera enhancer features by inputting [`EnumEnhancerFeatures`](enum-enhancer-features.md) values. |
| [`disableFeatures`](#disablefeatures) | Disable camera enhancer features by inputting [`EnumEnhancerFeatures`](enum-enhancer-features.md) values. |
| [`isFeatureEnabled`](#isfeatureenabled) | Check whether the input features are enabled. |

## Advanced Camera Control Methods Summary

| Method | Description |
| ------ | ----------- |
| [`updateAdvancedSettingsFromFile`](#updateadvancedsettingsfromfile) | Update advanced parameter settings including filter, sensor and focus settings from a JSON file. |
| [`updateAdvancedSettingsFromString`](#updateadvancedsettingsfromstring) | Update advanced parameter settings including filter, sensor and focus settings from a JSON string. |

## Camera UI Methods Summary

| Method | Description |
| ------ | ----------- |
| [`setCameraView`](#setcameraview) | Bind a instance of `DCECameraView` to the `CameraEnhancer`. |
| [`getCameraView`](#getcameraview) | Get the object of `DCECameraView` that is binded to the `CameraEnhancer`. |

## Initialization Methods Details

### CameraEnhancer

Initialize the `CameraEnhancer` Object.

```java
CameraEnhancer(android.app.Activity activity)
```

**Parameters**

`activity`: The target activity.

**Code Snippet**

```java
CameraEnhancer cameraEnhancer = new CameraEnhancer(MainActivity.this); 
```

&nbsp;

### getVersion

Get the SDK version of Dynamsoft Camera Enhancer.

```java
static String getVersion()
```

**Return Value**

A string value that indicates the version of `CameraEnhancer` SDK.

**Code Snippet**

```java
String version = CameraEnhancer.getVersion();
```

## Basic Camera Control Methods Details

### getAllCameras

Get the IDs of all available cameras.

```java
String[] getAllCameras()
```

**Return Value**

An array list that inclueds all available cameras. Users can clearly read whether the camera is front-facing, back-facing or external from the cameraID.

**Code Snippet**

```java
CameraEnhancer cameraEnhancer = new CameraEnhancer(MainActivity.this); 
String[] cameraIds = cameraEnhancer.getAllCameras();
```

&nbsp;

### selectCamera(EnumCameraPosition)

Select the camera position (front-facing or back-facing).

```java
void selectCamera(EnumCameraPosition cameraPosition) throws CameraEnhancerException
```

**Parameters**

`cameraPosition`: An `EnumCameraPosition` value that indicates front-facing or back-facing camera.

**Code Snippet**

```java
CameraEnhancer cameraEnhancer = new CameraEnhancer(MainActivity.this); 
cameraEnhancer.selectCamera(EnumCameraPosition.CP_BACK);
```

&nbsp;

### getCameraPosition

Returns whether the front-facing camera or back-facing camera is selected.

```java
EnumCameraPosition getCameraPosition()
```

**Return Value**

An `EnumCameraPosition` value that indicates front-facing or back-facing camera.

**Code Snippet**

```java
EnumCameraPosition camera = mCameraEnhancer.getCameraPosition();
```

&nbsp;

### selectCamera(String)

Select camera by `cameraID`. The camera will be selected and further camera control settings will be applied to this camera. When the selected camera is changed by selecting another camera via this method, the settings applied to this camera will be inherited by the newly selected camera.

```java
void selectCamera(String cameraID) throws CameraEnhancerException
```

**Parameters**

`cameraID`: A `String` value that listed in the `cameraIDList` returned by `getAllCameras`. The method will have no effects if the input value does not exist in the `cameraIDList`.

**Code Snippet**

```java
CameraEnhancer cameraEnhancer = new CameraEnhancer(MainActivity.this); 
cameraEnhancer.selectCamera("BACK_FACING_CAMERA_0");
```

**Remarks**

- There is always a back-facing camera be defined as a default camera. If the user doesn't select any camera via `selectCamera`, the default camera will be considered as the selected camera.
- If there is no opened camera, the method `selectCamera` will not open any camera.
- If there is an opened camera and the opened camera's ID exactly equals the input ID, the method `selectCamera` will make no changes.
- If there is an opened camera and the opened camera's ID is different from the input ID, the method `selectCamera` will close the currently opened camera and then open a new camera by the input ID.

&nbsp;

### getSelectedCamera

Get the ID of the currently selected camera.

```java
String getSelectedCamera()
```

**Return Value**

The ID of the current selected camera.

**CodeSnippet**

```java
CameraEnhancer cameraEnhancer = new CameraEnhancer(MainActivity.this); 
String selectedCameraID = cameraEnhancer.getSelectedCamera();
```

&nbsp;

### getCameraState

Get the state of the currently selected camera.

```java
EnumCameraState getCameraState()
```

**Return Value**

One of the preset camera state in Enumeration [`EnumCameraState`](enum-camera-state.md).

**Code Snippet**

```java
CameraEnhancer cameraEnhancer = new CameraEnhancer(MainActivity.this);
int cameraState = cameraEnhancer.getCameraState();
```

&nbsp;

### open

- Turn on the selected camera if a camera has been selected via `selectCamera`.
- Turn on the default camera if no camera is selected via `selectCamera`.

```java
void open() throws CameraEnhancerException
```

**Code Snippet**

```java
CameraEnhancer cameraEnhancer = new CameraEnhancer(MainActivity.this); 
cameraEnhancer.open();
```

&nbsp;

### close

- Turn off the selected camera if a camera has been selected via `selectCamera`.
- Turn off the default camera if no camera is selected via `selectCamera`.

```java
void close() throws CameraEnhancerException
```

**Code Snippet**

```java
CameraEnhancer cameraEnhancer = new CameraEnhancer(MainActivity.this); 
cameraEnhancer.close();
```

&nbsp;

### turnOnTorch

Turn on the torch (if the torch of the mobile device is available).

```java
void turnOnTorch() throws CameraEnhancerException
```

**Code Snippet**

```java
CameraEnhancer cameraEnhancer = new CameraEnhancer(MainActivity.this); 
cameraEnhancer.turnOnTorch();
```

&nbsp;

### turnOffTorch

Turn off the torch.

```java
void turnOffTorch() throws CameraEnhancerException
```

**Code Snippet**

```java
CameraEnhancer cameraEnhancer = new CameraEnhancer(MainActivity.this); 
cameraEnhancer.turnOffTorch();
```

### getFrameRate

Get the current frame rate.

```java
int getFrameRate()
```

**Return Value**

The current frame rate.

**Code Snippet**

```java
CameraEnhancer cameraEnhancer = new CameraEnhancer(MainActivity.this); 

int frameRate = cameraEnhancer.getFrameRate();
```

&nbsp;

### getResolutionList

Check the available resolutions of the current device.

```java
List<Size> getResolutionList()
```

**Return Value**

A list that contains all available resolutions.

**Code Snippet**

```java
CameraEnhancer cameraEnhancer = new CameraEnhancer(MainActivity.this); 

List<Size> resolutionList = cameraEnhancer.getResolutionList();
```

&nbsp;

### setResolution

Input a preset resolution value in Enumeration `Resolution`. The camera enhancer will try to set the resolution to the target value or the closest available value below the target value.

```java
void setResolution(EnumResolution resolution) throws CameraEnhancerException
```

**Parameters**

`resolution`: One of the int value that preset in [`EnumResolution`](enum-resolution.md).

**Code Snippet**

```java
CameraEnhancer cameraEnhancer = new CameraEnhancer(MainActivity.this); 

cameraEnhancer.setResolution(EnumResolution.RESOLUTION_2K);
```

&nbsp;

### getResolution

Get the current resolution.

```java
Size getResolution()
```

**Return Value**

The size of the current resolution.

**Code Snippet**

```java
CameraEnhancer cameraEnhancer = new CameraEnhancer(MainActivity.this); 

Size currentResolution = cameraEnhancer.getResolution();
```

&nbsp;

### setZoom

Set the zoom factor. The camera will zoom in/out immediately after this method is triggered.

```java
void setZoom(float factor) throws CameraEnhancerException
```

**Parameters**

`factor`: The target zoom factor.

**Code Snippet**

```java
CameraEnhancer cameraEnhancer = new CameraEnhancer(MainActivity.this); 

cameraEnhancer.setZoom(2.5)
```

&nbsp;

### setAutoZoomRange

Set the range of auto zoom.

```java
void setAutoZoomRange(android.util.Range zoomRange)
```

**Parameters**

`[in] zoomRange`: A `UIFloatRange` value that defines the range of auto zoom.

**Code Snippet**

```java
cameraEnhancer.setAutoZoomRange(new Range(1.5,4));
```

&nbsp;

### getAutoZoomRange

Get the range of auto zoom.

```java
Range getAutoZoomRange()
```

**Return Value**

A `UIFloatRange` value that defines the range of auto zoom.

**Code Snippet**

```java
Range range = cameraEnhancer.getAutoZoomRange();
```

&nbsp;

### setFocus

Set the focus position (value range from 0.0f to 1.0f) and trigger a focus at the configured position.

```java
void setFocus(float x, float y) throws CameraEnhancerException
```

**Parameters**

`x`: The x-coordinate of the targeting focus position.  
`y`: The y-coordinate of the targeting focus position.

**Code Snippet**

```java
CameraEnhancer cameraEnhancer = new CameraEnhancer(MainActivity.this); 

cameraEnhancer.setFocus(0.5,0.4);
```

&nbsp;

### setFocus(subsequentFocusMode)

Trigger a focus at the targeting point and set the subsequent focus mode after focused.

```java
void setFocus(android.graphics.PointF focusPoint, EnumFocusMode subsequentFocusMode) throws CameraEnhancerException
```

**Parameters**

`[in] focusPosition`: An `android.graphics.PointF` object indicates the interest area.
`[in] subsequentFocusMode`: Specify a focus mode via [EnumFocusMode](enum-focus-mode.md). If you set the focus mode to `FM_LOCKED`, the focallength will be lock after the focus. Otherwise, the continuous auto focus that control by the hardware is still enabled.

**Exception**

An exception thrown to indicate an error has occurred when trying to trigger a focus.

**Code Snippet**

```java
CameraEnhancer cameraEnhancer = new CameraEnhancer(MainActivity.this); 

cameraEnhancer.setFocus(new PointF(0.5f,0.5f), EnumFocusMode.FM_LOCKED);
```

&nbsp;

### setScanRegion

Specify the scan region. The DCEFrames will be cropped according to the scan region before they are stored in the video buffer.

```java
void setScanRegion(RegionDefinition scanRegion) throws CameraEnhancerException
```

**Parameters**

`scanRegion`: Use a RegionDefinition value to specify the scan region. The parameter will be optimized to the maximum or minimum available value if the input parameter is out of range. For more information, please view [`RegionDefinition`](region-definition.md) class.

**Code Snippet**

```java
com.dynamsoft.dce.RegionDefinition scanRegion = new RegionDefinition();
scanRegion.regionTop = 25;
scanRegion.regionBottom = 75;
scanRegion.regionLeft = 25;
scanRegion.regionRight = 75;
regionDefinition.regionMeasuredByPercentage = 1;

CameraEnhancer cameraEnhancer = new CameraEnhancer(MainActivity.this);
try {
    cameraEnhancer.setScanRegion(scanRegion);;
} catch (CameraEnhancerException e) {
    e.printStackTrace();
}
```

**Remarks**

- The region definition defines the region on the **camera view**. For each value of the class [`RegionDefinition`](region-definition.md):
  - The `regionTop` is the distance between the **top** of the scan region and the **top** of the video frame.
  - The `regionBottom` is the distance between the **bottom** of the scan region and the **top** of the video frame.
  - The `regionLeft` is the distance between the **left** of the scan region and the **left** of the video frame.
  - The `regionRight` is the distance between the **right** of the scan region and the **left** of the video frame.

- When you trigger `setScanRegion`, the enhancer feature [`EF_FAST_MODE`](#enablefeatures) will be disabled.
- You will still get the original [`DCEFrame`](dceframe.md) from [`FrameOutputCallback`](interface-dceframelistener.md) and cropped [`DCEFrame`](dceframe.md) from [`getFrameFromBuffer`](#getframefrombuffer). The `cropRegion` of [`DCEFrame`](dceframe.md) will be configured based on the `scanRegion` when `setScanRegion` is triggered.
- When you trigger `setScanRegion`, the **scanRegion** will be displayed on the UI automatically. If you don't want to display the **scanRegion** on the UI, please set the [`scanRegionVisible`](#scanregionvisible) to false manually.

&nbsp;

### getScanRegion

Get the scan region configurations. You will get a null value if the scan region is not set.

```java
RegionDefinition getScanRegion()
```

**Return Value**

The return value of `getScanRegion` is always the actual parameter of the `scanRegion`, which might be different from the user input parameter. If `scanRegion` is not configured or the method `setScanRegion` is not approved, the return value will be null.

**Code Snippet**

```java
com.dynamsoft.dce.RegionDefinition myScanRegion = new RegionDefinition();

CameraEnhancer cameraEnhancer = new CameraEnhancer(MainActivity.this);
myScanRegion = cameraEnhancer.getScanRegion(scanRegion);
```

&nbsp;

### setScanRegionVisible

Set whether to display the **scanRegion** on the UI. The default value is false. When the value is set to true, the scan region will be displayed on the UI. The **scanRegion** will not be displayed if the **scanRegion** value is null.

```java
void setScanRegionVisible(boolean scanRegionVisible)
```

**Parameters**

`scanRegionVisible`: When the value is set to true, the **scanRegion** will be displayed on the UI. Otherwise, the **scanRegion** will not be displayed.

**Code Snippet**

```java
CameraEnhancer cameraEnhancer = new CameraEnhancer(MainActivity.this); 

cameraEnhancer.setScanRegionVisible(true);
```

&nbsp;

### getScanRegionVisible

Get whether the **scanRegion** will be displayed on the UI.

```java
boolean getScanRegionVisible()
```

**Return Value**

When the return value is true, the **scanRegion** will be displayed. Otherwise, the **scanRegion** will not be displayed.

**Code Snippet**

```java
CameraEnhancer cameraEnhancer = new CameraEnhancer(MainActivity.this); 

boolean scanRegionVisible = cameraEnhancer.getScanRegionVisible();
```

&nbsp;

### setCameraStateListener

Add a [`DCECameraStateListener`](interface-dcecamerastatelistener.md) to receive notification when the camera state changes.

```java
void setCameraStateListener (DCECameraStateListener listener)
```

**Parameters**

`[in] listener`: A [`DCECameraStateListener`](interface-dcecamerastatelistener.md) object.

**Code Snippet**

```java
CameraEnhancer cameraEnhancer = new CameraEnhancer(MainActivity.this); 

cameraEnhancer.setCameraStateListener(new DCECameraStateListener(){
    @Override
    public void stateChangeCallback(EnumCameraState currentState) {
        // Add your code to do when camera state changes.
    }
});
```

&nbsp;

## Frame Acquiring Methods Details

### getFrameFromBuffer

Get the latest frame from the video buffer.

```java
DCEFrame getFrameFromBuffer(boolean isKeep)
```

**Parameters**

`isKeep`: If set to `true`, the frame will be kept in the video buffer. Otherwise, it will be removed from the video buffer.

**Return Value**

The latest frame in the video buffer.

**Code Snippet**

```java
CameraEnhancer cameraEnhancer = new CameraEnhancer(MainActivity.this); 
DCEFrame frame = cameraEnhancer.getFrameFromBuffer(false);
```

&nbsp;

### addListener

Add a listener to the `CameraEnhancer` instance. This method will have no effect if the same listener is already added.

```java
void addListener(DCEFrameListener listener)
```

**Parameters**

`listener`: An object of `DCEFrameListener`. Its callback method `frameOutputCallback` will be available for users to make further operations on the captured video frame.

**Code Snippet**

```java
CameraEnhancer cameraEnhancer = new CameraEnhancer(MainActivity.this); 

DCEFrameListener listener = new DCEFrameListener(){
    @Override
    public void frameOutputCallback(DCEFrame frame, long timeStamp) {
        //perform custom action on generated frame
    }
};
cameraEnhancer.addListener(listener);
```

&nbsp;

### removeListener

Remove a previously added listener from the `CameraEnhancer` instance. This method will have no effect if there is no listener exists in `CameraEnhancer` instance.

```java
void removeListener(DCEFrameListener listener)
```

**Parameters**

`listener`: The input listener will be removed from the Camera Enhancer instance.

**Code Snippet**

```java
CameraEnhancer cameraEnhancer = new CameraEnhancer(MainActivity.this); 

DCEFrameListener listener = new DCEFrameListener(){
    @Override
    public void frameOutputCallback(DCEFrame frame, long timeStamp) {
        //perform custom action on generated frame
    }
};
cameraEnhancer.addListener(listener);
// ......
cameraEnhancer.removeListener(listener);
```

&nbsp;

### takePhoto

Take a photo from the camera and save the image in the memory. The photo will be captured and users can receive the captured photo via [`photoOutputCallback`](interface-dcephotolistener.md#photooutputcallback).

```java
void takePhoto(DCEPhotoListener listener)
```

**Parameters**

`listener`: An instance of [`DCEPhotoListener`](interface-dcephotolistener.md).

**Code Snippet**

```java
// Create an instance of DCEPhotoListener
DCEPhotoListener photoListener = new DCEPhotoListener() {
    @Override
    public void photoOutputCallback(byte[] bytes) {
        // Add your code to execute when photo is captured.
    }
};
mCameraEnhancer.takePhoto(photoListener);
```

## Enhanced Features Methods Details

### enableFeatures

Enable camera enhancer features by inputting [`EnumEnhancerFeatures`](enum-enhancer-features.md) value.

```java
void enableFeatures(int enhancerFeatures) throws CameraEnhancerException
```

**Parameters**

`enhancerFeatures`: The combined value of [`EnumEnhancerFeatures`](enum-enhancer-features.md).  

**Code Snippet**

```java
CameraEnhancer cameraEnhancer = new CameraEnhancer(MainActivity.this);
cameraEnhancer.enableFeatures(EnumEnhancerFeatures.FRAME_FILTER | EnumEnhancerFeatures.SENSOR_CONTROL);
```

**Remarks**

The enable action will not be approved if the license is invalid. If your input values include the features that have been already enabled, these features will keep the enabled status.

&nbsp;

### disableFeatures

Disable camera enhancer features by inputting [`EnumEnhancerFeatures`](enum-enhancer-features.md) values.

```java
void disableFeatures(int enhancerFeatures)
```

**Parameters**

`enhancerFeatures`: The combined value of [`EnumEnhancerFeatures`](enum-enhancer-features.md).

**Code Snippet**

```java
CameraEnhancer cameraEnhancer = new CameraEnhancer(MainActivity.this); 

cameraEnhancer.disableFeatures(EnumEnhancerFeatures.FRAME_FILTER | EnumEnhancerFeatures.SENSOR_CONTROL);
```

**Remarks**

You can still disable the features even if the license is invalid. If your input values include the features that are not enabled, these features will keep the disabled status.

&nbsp;

### isFeatureEnabled

Returns a boolean value that means whether the feature(s) you input is (are) enabled.

```java
boolean isFeatureEnabled(int enhancerFeatures)
```

**Parameters**

`enhancerFeatures`: The combined value of [`EnumEnhancerFeatures`](enum-enhancer-features.md).

**Return Value**

`True`: All the features you input are enabled.  
`False`: There is at least one feature that is not enabled among your input values.

**Code Snippet**

```java
CameraEnhancer cameraEnhancer = new CameraEnhancer(MainActivity.this); 

boolean isEnabled = cameraEnhancer.isFeatureEnabled(EnumEnhancerFeatures.FRAME_FILTER | EnumEnhancerFeatures.SENSOR_CONTROL);
```

**Remarks**

If the features you input are all enabled but don't cover all the enabled features, this method will still return `true`.

## Advanced Camera Control Methods Details

### updateAdvancedSettingsFromFile

Update the advanced camera controlling and video streaming processing parameters. This method enable you to update settings via a JSON file from the storage.

```java
void updateAdvancedSettingsFromFile(String filePath) throws CameraEnhancerException
```

**Parameters**

`filePath`: The file path of the JSON file.

**Code Snippet**

```java
CameraEnhancer cameraEnhancer = new CameraEnhancer(MainActivity.this); 
// Replace the filePath with your target filePath
cameraEnhancer.updateAdvancedSettingsFromFile("/storage/emulated/0/1.json")
```

**Remarks**

You might need permission authority to enable the Camera Enhancer to read the file in your mobile storage.

&nbsp;

### updateAdvancedSettingsFromString

Update the advanced camera controlling and video streaming processing parameters. This method enables you to update settings via a JSON string.

```java
void updateAdvancedSettingsFromString(String jsonString) throws CameraEnhancerException
```

**Parameters**

`jsonString`: A stringified JSON data.

**Code Snippet**

```java
CameraEnhancer cameraEnhancer = new CameraEnhancer(MainActivity.this); 

cameraEnhancer.updateAdvancedSettingsFromString("{'sensorvalue':3,'graydiffthreshold':30,'conversioncountthreshold':30,'sharpnessthreshold':0.2,'sharpnessthresholdlarge':0.4,'abssharpnessthreshold':200,'absgraythreshold':35,'claritythreshold':0.1}");
```

## Camera UI Methods Details

### setCameraView

Set a [`DCECameraView`](dcecameraview.md) object as the main UI view.

```java
void setCameraView(DCECameraView cameraView)
```

**Parameters**

`cameraView`: The main UI view. See also [`DCECameraView`](dcecameraview.md).

**Code Snippet**

```java
CameraEnhancer cameraEnhancer = new CameraEnhancer(MainActivity.this); 

DCECameraView cameraView = findViewById(R.id.cameraView);
cameraEnhancer.setCameraView(cameraView);
```

&nbsp;

### getCameraView

Get the [`DCECameraView`](dcecameraview.md) object of the current UI view.

```java
DCECameraView getCameraView()
```

**Return Value**

The current UI view. See also [`DCECameraView`](dcecameraview.md).

**Code Snippet**

```java
CameraEnhancer cameraEnhancer = new CameraEnhancer(MainActivity.this); 
DCECameraView cameraView =  cameraEnhancer.getCameraView();
```
