---
layout: default-layout
title: Dynamsoft Core Java Class - ImageData
description: This page shows the ImageData Class of Dynamsoft Core for Java Language.
keywords: ImageData, java
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# ImageData

Stores the image data.  

```java
class com.dynamsoft.core.ImageData
```  

## Attributes

| Attribute | Type | Description |
|---------- | ---- | ----------- |
| [`bytes`](#bytes) | *byte[]* | The array of bytes that stores the pixel buffer of the image. |
| [`width`](#width) | *int* | The width of the image in pixels. |
| [`height`](#height) | *int* | The height of the image in pixels. |
| [`stride`](#stride) | *int* | The stride is measured by the byte length of each line in the pixel buffer. |
| [`format`](#format) | *int* | The image pixel format used in the image byte array. View [`EnumImagePixelFormat`]({{ site.enumerations }}image-pixel-format.html?src=android) for all supported image pixel formats. |

&nbsp;

### bytes

The image data content in a byte array.

```java
byte[] bytes
```

&nbsp;

### width

The width of the image in pixels.  

```java
int width
```

&nbsp;

### height

The height of the image in pixels.  

```java
int height
```

&nbsp;

### stride

The stride (or scan width) of the image.

```java
int stride
```

&nbsp;

### format

The image pixel format used in the image byte array.

```java
int format
```

## Methods

| Method | Description |
| ------ | ----------- |
| `toBitmap` | Convert the `ImageData` object to a `Bitmap` object. |

### toBitmap

Convert the `ImageData` object to a `Bitmap` object.

```java
Bitmap toBitmap() throws CoreException
```

**Return Value**

A Bitmap object.
