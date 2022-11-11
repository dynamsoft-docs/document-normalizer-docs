---
layout: default-layout
title: Dynamsoft Document Normalizer Android API Reference - Camera Methods
description: This page shows Camera methods of Dynamsoft Document Normalizer for Android SDK.
keywords: Camera methods, DocumentNormalizer, api reference, android
needAutoGenerateSidebar: true
noTitleIndex: true
pageStartVer: 1.0
---


# Video Detecting Methods

> Note:
>  
> - You have to include `CameraEnhancer` when using **Video Detecting Methods**.  
> - `CameraEnhancer` provide APIs that help you quickly deploy a camera module and capture video streaming for document normalizer.  
> - Through **Video Detecting Methods** you can control whether to start video streaming document detecting and get the detection results.  

| Method | Description |
|--------|-------------|
| [`setImageSource`](#setimagesource) | Sets an instance of ImageSource to get images.  |
| [`startDetecting`](#startdetecting) | Start the document quad detection thread in the video streaming scenario. |
| [`stopDetecting`](#stopdetecting) | Stop the document quad detection thread in the video streaming scenario. |
| [`setDetectResultListener`](#setdetectresultlistener) | Set callback interface to process detection results generated during frame detecting. |

---

## setImageSource

Sets an instance of ImageSource to get images. `CameraEnhancer` is a specific implementation of ImageSource, which can help the Document Normalizer to acquire video frames continuously for recognition.

```java
void setImageSource(ImageSource source)
```

**Parameters**

`[in] source`: An instance of ImageSource. If you are using `Dynamsoft Camera Enhancer`(DCE) to capture camera frames, pass an instance of `CameraEnhancer`.

**Code Snippet**

This code snippet displays a complete code on how to add CameraEnhancer to your project and start detecting and get detection results from the video streaming.

```java
DocumentNormalizer normalizer;
CameraEnhancer mCameraEnhancer;

@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    setContentView(R.layout.activity_main);

    // Be sure that you have added a cameraView in the layout file.
    DCECameraView cameraView = findViewById(R.id.cameraView);

    try {
        // Create an instance of Dynamsoft Document Normalizer.
        normalizer = new DocumentNormalizer();
    } catch (DocumentNormalizerException e) {
        e.printStackTrace();
    }
    mCameraEnhancer = new CameraEnhancer(MainActivity.this);
    mCameraEnhancer.setCameraView(cameraView);

    // Bind the Camera Enhancer instance to the Document Normalizer instance.
    normalizer.setImageSource(mCameraEnhancer);

    // Result callback configurations
    DetectResultListener mDetectResultListener = new DetectResultListener() {
        // Obtain the detected quad detection results and display.
        @Override
        public void detectResultCallback(int id, ImageData imageData, DetectedQuadResult[] detectedResults) {
            // Add your code to execute when quad detection results are returned.
        }
    };

    normalizer.setDetectResultListener(mDetectResultListener);
}

@Override
public void onResume() {
    // Open the camera and start video quad detecting 
    try {
        mCameraEnhancer.open();
    } catch (CameraEnhancerException e) {
        e.printStackTrace();
    }
    normalizer.startDetecting();
    super.onResume();
}

@Override
public void onPause() {
    // Stop video quad detecting 
    try {
        mCameraEnhancer.close();
    } catch (CameraEnhancerException e) {
        e.printStackTrace();
    }
    normalizer.stopDetecting();
    super.onPause();
}
```

## startDetecting

Start the document quad detection thread in the video streaming scenario. Please be sure that you have bound a Camera Enhancer to the document normalizer before you trigger `startDetecting`.

```java
void startDetecting()
```

**Code Snippet**

You can view the complete code snippet in [`setImageSource`](#setimagesource).

## stopDetecting

Stop the document quad detection thread in the video streaming scenario.

```java
void stopDetecting()
```

**Code Snippet**

You can view the complete code snippet in [`setImageSource`](#setimagesource).

## setDetectResultListener

Set the callback interface to process detection results generated during frame detecting.

```java
void setDetectResultListener(DetectResultListener detectResultListener)
```

**Parameters**

`[in] detectResultListener`: The Callback interface.

**Code Snippet**

You can view the complete code snippet in [`setImageSource`](#setimagesource).
