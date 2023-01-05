---
layout: default-layout
title: Dynamsoft Document Normalizer JavaScript API Reference - Main Page
description: This is the main page of Dynamsoft Document Normalizer for JavaScript SDK API Reference.
keywords: DocumentNormalizer, api reference, javascript, js
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: API Reference
noTitleIndex: true
---

# API Reference - JavaScript

The primary class of the library is `DocumentNormalizer`. The following code snippets shows the basic usage. 

* Detect and normalize a still image

```js
let normalizer = await Dynamsoft.DDN.DocumentNormalizer.createInstance();
let quads = await normalizer.detectQuad(imagePath);
let normalizedImageResult = await normalizer.normalize(imagePath, { quad: quads[0].location });
if(normalizedImageResult) {
    // Show the normalized image in a Canvas
    const cvs = normalizedImageResult.image.toCanvas();
    document.querySelector("#normalized-result").appendChild(cvs);
}
// Download the normalized image
let img = await normalizedImageResult.saveToFile("example.png", true);
```

* Detect and normalize continuous video frames

```js
(async function() {
    cameraEnhancer = await Dynamsoft.DCE.CameraEnhancer.createInstance();
    normalizer = await Dynamsoft.DDN.DocumentNormalizer.createInstance();
    await normalizer.setImageSource(cameraEnhancer, { resultsHighlightBaseShapes: Dynamsoft.DCE.DrawingItem });

    await document.getElementById('div-ui-container').append(cameraEnhancer.getUIElement());
    
    // Triggered when a quadrilateral is detected from a video frame.
    normalizer.onQuadDetected = (quadResults, sourceImage) => {
        console.log(quadResults);
    };

    // Click the button to pause the video and edit a quadrilateral.
    document.getElementById('confirmQuadForNormalization').addEventListener("click", () => {
        normalizer.confirmQuadForNormalization();
    });

    // Click the button to normalize with the selected/adjusted quadrilateral.
    document.getElementById('normalizeWithConfirmedQuad').addEventListener("click", async () => {
        const normalizedImageResult = await normalizer.normalizeWithConfirmedQuad();
        if(normalizedImageResult) {
        // Show the normalized image in a Canvas
        const cvs = normalizedImageResult.image.toCanvas();
        document.querySelector("#normalized-result").appendChild(cvs);
        console.log(normalizedImageResult);
        }
    });
    // Start scanning document boundaries.
    await normalizer.startScanning(true);
})();
```

The APIs for this class include

## Initialization Control

| Method               | Description |
|----------------------|-------------|
| [license](initialize.md#license) | Uses an alphanumeric string to specify the license. |
| [createInstance()](initialize.md#createinstance) | Creates a `DocumentNormalizer` instance. |
| [dispose()](initialize.md#dispose) | Dispose the DocumentNormalizer instance. |
| [disposed](initialize.md#disposed) | Returns whether the instance has been disposed. |
| [engineResourcePath](initialize.md#engineresourcepath) | Specifies the path from where the engine and models, etc. can be loaded. |
| [loadWasm()](initialize.md#loadwasm) | Loads the engine. |
| [isWasmLoaded()](initialize.md#iswasmloaded) | Returns whether the engine has been loaded. |
| [getVersion()](initialize.md#getversion) | Returns the version of the library. |

## Video Detecting Methods

| Method               | Description |
|----------------------|-------------|
| [setImageSource()](normalize.md#setimagesource) | Sets an image source for continous scanning. |
| [onQuadDetected](normalize.md#onquaddetected) | This event is triggered when a new quadrilateral is detected. |
| [setQuadResultFilter()](normalize.md#setquadresultfilter) | Sets a function to filter a detected quadrilateral. |
| [confirmQuadForNormalization()](normalize.md#confirmquadfornormalization) | Confirms which quadrilateral will be referred for later normalization. |
| [normalizeWithConfirmedQuad()](normalize.md#normalizewithconfirmedquad) | Normalizes the image whith a selected quadrilateral. |
| [startScanning()](normalize.md#startscanning) | Opens the camera and starts continuous scanning of incoming images. |
| [pauseScanning()](normalize.md#pausescanning) | Pauses continuous scanning but keep the video stream. |
| [resumeScanning()](normalize.md#resumescanning) | Resumes continuous scanning. |
| [stopScanning()](normalize.md#stopscanning) | Stops continuous scanning and closes the video stream. |

## Detect and Normalize Methods

| Method               | Description |
|----------------------|-------------|
| [detectQuad()](normalize.md#detectquad) | Detects quadrilaterals from an image. |
| [normalize()](normalize.md#normalize) | Normalizes the source image based on the settings in options. |

## Scan Settings Methods

| Method               | Description |
|----------------------|-------------|
| [getScanSettings()](settings.md#getscansettings) | Returns the current [`ScanSettings`](./interfaces/scansettings.md). |
| [updateScanSettings()](settings.md#updatescansettings) | Updates scan settings with the object passed in. |

## Runtime Settings Methods

| Method               | Description |
|----------------------|-------------|
| [getRuntimeSettings()](settings.md#getruntimesettings) | Gets runtime settings with a template represented by a JSON object. |
| [setRuntimeSettings()](settings.md#setputruntimesettings) | Sets runtime settings with a JSON object. |
| [resetRuntimeSettings()](settings.md#resetputruntimesettings) | Resets all parameters to default values. |

## Interfaces

* [`DetectedQuadResult`](./interfaces/detected-quad-result.md)
* [`NormalizedImageResult`](./interfaces/normalized-image-result.md)
* [`ScanSettings`](./interfaces/scansettings.md)
* [`Quadrilateral`](./interfaces/quadrilateral.md)
* [`Point`](./interfaces/point.md)
* [`ImageSource`](./interfaces/imagesource.md)
* [`DDNImage`](./interfaces/ddn-image.md)
* [`DSImage`](./interfaces/dsimage.md)

<!-- ## Enumerations

- [`EnumImagePixelFormat`]({{ site.enumerations }}image-pixel-format.html?src=android)

## Others

View the [Error Codes]({{ site.enumerations }}error-code.html) -->
