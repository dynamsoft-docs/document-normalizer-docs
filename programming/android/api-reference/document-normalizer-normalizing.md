---
layout: default-layout
title: Dynamsoft Document Normalizer Android API Reference - DocumentNormalizer Detect and Normalize Methods
description: This page shows DocumentNormalizer Detect and Normalize methods of Dynamsoft Document Normalizer for Android SDK.
keywords: detectQuad, normalize, DocumentNormalizer, api reference, android
needAutoGenerateSidebar: true
noTitleIndex: true
needGenerateH3Content: false
---


# Detect and Normalize Methods

| Method               | Description |
|----------------------|-------------|
| [`detectQuad(buffer)`](#detectquad(buffer)) | Detect quad from the memory buffer containing image pixels in defined format. |
| [`detectQuad(file)`](#detectquad(file)) | Detect quad from an image file. |
| [`detectQuad(bitmap)`](#detectquad(bitmap)) | Detect quad from a buffered image(bitmap). |
| [`normalize(buffer)`](#normalize(buffer)) | Normalize image from the memory buffer containing image pixels in defined format. |
| [`normalize(file)`](#normalize(file)) | Normalize an image file. |
| [`normalize(bitmap)`](#normalize(bitmap)) | Normalize a buffered image(bitmap). |

---

## detectQuad(buffer)

Detect quad from the memory buffer containing image pixels in defined format.

```java
DetectedQuadResult[] detectQuad(ImageData buffer) throws DocumentNormalizerException
```

**Parameters**

`[in]  buffer`: The memory buffer containing image pixels in defined format.

**Return Value**

The detected quads in the raw image buffer. Refer [`DetectedQuadResult`](detected-quad-result.md).

**Exceptions**

[`DocumentNormalizerException`](document-normalizer-exception.md)

There are several approaches for you to get a buffered image.

### Get ImageData from DCEFrame

You can import CameraEnhancer to acquire buffered video frames from `frameOutputCallback` or `videoBuffer` of DCE.

**Code Snippet**

```java
/*You can get frames from frame output call back if you import dynamsoft camera enhancer package.*/
/*You can get all the required parameters of decodeBuffer from DCEFrame.*/
import com.dynamsoft.dce.CameraEnhancer;

DocumentNormalizer normalizer = new DocumentNormalizer();
mCameraEnhancer.addListener(new DCEFrameListener() {
  @Override
  public void frameOutputCallback(DCEFrame dceFrame, long l) {
    try {
      ImageData buffer = new ImageData(dceFrame.getImageData(),dceFrame.getWidth(),dceFrame.getHeight(),dceFrame.getStrides()[0],dceFrame.getPixelFormat());

      DetectedQuadResult[] quads = normalizer.detectQuad(buffer);
    } catch (DocumentNormalizerException e) {
      e.printStackTrace();
    }
  }
});
```

### Get ImageData from Android Camera2

When you are using Android Camera2, you can get video frames from ImageReader.

**Code Snippet**

```java
previewReader.setOnImageAvailableListener(new ImageReader.OnImageAvailableListener() {
  @Override
  public void onImageAvailable(ImageReader reader) {
    Image mImage = reader.acquireLatestImage();
    ByteBuffer bufferY = mImage.getPlanes()[0].getBuffer();
    int strideY = mImage.getPlanes()[0].getRowStride() / mImage.getPlanes()[0].getPixelStride();
    ByteBuffer bufferU = mImage.getPlanes()[1].getBuffer();
    int strideU = mImage.getPlanes()[1].getRowStride() / mImage.getPlanes()[1].getPixelStride();
    ByteBuffer bufferV = mImage.getPlanes()[2].getBuffer();
    int strideV = mImage.getPlanes()[2].getRowStride() / mImage.getPlanes()[2].getPixelStride();
    int padingY = mImage.getPlanes()[0].getRowStride() - mImage.getWidth();
    int padingU = mImage.getPlanes()[1].getRowStride() - mImage.getWidth();
    byte[] newData = new byte[bufferY.limit()];
    newData = new byte[bufferY.limit() + bufferU.limit() + 1 + padingY + padingU];
    bufferV.get(newData, bufferY.limit() + padingY, 1);
    bufferU.get(newData, bufferY.limit() + padingY + 1, bufferU.limit());
    bufferY.get(newData, 0, bufferY.limit());
    int[] strides = new int[]{strideY, strideU, strideV};
    try {
      ImageData buffer = new ImageData(newData, strideY, mImage.getHeight(), strideY, 3);

      DetectedQuadResult[] quads = normalizer.detectQuad(buffer);
    } catch (DocumentNormalizerException e) {
      e.printStackTrace();
    }
  }
},handler);
```

## detectQuad(file)

Detect quad from an image file.

```java
DetectedQuadResult[] detectQuad(String fileFullPath) throws DocumentNormalizerException
```

**Parameters**

`[in]fileFullPath`: A string defining the file path. It supports BMP, TIFF, JPG, PNG files.  

**Return Value**

The detected quads in the image file. Refer [`DetectedQuadResult`](detected-quad-result.md).

**Exceptions**

[`DocumentNormalizerException`](document-normalizer-exception.md)

**Code Snippet**

```java
try {
    DocumentNormalizer normalizer = new DocumentNormalizer();
    DetectedQuadResult[] result = normalizer.detectQuad("your file path");
} catch (DocumentNormalizerException e) {
    e.printStackTrace();
}
```

## detectQuad(bitmap)

Detect quad from a buffered image (bitmap).

```java
DetectedQuadResult[] detectQuad(Bitmap bitmap) throws DocumentNormalizerException
```

**Parameters**

`[in]bitmap`: The android bitmap to be detected.

**Return Value**

The detected quads in the buffered image (bitmap). Refer [`DetectedQuadResult`](detected-quad-result.md).

**Exceptions**

[`DocumentNormalizerException`](document-normalizer-exception.md), IOException

**Code Snippet**

```java
try {
    DocumentNormalizer normalizer = new DocumentNormalizer();

    // user code: get bitmap from somewhere
    Bitmap bitmap = GetBitmapFromSomeWhere();

    DetectedQuadResult[] result = normalizer.detectQuad(bitmap);
} catch (DocumentNormalizerException e) {
    e.printStackTrace();
}
```

## normalize(buffer)

Normalize image from the memory buffer containing image pixels in defined format.

```java
NormalizedImageResult normalize(ImageData buffer, Quadrilateral quad) throws DocumentNormalizerException
```

**Parameters**

`[in] buffer`: The memory buffer containing image pixels in defined format.
`[in] quad`: The detected quad for normalizing.

**Return Value**

The normalized image result. Refer [`NormalizedImageResult`](normalized-image-result.md)

**Exceptions**

[`DocumentNormalizerException`](document-normalizer-exception.md)

There are several approaches for you to get a buffered image.

- Refer [`here`](#get-imagedata-from-dceframe) to get the ImageData from DCEFrame.
- Refer [`here`](#get-imagedata-from-android-camera2) to get the ImageData from Android Camera2.

**Code Snippet**

```java
try {
    DocumentNormalizer normalizer = new DocumentNormalizer();
    
    // user code: get ImageData from somewhere
    ImageData buffer = GetImageDataFromSomeWhere();

    DetectedQuadResult[] quads = normalizer.detectQuad(buffer);
    if(quads.length > 0) {
      NormalizedImageResult normalizedImage = normalizer.normalize(buffer, quads[0]);
    }
} catch (DocumentNormalizerException e) {
    e.printStackTrace();
}
```

## normalize(file)

Normalize an image file.

```java
NormalizedImageResult normalize(String fileFullePath, Quadrilateral quad) throws DocumentNormalizerException
```

**Parameters**

`[in] fileFullPath`: A string defining the file path. It supports BMP, TIFF, JPG, PNG files.  
`[in] quad`: The detected quad for normalizing.

**Return Value**

The normalized image result. Refer [`NormalizedImageResult`](normalized-image-result.md)

**Exceptions**

[`DocumentNormalizerException`](document-normalizer-exception.md)

**Code Snippet**

```java
try {
    DocumentNormalizer normalizer = new DocumentNormalizer();
    
    String imageFilePath = "your file path";

    DetectedQuadResult[] quads = normalizer.detectQuad(imageFilePath);
    if(quads.length > 0) {
      NormalizedImageResult normalizedImage = normalizer.normalize(imageFilePath, quads[0]);
    }
} catch (DocumentNormalizerException e) {
    e.printStackTrace();
}
```

## normalize(bitmap)

Normalize a buffered image (bitmap).

```java
NormalizedImageResult normalize(Bitmap bitmap, Quadrilateral quad) throws DocumentNormalizerException
```

**Parameters**

`[in] bitmap`: The android bitmap to be normalized.
`[in] quad`: The detected quad for normalizing.

**Return Value**

The normalized image result. Refer [`NormalizedImageResult`](normalized-image-result.md)

**Exceptions**

[`DocumentNormalizerException`](document-normalizer-exception.md), IOException

**Code Snippet**

```java
try {
    DocumentNormalizer normalizer = new DocumentNormalizer();

    // user code: get bitmap from somewhere
    Bitmap bitmap = GetBitmapFromSomeWhere();

    DetectedQuadResult[] quads = normalizer.detectQuad(bitmap);
    if(quads.length > 0) {
      NormalizedImageResult normalizedImage = normalizer.normalize(bitmap, quads[0]);
    }
} catch (DocumentNormalizerException e) {
    e.printStackTrace();
}
```
