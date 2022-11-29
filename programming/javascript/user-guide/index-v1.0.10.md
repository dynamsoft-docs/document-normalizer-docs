---
layout: default-layout
title: Dynamsoft Document Normalizer for JavaScript - User Guide
description: This is the user guide of Dynamsoft Document Normalizer for JavaScript SDK.
keywords: user guide, javascript
needAutoGenerateSidebar: true
needGenerateH4Content: true
noTitleIndex: true
---

# Document Normalizer for Your Website - User Guide

Dynamsoft Document Normalizer JavaScript Edition (DDN-JS) is equipped with industry-leading quadrilateral detection and image normalization algorithms. Using its well-designed API, you can turn your web page into a document normalizer with a few lines of code.

![version](https://img.shields.io/npm/v/dynamsoft-document-normalizer.svg)
![downloads](https://img.shields.io/npm/dm/dynamsoft-document-normalizer.svg)
![jsdelivr](https://img.shields.io/jsdelivr/npm/hm/dynamsoft-document-normalizer.svg)
![vulnerabilities](https://img.shields.io/snyk/vulnerabilities/npm/dynamsoft-document-normalizer.svg)

Once the DDN-JS SDK is integrated into your web pages, your users can access a connected camera through their browser, point it at the document and detect the document's boundaries in real-time. Once a detection looks promising, users can enter edit mode to fine-tune the boundaries before using them to obtain a normalized image of the document. The normalization process now includes cropping, perspective correction, brightness adjustment, contrast adjustment, and color mode conversion.

In this guide, you will learn how to integrate this SDK into your website step by step.

<span style="font-size:20px">Table of Contents</span>

- [Document Normalizer for Your Website - User Guide](#document-normalizer-for-your-website---user-guide)
  - [Example Usage](#example-usage)
    - [Check the code](#check-the-code)
      - [About the code](#about-the-code)
    - [Test the code](#test-the-code)
  - [Building your own page](#building-your-own-page)
    - [Include the SDK](#include-the-sdk)
      - [Use a CDN](#use-a-cdn)
      - [Host the SDK yourself](#host-the-sdk-yourself)
    - [Configure the SDK](#configure-the-sdk)
      - [Specify the license](#specify-the-license)
      - [Specify the location of the "engine" files](#specify-the-location-of-the-engine-files)
    - [Interact with the SDK](#interact-with-the-sdk)
      - [Create a `DocumentNormalizer` object](#create-a-documentnormalizer-object)
      - [Create a `CameraEnhancer` object and bind it to the `DocumentNormalizer` object](#create-a-cameraenhancer-object-and-bind-it-to-the-documentnormalizer-object)
      - [Change the camera settings (optional)](#change-the-camera-settings-optional)
      - [Customize the DocumentNormalizer Settings (optional)](#customize-the-documentnormalizer-settings-optional)
      - [Start the detection and normalization](#start-the-detection-and-normalization)
    - [Customize the UI (optional)](#customize-the-ui-optional)
  - [API Documentation](#api-documentation)
  - [System Requirements](#system-requirements)
  - [Release Notes](#release-notes)
  - [Next Steps](#next-steps)

## Example Usage

Let's start by testing an example of the SDK which demonstrates how to detect quadrilaterals (document boundaries) from a live video stream and use a selected quadrilateral to obtain a normalized image of the document. To run the example, the following are required

1. Internet connection
2. [A supported browser](#system-requirements)
3. An accessible Camera

### Check the code

The complete code of the example is shown below:

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <script src="https://cdn.jsdelivr.net/npm/dynamsoft-camera-enhancer@3.1.0/dist/dce.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/dynamsoft-document-normalizer@1.0.10/dist/ddn.js"></script>
</head>

<body>
    <h1>Capture A Document</h1>
    <button id="confirmQuadForNormalization">Edit Boundaries</button>
    <button id="normalizeWithConfirmedQuad">Normalize and Capture</button>
    <div id="div-ui-container" style="margin-top: 10px;height: 500px;"></div>
    <div id="normalized-result"></div>
    <script>
        let normalizer = null;
        let cameraEnhancer = null;

        /** LICENSE ALERT - README
         * To use the library, you need to first specify a license key using the API "license" as shown below.
        */
        Dynamsoft.DDN.DocumentNormalizer.license = "DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9";
        /**
         * You can visit https://www.dynamsoft.com/customer/license/trialLicense?utm_source=github&product=ddn&package=js to get your own trial license good for 30 days.
         * For more information, see https://www.dynamsoft.com/document-normalizer/docs/programming/javascript/user-guide.html?ver=1.0.10&utm_source=github#specify-the-license or contact support@dynamsoft.com.
         * LICENSE ALERT - THE END
        */

        (async function() {
          try {
            cameraEnhancer = await Dynamsoft.DCE.CameraEnhancer.createInstance();
            normalizer = await Dynamsoft.DDN.DocumentNormalizer.createInstance();
            let options = {
              resultsHighlightBaseShapes: Dynamsoft.DCE.DrawingItem
            };
            await normalizer.setImageSource(cameraEnhancer, options);

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
              try {
                const normalizedImageResult = await normalizer.normalizeWithConfirmedQuad();
                if(normalizedImageResult) {
                  // Show the normalized image in a Canvas
                  const cvs = normalizedImageResult.image.toCanvas();
                  document.querySelector("#normalized-result").appendChild(cvs);
                  console.log(normalizedImageResult);
                }
              } catch(ex) {
                alert(ex.message || ex);
              }
            });

            // Start scanning document boundaries.
            await normalizer.startScanning(true);
          } catch (ex) {
            let errMsg;
            if (ex.message.includes("network connection error")) {
              errMsg = "Failed to connect to Dynamsoft License Server: network connection error. Check your Internet connection or contact Dynamsoft Support (support@dynamsoft.com) to acquire an offline license.";
            } else {
              errMsg = ex.message||ex;
            }
            alert(errMsg);
            console.error(errMsg);
          }
        })();
    </script>
</body>

</html>
```

<p align="center" style="text-align:center; white-space: normal; ">
  <a target="_blank" href="https://jsfiddle.net/DynamsoftTeam/3ojhuyz6/" title="Run via JSFiddle">
    <img src="https://cdn.jsdelivr.net/npm/simple-icons@3.0.1/icons/jsfiddle.svg" alt="Run via JSFiddle" width="20" height="20" style="width:20px;height:20px;">
  </a>
</p>

-----

#### About the code

- `DocumentNormalizer.createInstance()`: this method creates a `DocumentNormalizer` object called `normalizer`.

- `CameraEnhancer.createInstance()`: this method creates a `CameraEnhancer` object called `cameraEnhancer`, which is used to control the camera as well as the default user interface. Once `CameraEnhancer` is bound to `normalizer` via `setImageSource()`, the `normalizer` will get video frames from the camera for detection and normalization.

- `onQuadDetected`: this event is triggered every time the SDK finds at least one quadrilateral after scanning a video frame. The `quadResults` object contains all the found quadrilaterals. In this example, the results are logged in the browser console.

- `startScanning(true)`: starts continuous video frame scanning. It returns a `Promise` which resovles when the camera is opened, the video shows up on the page and begins to scan (which means the `normalizer` starts to get frames for detection).

- `confirmQuadForNormalization()`: pauses the video stream and enter "editor mode" where the quadrilaterals in current frame are selectable and editable. You can select one quadrilateral that surrounds the target document and edit it to be as accurate as possible.

- `normalizeWithConfirmedQuad()`: normalizes the image with the quadrilateral to obtain an image of the document as "normalizedImageResult".

### Test the code

Create a text file with the name "Normalize-Video-Frames.html", fill it with the code above and save. After that, open the example page in a browser, allow the page to access your camera and the video will show up on the page. After that, you can point the camera at something with a quadrilateral border to detect it.

> You can also just test it at [https://jsfiddle.net/DynamsoftTeam/3ojhuyz6/](https://jsfiddle.net/DynamsoftTeam/3ojhuyz6/)

Please note:

- Although the page should work properly when opened directly as a file ("file:///"), it's recommended that you deploy it to a web server and access it via HTTPS.
- On first use, you need to wait a few seconds for the SDK to initialize.
- The license "DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9" used in this sample is an online license and requires network connection to work.

If the test doesn't go as expected, you can [contact us](https://www.dynamsoft.com/company/contact/?utm_source=guide&product=ddn&package=js).

## Building your own page

In this section, we'll break down and show all the steps required to build a web page for document capturing with DDN-JS.

### Include the SDK

#### Use a CDN

The simplest way to include the SDK is to use either the [jsDelivr](https://jsdelivr.com/) or [UNPKG](https://unpkg.com/) CDN. The "hello world" example above uses **jsDelivr**. We should also include the SDK Dynamsoft Camera Enhancer which provides camera support.

- jsDeliv

  ```html
  <script src="https://cdn.jsdelivr.net/npm/dynamsoft-document-normalizer@1.0.10/dist/ddn.js"></script>
  <script src="https://cdn.jsdelivr.net/npm/dynamsoft-camera-enhancer@3.1.0/dist/dce.js"></script>
  ```

- UNPKG

  ```html
  <script src="https://unpkg.com/dynamsoft-document-normalizer@1.0.10/dist/ddn.js"></script>
  <script src="https://unpkg.com/dynamsoft-camera-enhancer@3.1.0/dist/dce.js"></script>
  ```

#### Host the SDK yourself

Besides using the CDN, you can also download the SDK and host its files on your own website / server before including it in your application.

> Also read [how to do the same for Dynamsoft Camera Enhancer](https://www.dynamsoft.com/camera-enhancer/docs/programming/javascript/user-guide/index.html?ver=latest#host-the-sdk-yourself).

To download the SDK:

- yarn

  ```cmd
  yarn add dynamsoft-document-normalizer@1.0.10
  ```

- npm

  ```cmd
  npm install dynamsoft-document-normalizer@1.0.10
  ```

Depending on how you downloaded the SDK and where you put it, you can typically include it like this:

  ```html
  <script src="/dynamsoft-document-normalizer-js-1.0.10/dist/ddn.js"></script>
  ```

or

  ```html
  <script src="/node_modules/dynamsoft-document-normalizer/dist/ddn.js"></script>
  ```

or

  ```ts
  import { DocumentNormalizer } from 'dynamsoft-document-normalizer';
  ```

### Configure the SDK

Before using the SDK, you need to configure a few things.

#### Specify the license

The SDK requires a license to work, use the API `license` to specify a license key.

```javascript
Dynamsoft.DDN.DocumentNormalizer.license = "YOUR-LICENSE-KEY";
```

To test the SDK, you can request a 30-day trial license via the [customer portal](https://www.dynamsoft.com/customer/license/trialLicense?utm_source=guide&product=ddn&package=js).

#### Specify the location of the "engine" files

If the engine files (\*.worker.js, \*.wasm.js and \*.wasm, etc.) are NOT in the same location with the main SDK file (ddn.js), you can use the API `engineResourcePath` to specify the engine path, for example:

```javascript
// The following code uses the jsDelivr CDN, feel free to change it to your own location of these files.
Dynamsoft.DDN.DocumentNormalizer.engineResourcePath = "https://cdn.jsdelivr.net/npm/dynamsoft-document-normalizer@1.0.10/dist/";
```

### Interact with the SDK

#### Create a `DocumentNormalizer` object

To use the SDK, we first create a `DocumentNormalizer` object.

```javascript
let normalizer = null;
try {
    normalizer = await Dynamsoft.DDN.DocumentNormalizer.createInstance();
} catch (ex) {
    console.error(ex);
}
```

#### Create a `CameraEnhancer` object and bind it to the `DocumentNormalizer` object

The `CameraEnhancer` object is necessary to access the camera to display the video stream and draw the found quads.

```javascript
let cameraEnhancer = null;
cameraEnhancer = await Dynamsoft.DCE.CameraEnhancer.createInstance();
let options = {
    resultsHighlightBaseShapes: Dynamsoft.DCE.DrawingItem
};
await normalizer.setImageSource(cameraEnhancer, options);
```

#### Change the camera settings (optional)

In some cases, a different camera might be required instead of the default one. Also, a different resolution might work better. To change the camera or the resolution, we use the `CameraEnhancer` object. Learn more [here](https://www.dynamsoft.com/camera-enhancer/docs/programming/javascript/api-reference/camera-control.html?ver=3.1.0&utm_source=guide&product=ddn&package=js).

```javascript
// The following lines set which camera and what resolution to use.
let allCameras = await cameraEnhancer.getAllCameras();
await cameraEnhancer.selectCamera(allCameras[0]);
await cameraEnhancer.setResolution(1280, 720);
```

#### Customize the DocumentNormalizer Settings (optional)

Check out the following code:

```javascript
// Sets up the scanner behavior
let scanSettings = await normalizer.getScanSettings();
// Sets a scan interval in milliseconds so the SDK may release the CPU from time to time.
// (setting this value larger is a simple way to save battery power and reduce device heating).
scanSettings.intervalTime = 100; // The default is 0.
await normalizer.updateScanSettings(scanSettings);

// Sets up the runtime settings
let runtimeSettings = await normalizer.getRuntimeSettings();
runtimeSettings.ImageParameterArray[0].BinarizationModes[0].ThresholdCompensation = 3;
runtimeSettings.ImageParameterArray[0].ScaleDownThreshold = 512;
await normalizer.setRuntimeSettings(runtimeSettings);

// or uses a built-in runtime setting template "lowcontrast"
await normalizer.setRuntimeSettings("lowcontrast");

// Resets the runtime setting to default
await normalizer.resetRuntimeSettings();
```

As you can see from the above code snippets, there are two types of configurations:

- `get/updateScanSettings`: Configures the scanning behavior of the normalizer which only includes `intervalTime` for now.

- `get/set/resetRuntimeSettings`: Configures the normalizer engine with a built-in template or a template represented by a JSON object. This will override the previous RuntimeSettings.

#### Start the detection and normalization

After attaching an event handler to the event `onQuadDetected`. We can call `startScanning(true)` to start the detection process.

For user interaction, we should also add buttons for fucntions that invoke `confirmQuadForNormalization()` and `normalizeWithConfirmedQuad()`.

```javascript
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
  try {
    const normalizedImageResult = await normalizer.normalizeWithConfirmedQuad();
    if(normalizedImageResult) {
      // Show the normalized image in a Canvas
      const cvs = normalizedImageResult.image.toCanvas();
      document.querySelector("#normalized-result").appendChild(cvs);
      console.log(normalizedImageResult);
    }
  } catch(ex) {
    alert(ex.message || ex);
  }
});
// Start video scanning.
await normalizer.startScanning(true);
```

### Customize the UI (optional)

The built-in UI of the `DocumentNormalizer` object is defined in the file `dist/ddn.ui.html` . There are 4 ways to customize it:

- Modify the file `ddn.ui.html` directly.

  This option is only possible when you host this file on your own web server instead of using a CDN. Note that this file is put in the **dist** directory of the **dynamsoft-camera-enhancer** package.

- Copy the file `ddn.ui.html` to your application, modify it and pass its URL to the API `setUIElement` to set it as the default UI.

  ```javascript
  await cameraEnhancer.setUIElement("THE-URL-TO-THE-FILE");
  ```

- Append the default UI element to your page, customize it before showing it.

  ```html
  <div id="camera-container"></div>
  ```

  ```javascript
  document.getElementById('camera-container').appendChild(cameraEnhancer.getUIElement());
  document.getElementsByClassName('dce-btn-close')[0].hidden = true; // Hide the close button
  ```

- Build the UI element into your own web page and specify it with the API `setUIElement(HTMLElement)`.

  - Embed the video

    ```html
    <div id="div-ui-container" style="width:100%;height:100%;">
        <div class="dce-video-container" style="position:relative;width:100%;height:500px;"></div>
    </div>
    <script>
        (async () => {
            let cameraEnhancer = await Dynamsoft.DCE.CameraEnhancer.createInstance();
            let normalizer = await Dynamsoft.DDN.DocumentNormalizer.createInstance();
            let options = {
              resultsHighlightBaseShapes: Dynamsoft.DCE.DrawingItem
            };
            await normalizer.setImageSource(cameraEnhancer, options);

            await document.getElementById('div-ui-container').append(cameraEnhancer.getUIElement());
        })();
    </script>
    ```

    > The video element will be created and appended to the DIV element with the class `dce-video-container` , make sure the class name is the same. Also note that the CSS property `position` of the DIV element must be either `relative` , `absolute` , `fixed` , or `sticky` .

  - Add the camera list and resolution list

    If the class names for these lists match the default ones, `dce-sel-camera` and `dce-sel-resolution` , the SDK will automatically populate the lists and handle the camera/resolution switching.

    ```html
    <div id="div-ui-container">
        <select class="dce-sel-camera"></select>
        <select class="dce-sel-resolution"></select>
        <br>
        <div class="dce-video-container" style="position:relative;width:100%;height:500px;"></div>
    </div>
    ```

    > By default, only 3 hard-coded resolutions (1920 x 1080, 1280 x 720, 640 x 480), are populated as options. You can show a customized set of options by hardcoding them.

    ```html
    <select class="dce-sel-resolution">
        <option class="dce-opt-gotResolution" value="got"></option>
        <option data-width="1280" data-height="720">1280x720</option>
        <option data-width="1920" data-height="1080">1920x1080</option>
    </select>
    ```

    > Generally, you need to provide a resolution that the camera supports. However, in case a camera does not support the specified resolution, it usually uses the closest supported resolution. As a result, the selected resolution may not be the actual resolution. In this case, add an option with the class name `dce-opt-gotResolution` (as shown above) and the SDK will then use it to show the **actual resolution**.

## API Documentation

You can check out the detailed documentation about the APIs of the SDK at
[https://www.dynamsoft.com/document-normalizer/docs/programming/javascript/api-reference/?ver=latest](https://www.dynamsoft.com/document-normalizer/docs/programming/javascript/api-reference/?ver=latest).

## System Requirements

DDN-JS SDK requires the following features to work:

- Secure context (HTTPS deployment)

  When deploying your application / website for production, make sure to serve it via a secure HTTPS connection. This is required for two reasons
  
  - Access to the camera video stream is only granted in a security context. Most browsers impose this restriction.
  > Some browsers like Chrome may grant the access for `http://127.0.0.1` and `http://localhost` or even for pages opened directly from the local disk (`file:///...`). This can be helpful for temporary development and test.
  
  - Dynamsoft License requires a secure context to work.

- `WebAssembly`, `Blob`, `URL`/`createObjectURL`, `Web Workers`

  The above four features are required for the SDK to work.

- `MediaDevices`/`getUserMedia`

  This API is only required for in-browser video streaming.

- `getSettings`

  This API inspects the video input which is a `MediaStreamTrack` object about its constrainable properties.

The following table is a list of supported browsers based on the above requirements:

  Browser Name | Version
  :-: | :-:
  Chrome | v85+ on desktop, v94+ on Android
  Firefox | v99+ on desktop and Android
  Safari | v15+ on iOS

Apart from the browsers, the operating systems may impose some limitations of their own that could restrict the use of the SDK.

## Release Notes

Learn about what are included in each release at [https://www.dynamsoft.com/document-normalizer/docs/programming/javascript/release-notes/?ver=latest](https://www.dynamsoft.com/document-normalizer/docs/programming/javascript/release-notes/?ver=latest).

## Next Steps

Now that you have got the SDK integrated, you can choose to move forward in the following directions

1. Check out the [official samples](https://github.com/Dynamsoft/document-normalizer-javascript-samples).
2. Learn about the available [APIs](https://www.dynamsoft.com/document-normalizer/docs/programming/javascript/api-reference/?ver=latest).
