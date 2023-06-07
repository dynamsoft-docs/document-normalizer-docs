---
layout: default-layout
title: Android DCEFrame Class - Dynamsoft Document Normalizer Documents
description: Documentation page of Android DCEFrame Class of Dynamsoft Document Normalizer.
keywords:  Camera Enhancer, Android, DCEFrame
needAutoGenerateSidebar: true
noTitleIndex: true
needGenerateH3Content: true
breadcrumbText: Android DCEFrame Class
---

# DCEFrame

The `DCEFrame` is the class that stores pixel data and further information.

```java
class com.dynamsoft.dce.DCEFrame
```

| Method Name | Description |
| ----------- | ----------- |
| [`getImageData`](#getimagedata) | Get the pixel data of the image. |
| [`getWidth`](#getwidth) | Get the pixel width of the image. |
| [`getHeight`](#getheight) | Get the pixel height of the image. |
| [`getStrides`](#getstrides) | Get the number of row bytes in each image plane (YUV). |
| [`getPixelFormat`](#getpixelformat) | Get the pixel format of the image. Currently, the image output format of `DCEFrame` is always NV21. |
| [`getFrameID`](#getframeid) | Get the `frameID` of the `DCEFrame` object. |
| [`getQuality`](#getquality) | Get the frame quality of the image. User have to enable the frame filter feature to get the quality (high/low) of the image. Otherwise, the frame quality will be unknown. |
| [`getIsCropped`](#getiscropped) | Get a boolean value that means whether the image is cropped. The frames can be cropped if `fast mode` is enabled. |
| [`getCropRegion`](#getcropregion) | Get the crop region of the image (if the image is cropped). |
| [`getOrientation`](#setorientation) | Set the orientation of the image. |
| [`setImageData`](#setimagedata) | Set the pixel data of the image. |
| [`setWidth`](#setwidth) | Set the pixel width of the image. |
| [`setHeight`](#setheight) | Set the pixel height of the image. |
| [`setStrides`](#setstrides) | Set the number of row bytes in each image plane (YUV). |
| [`setPixelFormat`](#setpixelformat) | Set the pixel format of the image. Currently, the image output format of `DCEFrame` is always NV21. |
| [`setFrameID`](#setframeid) | Set the `frameID` of the `DCEFrame` object. |
| [`setQuality`](#setquality) | Set the frame quality of the image. User have to enable the frame filter feature to get the quality (high/low) of the image. Otherwise, the frame quality will be unknown. |
| [`setIsCropped`](#setiscropped) | Set a boolean value that means whether the image is cropped. The frames can be cropped if `fast mode` is enabled. |
| [`setCropRegion`](#setcropregion) | Set a boolean value that means whether the image is cropped. The frames can be cropped if `fast mode` is enabled. |
| [`setOrientation`](#setorientation) | Set the orientation of the image. |
| [`toBitmap`](#tobitmap) | The method converts the image to `Bitmap`. |

&nbsp;

## getImageData

Get the pixel data of the image.

```java
byte[] getImageData()
```

**Return Value**

The method returns a byte list that stores the pixel data of the image.

&nbsp;

## getWidth

Get the pixel width of the image.

```java
int getWidth()
```

**Return Value**

The method returns the pixel width of the image.

&nbsp;

## getHeight

Get the pixel height of the image.

```java
int getHeight()
```

**Return Value**

The method returns the pixel height of the image.

&nbsp;

## getStrides

Get the number of row bytes in each image plane (YUV).

```java
int[] getStrides()
```

**Return Value**

The number of row bytes in each image plane (YUV).

**Remarks**

`strides[0]` is the stride of Y component in the image. `strides[1]` and `strides[2]` are the strides of the U (blue projection) and V (red projection) components in the image.

&nbsp;

## getPixelFormat

Get the pixel format of the image. Currently, the image output format of `DCEFrame` is always NV21.

```java
int getPixelFormat()
```

**Return Value**

The method returns an int value that refers to the pixel format of the image. View morein [`EnumImagePixelFormat`]({{ site.enumerations }}image-pixel-format.html?src=android).

&nbsp;

## getFrameID

Get the `frameID` of the `DCEFrame` object.

```java
int getFrameID()
```

**Return Value**

The method returns an int value that stores the `frameID` of the image.

&nbsp;

## getQuality

Get the frame quality of the image. User have to enable the frame filter feature to get the quality (high/low) of the image. Otherwise, the frame quality will be unknown.

```java
EnumFrameQuality getQuality()
```

**Return Value**

The method returns an enumeration value in [`EnumFrameQuality`](enum-frame-quality.md).

**Remarks**

Users can get all the original DCEFrame via `DCEFrameListener` but only high-quality frame can be acquired from the DCE video buffer if frame filter is enabled. In another word, when frame filter feature is enabled, the frame quality will always be high if they are acquired by triggering `getFrameFromBuffer`.

&nbsp;

## getIsCropped

Get a boolean value that means whether the image is cropped. The frames can be cropped if `fast mode` is enabled.

```java
boolean getIsCropped()
```

**Return Value**

A boolean value. `True` means the image is cropped and `false` means the image has never been cropped.

&nbsp;

## getCropRegion

Get the crop region of the image (if the image is cropped).

```java
Rect getCropRegion()
```

**Return Value**

A Rect value that stores the crop region. If the image is not cropped, the value will be null.

&nbsp;

## getOrientation

Set the orientation of the image.

```java
int getOrientation()
```

**Return Value**

Int value that means the rotation angle of the image. The value is 0, 90, 180 or 270 with depends on the device orientation.

<div align="center">
    <p><img src="assets/getOrientation.png" width="70%" alt="getOrientation"></p>
    <p>All examples of the orientation</p>
</div>

&nbsp;

## setImageData

Set the pixel data of the image.

```java
void setImageData(byte[] imageData)
```

**Parameters**

`imageData`: A byte list that storing the image pixel data.

&nbsp;

## setWidth

Set the pixel width of the image.

```java
void setWidth(int width)
```

**Parameters**

`width`: The pixel value that stands for the width of the image.

&nbsp;

## setHeight

Set the pixel height of the image.

```java
void setHeight(int height)
```

**Parameters**

`height`: The pixel value that stands for the height of the image.

&nbsp;

## setStrides

Set the number of row bytes in each image plane.

```java
void setStrides(int[] strides)
```

**Parameters**

`strides`: The number of row bytes in each image plane.

&nbsp;

## setPixelFormat

Set the pixel format of the image.

```java
void setPixelFormat(int pixelFormat)
```

**Parameters**

`pixelFormat`: The pixelFormat of the image. View more in [`EnumImagePixelFormat`]({{ site.enumerations }}image-pixel-format.html?src=android).

&nbsp;

## setFrameID

Set the `frameID` of the image.

```java
void setFrameID(int frameID)
```

**Parameters**

`frameID`: An int value that stands for the `frameID` of the image.

&nbsp;

## setQuality

Set the frame quality of the image.

```java
void setQuality(EnumFrameQuality quality)
```

**Parameters**

`quality`: One of the [`EnumFrameQuality`](enum-frame-quality.md) value that indicates the frame quality.

&nbsp;

## setIsCropped

Set whether the image is cropped.

```java
void setIsCropped(boolean isCropped)
```

**Parameters**

`isCropped`: A boolean value that means whether the image is cropped.

&nbsp;

## setCropRegion

Set the crop region of the image (if the frame is cropped).

```java
void setCropRegion(Rect region)
```

**Parameters**

`cropRegion`: A Rect value that means crop area of the image (if the frame is cropped).

&nbsp;

## setOrientation

Set the orientation of the image.

```java
void setOrientation(int orientation)
```

**Parameters**

`orientation`: Int value that means the rotation angle of the image.

## toBitmap

The method converts the image to `Bitmap`.

```java
Bitmap toBitmap()
```

**Return Value**

The converted image.

**Code Snippet**

```java
Bitmap frame = DCEFrame.toBitmap();
```
