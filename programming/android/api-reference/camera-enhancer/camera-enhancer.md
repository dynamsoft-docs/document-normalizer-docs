---
layout: default-layout
title: Android CameraEnhancer Class
description: This is the documentation - Android API references - CameraEnhancer Class page of Dynamsoft Camera Enhancer.
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

## Initialization

| Method | Description |
| ------ | ----------- |
| [`CameraEnhancer`](#cameraenhancer) | Initialize the `CameraEnhancer`. |
| [`getVersion`](#getversion) | Get the SDK version. |

&nbsp;

### CameraEnhancer

Initialize the `CameraEnhancer` Object.

```java
CameraEnhancer(android.content.Context context)
```

**Parameters**

`context`: An instance of global information about an application environment.

**Code Snippet**

```java
CameraEnhancer cameraEnhancer = new CameraEnhancer(MainActivity.this); 
```

&nbsp;

### getVersion

Get the SDK version of Dynamsoft Camera Enhancer.

```java
String getVersion()
```

**Return Value**

A string value that stands for the camera enhancer SDK version.

**Code Snippet**

```java
CameraEnhancer cameraEnhancer = new CameraEnhancer(MainActivity.this); 
String DCEVersion = cameraEnhancer.getVersion();
```

&nbsp;

## Basic Camera Control Methods

| Method | Description |
| ------ | ----------- |
| [`getAllCameras`](#getallcameras) | Get all available cameras. This method returns a list of available camera IDs. |
| [`selectCamera`](#selectcamera) | Select a camera from the camera list with the camera ID. |
| [`getSelectedCamera`](#getselectedcamera) | Get the camera ID of the current selected camera. |
| [`getCameraState`](#getcamerastate) | Get the state of the currently selected camera. |
| [`open`](#open) | Turn on the current selected camera. |
| [`close`](#close) | Turn off the current selected camera. |
| [`pause`](#pause) | Pause the current selected  camera. |
| [`resume`](#resume) | Resume the current selected camera. |
| [`turnOnTorch`](#turnontorch) | Turn on the torch. |
| [`turnOffTorch`](#turnofftorch) | Turn off the torch. |

&nbsp;

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

### selectCamera

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

One of the preset camera state in Enumeration `EnumCameraState`.

| `EnumCameraState` | Value | Description |
| ----------------- | ----- | ----------- |
| `CAMERA_STATE_OPENED` | 1 | The selected camera is opened. |
| `CAMERA_STATE_CLOSED` | 2 | The selected camera is closed. |
| `CAMERA_STATE_OPENING` | 0 | The selected camera is currently closed but will be opened soon. |
| `CAMERA_STATE_CLOSING` | 3 | The selected camera is currently closed but will be closed soon. |

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

### pause

- Pause the selected camera if a camera has been selected via `selectCamera`.
- Pause the default camera if no camera is selected via `selectCamera`.

```java
void pause() throws CameraEnhancerException
```

**Code Snippet**

```java
CameraEnhancer cameraEnhancer = new CameraEnhancer(MainActivity.this); 
cameraEnhancer.pause();
```

**Remarks**

If the `pause` method is triggered:

- The camera UI will be stopped on the last captured frame before you `pause` the camera.
- The camera is still open.
- The video streaming input is not stopped.
- DCE video buffer will continue appending frames.

&nbsp;

### resume

- Resume the selected camera if a camera has been selected via `selectCamera`.
- Resume the default camera if no camera is selected via `selectCamera`.

```java
void resume() throws CameraEnhancerException
```

**Code Snippet**

```java
CameraEnhancer cameraEnhancer = new CameraEnhancer(MainActivity.this); 
cameraEnhancer.resume();
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

&nbsp;

## Frame Acquiring Methods

| Method | Description |
| ------ | ----------- |
| [`getFrameFromBuffer`](#getframefrombuffer) | Get the latest frame from the buffer. The boolean value determines whether the fetched frame will be removed from the buffer. |
| [`addListener`](#addlistener) | Add a listener to the camera enhancer instance. |
| [`removeListener`](#removelistener) | Remove a previously added listener from the camera enhancer instance. |

&nbsp;

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

## Enhanced Features

| Method | Description |
| ------ | ----------- |
| [`enableFeatures`](#enablefeature) | Enable camera enhancer features by inputting `EnumEnhancerFeatures` values. |
| [`disableFeatures`](#disablefeature) | Disable camera enhancer features by inputting `EnumEnhancerFeatures` values. |
| [`isFeatureEnabled`](#isfeatureenabled) | Check whether the input features are enabled. |

&nbsp;

### enableFeatures

Enable camera enhancer features by inputting `EnumEnhancerFeatures` value.

```java
void enableFeatures(int enhancerFeatures) throws CameraEnhancerException
```

**Parameters**

`enhancerFeatures`: The combined value of `EnumEnhancerFeatures`.  

| `EnumEnhancerFeatures` | Value | Description |
| ---------------- | ----- | ----------- |
| `EF_FRAME_FILTER` | 0x01 | The frame sharpness filter feature of DCE. By enabling this feature, the low-quality frame will be recognized and discarded automatically. |
| `EF_SENSOR_CONTROL` | 0x02 | The sensor filter feature of DCE. By enabling this feature, the frames will be discarded automatically while the device is shaking. |
| `EF_ENHANCED_FOCUS` | 0x04 | The enhanced focus feature. DCE will support the camera in triggering auto-focus. |
| `EF_FAST_MODE` | 0x08 | The fast mode of DCE. By enabling the fast mode, the frames will be cropped to speed up the following processing. |
| `EF_AUTO_ZOOM` | 0x10 | The auto-zoom feature of DCE. By enabling this feature, the camera will automatically zoom in to the interest area. |
| `EF_SMART_TORCH` | 0x20 | Add a smart torch on the UI. The torch will be hided when the environment brightness is high and displayed when the brightness is low. |
| `EF_ALL` | 0x3f | Enable all the above features. |

**Code Snippet**

```java
CameraEnhancer cameraEnhancer = new CameraEnhancer(MainActivity.this);
cameraEnhancer.enableFeatures(EnumEnhancerFeatures.FRAME_FILTER | EnumEnhancerFeatures.SENSOR_CONTROL);
```

**Remarks**

The enable action will not be approved if the license is invalid. If your input values include the features that have been already enabled, these features will keep the enabled status.

&nbsp;

### disableFeatures

Disable camera enhancer features by inputting `EnumEnhancerFeatures` values.

```java
void disableFeatures(int enhancerFeatures)
```

**Parameters**

`enhancerFeatures`: The combined value of `EnumEnhancerFeatures`.

| `EnumEnhancerFeatures` | Value | Description |
| ---------------- | ----- | ----------- |
| `EF_FRAME_FILTER` | 0x01 | The frame sharpness filter feature of DCE. By enabling this feature, the low-quality frame will be recognized and discarded automatically. |
| `EF_SENSOR_CONTROL` | 0x02 | The sensor filter feature of DCE. By enabling this feature, the frames will be discarded automatically while the device is shaking. |
| `EF_ENHANCED_FOCUS` | 0x04 | The enhanced focus feature. DCE will support the camera in triggering auto-focus. |
| `EF_FAST_MODE` | 0x08 | The fast mode of DCE. By enabling the fast mode, the frames will be cropped to speed up the following processing. |
| `EF_AUTO_ZOOM` | 0x10 | The auto-zoom feature of DCE. By enabling this feature, the camera will automatically zoom in to the interest area. |
| `EF_SMART_TORCH` | 0x20 | Add a smart torch on the UI. The torch will be hided when the environment brightness is high and displayed when the brightness is low. |
| `EF_ALL` | 0x3f | Enable all the above features. |

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

`enhancerFeatures`: The combined value of `EnumEnhancerFeatures`.

| `EnumEnhancerFeatures` | Value | Description |
| ---------------------- | ----- | ----------- |
| `EF_FRAME_FILTER` | 0x01 | The frame sharpness filter feature of DCE. By enabling this feature, the low-quality frame will be recognized and discarded automatically. |
| `EF_SENSOR_CONTROL` | 0x02 | The sensor filter feature of DCE. By enabling this feature, the frames will be discarded automatically while the device is shaking. |
| `EF_ENHANCED_FOCUS` | 0x04 | The enhanced focus feature. DCE will support the camera in triggering auto-focus. |
| `EF_FAST_MODE` | 0x08 | The fast mode of DCE. By enabling the fast mode, the frames will be cropped to speed up the following processing. |
| `EF_AUTO_ZOOM` | 0x10 | The auto-zoom feature of DCE. By enabling this feature, the camera will automatically zoom in to the interest area. |
| `EF_SMART_TORCH` | 0x20 | Add a smart torch on the UI. The torch will be hided when the environment brightness is high and displayed when the brightness is low. |
| `EF_ALL` | 0x3f | Enable all the above features. |

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

&nbsp;

## Advanced Camera Control Methods

| Method | Description |
| ------ | ----------- |
| [`setFrameRate`](#setframerate) | Set the frame rate to the input value (if the input value is available for the device). |
| [`getFrameRate`](#getframerate) | Get the current frame rate. |
| [`getResolutionList`](#getresolutionlist) | Get all available resolutions. |
| [`setResolution`](#setresolution) | Set the resolution to the input value (if the input value is available for the device). |
| [`getResolution`](#getresolution) | Get the current resolution. |
| [`setZoom`](#setzoom) | Set the zoom factor. Once `setZoom` is triggered and approved, the zoom factor of the actived camera will immediately become the input value. |
| [`setFocus`](#setfocus) | Focus once at the input position. |
| [`setScanRegion`](#setscanregion) | Set the scan region with a RegionDefinition value. The frame will be cropped according to the scan region. |
| [`getScanRegion`](#getscanregion) | Get the scan region. |
| [`setScanRegionVisible`](#setscanregionvisible) | Set whether to display the **scanRegion** on the UI. |
| [`getScanRegionVisible`](#getscanregionvisible) | Get whether the **scanRegion** will be displayed on the UI. |
| [`updateAdvancedSettingsFromFile`](#updateadvancedsettingsfromfile) | Update advanced parameter settings including filter, sensor and focus settings from a JSON file. |
| [`updateAdvancedSettingsFromString`](#updateadvancedsettingsfromstring) | Update advanced parameter settings including filter, sensor and focus settings from a JSON string. |

### setFrameRate

Camera Enhancer will try to set the frame rate around the input value.

```java
void setFrameRate(int frameRate) throws CameraEnhancerException
```

**Parameters**

`frameRate`: An int value that refers to the target frame rate.  

**Code Snippet**

```java
CameraEnhancer cameraEnhancer = new CameraEnhancer(MainActivity.this); 

cameraEnhancer.setFrameRate(25);
```

**Remarks**

The available frame rate setting threshold is always intermittent, which means the input value might not match any available frame rate threshold. If the input value is below the lowest available threshold, the frame rate will be set to the lowest available threshold. If the input value is above the lowest available threshold but still does not match any threshold, the frame rate will be set to the highest available threshold below the input value.

&nbsp;

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

`resolution`: One of the int value that preset in `EnumResolution`.

| `EnumResolution` | Value | Description |
| ---------------- | ----- | ----------- |
| `RESOLUTION_AUTO` | 0 | The resolution will be set automatically. |
| `RESOLUTION_480P` | 1 | The resolution will be set to 480P. |
| `RESOLUTION_720P` | 2 | The resolution will be set to 720P. |
| `RESOLUTION_1080P` | 3 | The resolution will be set to 1080P. |
| `RESOLUTION_2K` | 4 | The resolution will be set to 2K. |
| `RESOLUTION_4K` | 5 | The resolution will be set to 4K. |

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

&nbsp;

## Camera UI Methods

| Method | Description |
| ------ | ----------- |
| [`setCameraView`](#setcameraview) | Bind a instance of `DCECameraView` to the `CameraEnhancer`. |
| [`getCameraView`](#getcameraview) | Get the object of DCECameraView that is binded to the `CameraEnhancer`. |

&nbsp;

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
