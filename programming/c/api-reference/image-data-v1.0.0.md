---
layout: default-layout
title: ImageData Struct - Dynamsoft Document Normalizer SDK C Edition
description: This page shows ImageData struct definition of Dynamsoft Document Normalizer SDK C Edition.
keywords: ImageData, struct, api reference
---

# ImageData Struct

Stores the image data.  

## Definition

```c
typedef struct tagImageData
{
    int bytesLength;
    unsigned char* bytes;
    int width;
    int height;
    int stride;
    ImagePixelFormat format;
}ImageData;
```  

### bytesLength

The length of the image data byte array.

### bytes

The image data content in a byte array.

### width

The width of the image in pixels.  

### height

The height of the image in pixels.  

### stride

The stride (or scan width) of the image.

### format

The image pixel format used in the image byte array.

**See Also**

[ImagePixelFormat]({{ site.enumerations }}image-pixel-format.html?src=c)
