---
layout: default-layout
title: Dynamsoft Document Normalizer Android API Reference - NormalizedImageResult Class
description: This page shows the NormalizedImageResult Class of Dynamsoft Document Normalizer for Android SDK.
keywords: NormalizedImageResult, class, api reference, android
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# NormalizedImageResult

Stores the detected quad result.

```java
class com.dynamsoft.ddn.NormalizedImageResult;
```

| Attribute | Type | Descriptions |
| --------- | ---- | ------------ |
| [`image`](#image) | [`ImageData`](image-data.md) | The normalized image in ImageData structure. |

| Method | Descriptions |
| -------|------------ |
| [`saveToFile`](#savetofile) | Save the normalized image to a file. |

## image

The location of the detected quad result.

```java
ImageData image;
```

## saveToFile

Save the normalized image to a file.

```java
void saveToFile(String filePath) throws DocumentNormalizerException
```

**Parameters**

`[in] filePath` The path of the output image file with the extension specifying the image format. It supports BMP, PNG, JPEG and PDF file types.

**Remarks**

- This method supports exporting bmp, jpeg, png, pdf formats.
- For non-pdf formats, if the file path already exists, this method will overwrite the existing file
- For pdf format, if the file path already exists, this method will append a new page with the image to the existing pdf file.
