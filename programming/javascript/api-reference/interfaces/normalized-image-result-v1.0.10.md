---
layout: default-layout
title: Dynamsoft Document Normalizer JavaScript Interface - NormalizedImageResult
description: This page shows the NormalizedImageResult Interface of Dynamsoft Document Normalizer for JavaScript SDK.
keywords: NormalizedImageResult, interface, api reference, javascript
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# NormalizedImageResult

Stores the normalized image result.

## Attributes

| Attribute | Type |
| --------- | ---- |
| [`image`](#image) | [`DDNImage`](ddn-image.md) |

### image

The normalized image in DDNImage structure.

## APIs

| API | Descriptions |
| --------- | ------------ |
| [`saveToFile()`](#savetofile) | Saves the normalized image to file. |

### saveToFile

Save the normalized image (only one) to a `File` object in memory. Download it to the local driver if needed.

```js
saveToFile: (name: string, download?: boolean) => Promise<File>;
```

**Parameters**

`name` : specifies the name of the `File` object in memory. If a `File` object with the same name exists, replace it. `.png` or `.jpg` must be used to specify the file's format in the name.

`download`: specifies whether to download the file once it's created. If set to false or not specified, keep the file in memory.

**Return value**

A promise resolving to the `File` that stores the normalized image data. 

**Code snippet**

```js
let resultImg = await normalizedImageResult.saveToFile("example.png"); //.png or .jpg must be used in the name
```
