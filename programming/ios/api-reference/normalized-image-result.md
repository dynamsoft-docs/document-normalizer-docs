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

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface iNormalizedImageResult
```
2. 
```swift
class iNormalizedImageResult : NSObject
```

| Attribute | Type | Descriptions |
| --------- | ---- | ------------ |
| [`image`](#image) | [`iImageData*`](image-data.md) | The normalized image in iImageData structure. |

| Method | Descriptions |
| -------|------------ |
| [`saveToFile`](#savetofile) | Save the normalized image to a file. |

## image

The location of the detected quad result.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
iImageData* image;
```
2. 
```swift
var image: iImageData { get set }
```

## saveToFile

Save the normalized image to a file.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(BOOL)saveToFile:(NString*)filePath error:(NSError**)error
```
2. 
```swift
func saveToFile(_ filePath: String) throws
```

**Parameters**

`[in] filePath`: The output file path of the normalized image.  
`[in,out] error`: Input a pointer to an error object. If an error occurs, this pointer is set to an actual error object containing the error information. You may specify nil for this parameter if you do not want the error information.

**Remarks**

- This method supports exporting bmp, jpeg, png, pdf formats.
- For non-pdf formats, if the file path already exists, this method will overwrite the existing file
- For pdf format, if the file path already exists, this method will append a new page with the image to the existing pdf file.

