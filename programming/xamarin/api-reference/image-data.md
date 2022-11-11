---
layout: default-layout
title: Class ImageData - Dynamsoft Document Normalizer Xamarin.Forms API Reference
description: This is the page of class ImageData of Dynamsoft Document Normalizer Xamarin.Forms SDK.
keywords: ImageData, Xamarin.Forms
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# ImageData

Stores the image data.  

```csharp
class DDNXamarin.ImageData
```  

## Attributes Summary

| Attribute | Type | Description |
|---------- | ---- | ----------- |
| [`Bytes`](#bytes) | *int* | The byte data of the image. |
| [`Width`](#width) | *int* | The width of the image. |
| [`Height`](#height) | *int* | The height of the image. |
| [`Stride`](#stride) | *int* | The stride of the image. |
| [`Format`](#format) | *int* | The pixel format of the image. |
| [`Orientation`](#orientation) | *int* | The orientation of the image. |

## Methods Summary

| Methods | Description |
| ------- | ----------- |
| [`ToImageSource`](#toimagesource) | Convert the `ImageData` to `Xamarin.Forms.ImageSource`. |

&nbsp;

## Attributes and Methods Details

### Bytes

The byte data of the image.

```csharp
IList<byte> Bytes;
```

### Width

The width of the image.

```csharp
int Width;
```

### Height

The height of the image.

```csharp
int Height;
```

### Stride

The stride of the image.

```csharp
int Stride;
```

### Format

The pixel format of the image.

```csharp
int Format;
```

### orientation

The orientation of the image. The following image illustrates the `orientation` value of the `ImageData`.

<div align="center">
    <p><img src="../assets/getOrientation.png" width="70%" alt="getOrientation"></p>
    <p>Illustration of the orientation</p>
</div>

```csharp
int Orientation;
```

### ToImageSource

Convert the `ImageData` to `Xamarin.Forms.ImageSource`.

```csharp
ImageSource toImageSource();
```
