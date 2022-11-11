---
layout: default-layout
title: Dynamsoft Document Normalizer iOS API Reference - NormalizedImageResult Class
description: This page shows the NormalizedImageResult Class of Dynamsoft Document Normalizer for iOS SDK.
keywords: NormalizedImageResult, class, api reference, ios
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# iNormalizedImageResult

Stores the detected quad result.

```objc
@interface iNormalizedImageResult
```

| Attribute | Type | Descriptions |
| --------- | ---- | ------------ |
| [`image`](#image) | [`iImageData*`](image-data.md) | The normalized image in iImageData structure. |

| Method | Descriptions |
| -------|------------ |
| [`saveToFile`](#savetofile) | Save the normalized image to a file. |

## image

The location of the detected quad result.

```objc
iImageData* image;
```

## saveToFile

Save the normalized image to a file.

```objc
-(BOOL)saveToFile:(NString*)filePath error:(NSError**)error
```

**Parameters**

`[in] filePath`: The output file path of the normalized image.  
`[in,out] error`: Input a pointer to an error object. If an error occurs, this pointer is set to an actual error object containing the error information. You may specify nil for this parameter if you do not want the error information.

**Remarks**

- This method supports exporting bmp, jpeg, png, pdf formats.
- For non-pdf formats, if the file path already exists, this method will overwrite the existing file
- For pdf format, if the file path already exists, this method will append a new page with the image to the existing pdf file.

