---
title: Dynamsoft Content Normalizer - ImageData Struct
keywords: imagedata, struct, api, api reference, c, c language, c++, cplusplus, dcn, documentation
description: Dynamsoft Content Normalizer - ImageData Struct
---


# ImageData
Stores the image data.

```cpp
typedef struct tagImageData  ImageData
```  

## Attributes
  
| Attribute | Type |
|---------- | ---- |
| [`bytesLength`](#byteslength) | *int* |
| [`bytes`](#bytes) | *unsigned char\** |
| [`width`](#width) | *int* |
| [`height`](#height) | *int* |
| [`stride`](#stride) | *int* |
| [`format`](#format) | [`ImagePixelFormat`]({{ site.common_enumerations }}image-pixel-format.html) |


&nbsp;

### bytesLength
The length of the image data byte array.

```cpp
int bytesLength
```

### bytes
The image data content in a byte array.

```cpp
int bytes
```

### width
The width of the image in pixels.

```cpp
int width
```

### height
The height of the image in pixels.

```cpp
int height
```

### stride
The stride (or scan width) of the image.

```cpp
int stride
```

### format
The image pixel format used in the image byte array.

```cpp
ImagePixelFormat format
```


