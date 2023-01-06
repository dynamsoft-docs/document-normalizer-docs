---
layout: default-layout
title: Dynamsoft Document Normalizer JavaScript Interface - DDNImage
description: This page shows the DDNImage Interface of Dynamsoft Document Normalizer for JavaScript SDK.
keywords: DDNImage, interface, api reference, javascript
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# DDNImage

Stores the normalized image data. Extends from [`DSImage`](dsimage.md).

## APIs

| API | Descriptions |
| --------- | ------------ |
| [`toCanvas()`](#tocanvas) | Converts the DDNImage to `HTMLCanvasElement`. |
| [`toImage()`](#toimage) | Converts the DDNImage to PNG or JPEG image. |
| [`toBlob()`](#toblob) | Converts the DDNImage to `Blob`. |

### toCanvas

Converts the DDNImage to `HTMLCanvasElement`.

```js
toCanvas: () => HTMLCanvasElement;
```

**Return value**

An [HTMLCanvasElement](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement) that holds the normalized image data.

**Code snippet**

```js
let canvas = ddnImage.toCanvas();
```

### toImage

Converts the DDNImage to PNG or JPEG image.

```js
toImage: (type?: "image/png" | "image/jpeg") => HTMLImageElement;
```

**Parameters**

`type` : "image/png" indicates PNG type, "image/jpeg" indicates JPEG type.

**Return value**

An [HTMLImageElement](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement) that holds the normalized image data.

**Code snippet**

```js
let pngImage = ddnImage.toImage("image/png");
```

### toBlob

Converts the DDNImage to [`Blob`](https://developer.mozilla.org/en-US/docs/Web/API/Blob).

```js
toBlob: (type?: "image/png" | "image/jpeg") => Promise<Blob>;
```

**Parameters**

`type` : "image/png" indicates PNG type, "image/jpeg" indicates JPEG type.

**Return value**

A promise resolving to the `Blob` data that converted from the normalized image data.

**Code snippet**

```js
let data = await ddnImage.toBlob("image/png");
```
