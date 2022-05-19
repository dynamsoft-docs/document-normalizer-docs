---
layout: default-layout
title: Dynamsoft Document Normalizer - Introduction
keywords: introduction, documentation
description: Dynamsoft Document Normalizer - Introduction
---

# Introduction to Dynamsoft Document Normalizer

When gathering information (text, barcodes, machine readable zones, etc.) from images of typical documents such as price tags, office documents, driver's licenses, and ID cards, the quality or complexity of these images is often a hindrance. To address this, Dynamsoft Document Normalizer (DDN) is an SDK designed to analyze structural information such as document boundaries, table boundaries, etc. on images, and then normalize the ROI image so that subsequent processes can better focus on key information.

DDN powers your software development from the following aspects:

- Robust quadrilateral detection for different structures such as document/table boundaries.
- Various content normalization features such as border crop/deskew/perspective correction/colur mode/contrast/brightness, etc.
- Scenario-oriented customizablity such as image processing modes

With DDN, you can efficiently embed the functionality of quadrilateral detection and content normalization in multiple platforms. DDN also provides various image processing features, allowing you to customize DDN and meet your business needs.

## Key Features

### Robust quadrilateral detection

With DDN, you can extract the four corner coordinates of one or multiple documents/tables.

- Document boundary detection

<div align="center">
   <p><img src="assets/document-boundary-detection.jpg" alt="Document boundary detection" width="50%" /></p>
   <p>Figure 1 – Document boundary detection</p>
</div>

- Table boundary detection

<div align="center">
   <p><img src="assets/table-boundary-detection.jpg" alt="Table boundary detection" width="50%" /></p>
   <p>Figure 2 – Table boundary detection</p>
</div>

- Multiple boundaries in one detection

<div align="center">
   <p><img src="assets/multiple-boundaries-detection.jpg" alt="Multiple boundaries detection" width="50%" /></p>
   <p>Figure 3 – Multiple boundaries in one detection</p>
</div>

Don’t worry if your documents/tables are blurry, damaged, too colorful or peculiar in any way. DDN provides various image processing settings for fully customization. Our default settings are sufficient for most cases. However, additional tweaks can be made for your specific cases to achieve greater speed and accuracy.

### Various content normalization features

Do you want to convert a document photo that is randomly taken, to a document image that looks like a carefully scanned document? With DDN, you can easily extract documents from photos, and normalize them in various ways.

- Border crop

Trims the current image, removing the space around the borders.

- Deskew

It is usually used to straighten scanned documents. Deskewing is the process of removing skew by rotating the image by the same degree but in the opposite direction.

- Perspective correction

It is usually used to correct perspective distortion introduced by the camera’s perspective relation to the target.

- Colour mode

Change the colour space of the output normalized image. DDN supports outputting colour, grayscale and binary images.

<div align="center">
   <p><img src="assets/color-mode-image.jpg" alt="Original image" width="100%" /></p>
   <p>Figure 4 – Original image and output colour/grayscale/binary image</p>
</div>

- Brightness and Contrast

Adjust the brightness and contrast of the output normalized image.

### Scenario-oriented customizablity

In order to cope with various scenarios, DDN provides a variety of image processing modes at each stage of the algorithm process to maintain great scalability.

For example, [`BinarizationModes`]({{site.parameters_reference }}binarization-modes.html) provides several image binarization methods and [`RegionPredetectionModes`]({{site.parameters_reference }}region-predetection-modes.html) provides different pre-detection methods to help locate the ROI.

These modes can be configured not only through API but also through a configuration template (as file, string, JSON etc.). Furthermore, the implementation of these modes can be customized according to customer scenarios to seamlessly integrated with customer's project.

## How to Use

### Overview of DDN SDK Modules

DDN SDK consists of four modules as shown in the following table. This structure is shared between all platform versions of DDN SDK, which makes it easier to integrate and support multiple operating systems in your apps.

Table 1 – Modules description of the SDK

| Module Name | Description | Primary Classes |
| ---- | ----------- |-------|
| **DynamsoftDocumentNormalizer** | Provide APIs related to quad detection and various content normalization. | **DocumentNormalizer** |
| **DynamsoftIntermediateResult** | The common intermediate result library of Dynamsoft's capture vision SDKs, including all intermediate results produced in the process of decoding a barcode, recognizing a label or normalizing a document. | **The APIs are for internal use only and is not public yet**|
| **DynamsoftImageProcessing** | The image processing library of Dynamsoft's capture vision SDKs, including image processing algorithms and APIs. | **The APIs are for internal use only and is not public yet**|
| **DynamsoftCore**  | The core library of Dynamsoft's capture vision SDKs, including common basic structure and license related APIs. | **LicenseManager**<br/>**...**|

The primary class in DDN SDK:

- **DocumentNormalizer**: It supports quad detection and image normalization for still pictures and live video. Common detections include document/table boundary detection. Common normalizations include border crop/deskew/perspective correction/colour mode/brightness and contrast.

### Quick Start for Mobile Scenarios

In real life, document quad detection and content normalization often occurs in mobile catpure scenarios. In order to simplify the integration cost of camera control, camera preview and interactive editing functions etc., we recommend that you use <a href="https://www.dynamsoft.com/camera-enhancer/docs/introduction/" target="_blank">Dynamsoft Camera Enhancer(DCE) SDK</a> with DDN to complete the document detection and normalization on the mobile side. The DCE SDK provides three primary classes:

- **CameraEnhancer**: It provides basic camera control functions as well as advanced features such as video buffering, frame filtering and fast mode for fast camera module integration.
- **DCECameraView**: It is designed to display the camera preview, overlay, scan region, etc.
- **DCEImageEditorView**: It supports previewing still images, displaying graphic items (rectangles, quads, text, etc.) and interactively adjusting the vertices of graphic items.

The easiest steps to integrate DDN and DCE into your application are as follows：

1. Add the DDN and DCE libraries and their dependencies to your project.
2. Initialize the license via `LicenseManger`.
3. Display the camera preview by creating an instance of `DCECameraView` and binding it to a new instance of `CameraEnhancer`.
4. Create an instance of `DocumentNormalizer` and set the instance of `CameraEnhancer` as the image source.
5. Register a quad detection result listener to receive detection events. You can obtain the detected quads and the corresponding image in the callback function.
6. If you want to make additional manual adjustments to the detected quads, preview the captured image and detected quads in `DCEImageEditorView`, which also provides the user with a magnified view to move points precisely.
7. Use the selected quad output by `DCEImageEditorView` to normalize the captured image according to your application's needs.

Please refer to the following articles for more details:

- <a href="https://www.dynamsoft.com/document-normalizer/docs/programming/android/user-guide.html" target="_blank">Getting Started with DDN Android SDK</a>
- <a href="https://www.dynamsoft.com/document-normalizer/docs/programming/ios/user-guide.html" target="_blank">Getting Started with DDN iOS SDK</a>

## Usage scenarios

### Retail

In retail, DDN can help detect the price label boundaries or table boundaries in images. Additionally, the extracted images can be used for recognition to extract text information.

### Identity Documents

In many scenarios, identity documents such as id card/passport need to be quickly located and identified. However, the captured images of id card/passport might not be uniformed. You may encounter images taken with different angles, lightings, clearness…etc. With DDN, you can detect the the boundaries of identity document images and normalize the ROI with ease. Therefore, the information extraction of ID document images will become easier.

### Document scanning and archiving

In government or large corporations, we want to keep an electronic version of paper documents. We often do so by taking photos or scanning of the documents. However, the captured document images might not be uniformed. You may encounter images taken with different angles, lightings, clearness…etc. With DDN, you can normalize the document images with ease. DDN also provide various settings so you can customize the outcome of the normalized document image to meet your needs.

## Cross-Platform Programming Languages

DDN is designed to be cross-platform. The core of DDN is written in C/C++ for performance. The library is wrapped for Java, Objective-C and other programming languages so that users can use DDN on iOS, Android, Windows, and Linux. Below is a list of supported OSes and corresponding programming languages:

| OS            | Programming Language |
|---------------|----------------------|
|Windows        | C/C++                |
|Linux          | C/C++                |
|Android        | Java                 |
|iOS            | Swift/Objective-C    |
