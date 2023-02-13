---
layout: default-layout
title: Dynamsoft Document Normalizer iOS API Reference - DocumentNormalizer Detect and Normalize Methods
description: This page shows DocumentNormalizer Detect and Normalize methods of Dynamsoft Document Normalizer for iOS SDK.
keywords: detectQuadFromBuffer,detectQuadFromFile,detectQuadFromImage,normalizeBuffer,normalizeFile, normalizeImage, DocumentNormalizer, api reference, ios
needAutoGenerateSidebar: true
noTitleIndex: true
needGenerateH3Content: false
---


# Detect and Normalize Methods

| Method               | Description |
|----------------------|-------------|
| [`detectQuadFromBuffer`](#detectquadfrombuffer) | Detect quad from the memory buffer containing image pixels in defined format. |
| [`detectQuadFromFile`](#detectquadfromfile) | Detect quad from an image file. |
| [`detectQuadFromImage`](#detectquadfromimage) | Detect quad from a buffered image(uiimage). |
| [`normalizeBuffer`](#normalizebuffer) | Normalize image from the memory buffer containing image pixels in defined format. |
| [`normalizeFile`](#normalizefile) | Normalize an image file. |
| [`normalizeImage`](#normalizeimage) | Normalize a buffered image(uiimage). |

---

## detectQuadFromBuffer

Detect quad from the memory buffer containing image pixels in defined format.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(NSArray<iDetectedQuadResult*>*) detectQuadFromBuffer:(iImageData*)buffer error:(NSError**)error;
```
2. 
```swift
func detectQuadFromBuffer(_ data: iImageData) throws -> [iDetectedQuadResult]
```

**Parameters**

`[in] buffer`: The memory buffer containing image pixels in defined format.  
`[in,out] error`: Input a pointer to an error object. If an error occurs, this pointer is set to an actual error object containing the error information. You may specify nil for this parameter if you do not want the error information.

**Return Value**

The detected quads in the raw image buffer. Refer [`iDetectedQuadResult`](detected-quad-result.md).

### Get ImageData from DCEFrame

If you have imported **DynamsoftCameraEnhancer.framework**, you can get video frames from the `frameOutputCallback`. DCEFrame object contains all required parameters of `decodeBuffer` method.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
//Get frames in callback methods.
- (void)frameOutPutCallback:(DCEFrame *)frame timeStamp:(NSTimeInterval)timeStamp{
    iImageData* buffer = [[iImageData alloc] init];
    buffer.bytes = frame.imageData;
    buffer.width = frame.width;
    buffer.height = frame.height;
    buffer.stride = frame.stride;
    buffer.format = frame.pixelFormat;
    NSError* error;
    NSArray<iDetectedQuadResult*>* detectedResults = [normalizer detectQuadFromBuffer:buffer error:&error];
}
```
2. 
```swift
func frameOutPutCallback(_ frame: DCEFrame, timeStamp: TimeInterval){
  let buffer = iImageData();
  buffer.bytes = frame.imageData;
  buffer.width = frame.width;
  buffer.height = frame.height;
  buffer.stride = frame.stride;
  buffer.format = frame.pixelFormat;
  let detectedResults = try? normalizer.detectQuadFromBuffer(buffer)
}
```

### Get ImageData from CaptureOutput

If you are acquiring video frames from `captureOutput` callback, you can use the following code to extract the required parameters from `sampleBuffer`.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (void)captureOutput:(AVCaptureOutput *)captureOutput didOutputSampleBuffer:(CMSampleBufferRef)sampleBuffer fromConnection:(AVCaptureConnection *)connection;
{
  // Extract image data from sampleBuffer.
  CVImageBufferRef imageBuffer = CMSampleBufferGetImageBuffer(sampleBuffer);
  CVPixelBufferLockBaseAddress(imageBuffer, kCVPixelBufferLock_ReadOnly);
  int bufferSize = (int)CVPixelBufferGetDataSize(imageBuffer);
  int imgWidth = (int)CVPixelBufferGetWidth(imageBuffer);
  int imgHeight = (int)CVPixelBufferGetHeight(imageBuffer);
  size_t bpr = CVPixelBufferGetBytesPerRow(imageBuffer);
  void *baseAddress = CVPixelBufferGetBaseAddress(imageBuffer);
  CVPixelBufferUnlockBaseAddress(imageBuffer, kCVPixelBufferLock_ReadOnly);
  NSData * bufferBytes = [NSData dataWithBytes:baseAddress length:bufferSize];
  startRecognitionDate = [NSDate date];
  iImageData* buffer = [[iImageData alloc] init];
  buffer.bytes = bufferBytes;
  buffer.width = imgWidth;
  buffer.height = imgHeight;
  buffer.stride = bpr;
  buffer.format = EnumImagePixelFormatARGB_8888;
  NSArray<iDetectedQuadResult*>* detectedResults = [normalizer detectQuadFromBuffer:buffer error:&error];
}
```
2. 
```swift
func captureOutput(_ output: AVCaptureOutput, didOutput sampleBuffer: CMSampleBuffer, from connection: AVCaptureConnection){
  let imageBuffer:CVImageBuffer = CMSampleBufferGetImageBuffer(sampleBuffer)!
  CVPixelBufferLockBaseAddress(imageBuffer, .readOnly)
  let baseAddress = CVPixelBufferGetBaseAddress(imageBuffer)
  let bufferSize = CVPixelBufferGetDataSize(imageBuffer)
  let width = CVPixelBufferGetWidth(imageBuffer)
  let height = CVPixelBufferGetHeight(imageBuffer)
  let bpr = CVPixelBufferGetBytesPerRow(imageBuffer)
  CVPixelBufferUnlockBaseAddress(imageBuffer, .readOnly)
  startRecognitionDate = NSDate()
  let bufferBytes = Data(bytes: baseAddress!, count: bufferSize)
  let buffer = iImageData()
  buffer.bytes = bufferBytes
  buffer.width = width
  buffer.height = height;
  buffer.stride = bpr;
  buffer.format = .ARGB_8888;
  guard let detectedResults = try? normalizer.detectQuadFromBuffer(buffer)
}
```

## detectQuadFromFile

Detect quad from an image file.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(NSArray<iDetectedQuadResult*>*) detectQuadFromFile:(NSString*)fileFullPath error:(NSError**) error;
```
2. 
```swift
func detectQuadFromFile(_ sourceFilePath: String) throws -> [iDetectedQuadResult]
```

**Parameters**

`[in] fileFullPath`: A string defining the file path. It supports BMP, TIFF, JPG, PNG files.  
`[in,out] error`: Input a pointer to an error object. If an error occurs, this pointer is set to an actual error object containing the error information. You may specify nil for this parameter if you do not want the error information.

**Return Value**

The detected quads in the image file. Refer [`iDetectedQuadResult`](detected-quad-result.md).

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
DynamsoftDocumentNormalizer* normalizer = [[DynamsoftDocumentNormalizer alloc] init];
NSError* error;
NSArray<iDetectedQuadResult*>* detectedResults = [normalizer detectQuadFromFile:@"your image file path" error:&error];
```
2. 
```swift
let normalizer = DynamsoftDocumentNormalizer()
let detectedResults = try? normalizer.detectQuadFromFile("your image file path")
```

## detectQuadFromImage

Detect quad from a buffered image (UIImage).

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(NSArray<iDetectedQuadResult*>*) detectQuadFromImage(UIImage*)uiimage error:(NSError**)error;
```
2. 
```swift
func detectQuadFromFile(_ image: UIImage) throws -> [iDetectedQuadResult]
```


**Parameters**

`[in] uiimage`: The ios UIImage to be detected.  
`[in,out] error`: Input a pointer to an error object. If an error occurs, this pointer is set to an actual error object containing the error information. You may specify nil for this parameter if you do not want the error information.

**Return Value**

The detected quads in the buffered image (UIImage). Refer [`iDetectedQuadResult`](detected-quad-result.md).

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
DynamsoftDocumentNormalizer* normalizer = [[DynamsoftDocumentNormalizer alloc] init];
UIImage* uiimage = GetUIImageFromSomeWhere;
NSError* error;
NSArray<iDetectedQuadResult*>* detectedResults = [normalizer detectQuadFromImage:uiimage error:&error];
```
2. 
```swift
let normalizer = DynamsoftDocumentNormalizer()
let uiimage = GetUIImageFromSomeWhere();
let detectedResults = try? normalizer.detectQuadFromImage(uiimage)
```

## normalizeBuffer

Normalize image from the memory buffer containing image pixels in defined format.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(iNormalizedImageResult*) normalizeBuffer:(iImageData*)buffer quad:(iQuadrilateral*)quad error:(NSError**)error;
```
2. 
```swift
func normalizeBuffer(_ data: iImageData, quad: iQuadrilateral?) throws -> iNormalizedImageResult
```

**Parameters**

`[in] buffer`: The memory buffer containing image pixels in defined format.  
`[in] quad`: The detected quad for normalizing.  
`[in,out] error`: Input a pointer to an error object. If an error occurs, this pointer is set to an actual error object containing the error information. You may specify nil for this parameter if you do not want the error information.

**Return Value**

The normalized image result. Refer [`iNormalizedImageResult`](normalized-image-result.md)

There are several approaches for you to get a buffered image.

- Refer [`here`](#get-imagedata-from-dceframe) to get the iImageData from DCEFrame.
- Refer [`here`](#get-imagedata-from-ios-camera2) to get the iImageData from AVCaptureOut.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
DynamsoftDocumentNormalizer* normalizer = [[DynamsoftDocumentNormalizer alloc] init];
// user code: get iImageData from somewhere
iImageData* buffer = GetImageDataFromSomeWhere;
NSError* error;
NSArray<iDetectedQuadResult*>* detectedResults= [normalizer detectQuadFromBuffer:buffer error:&error];
if([detectedResults count] > 0) {
    iNormalizedImageResult* normalizedImage = [normalizer normalizeBuffer:buffer  quad:detectedResults[0] error:&error];
}
```
2. 
```swift
let normalizer = DynamsoftDocumentNormalizer()
// user code: get iImageData from somewhere
let buffer = GetImageDataFromSomeWhere()
let detectedResults = try? normalizer.detectQuadFromBuffer(buffer)
if(detectedResults.count > 0) {
    let normalizedImage = try? normalizer.normalizeBuffer(buffer, quad:detectedResults[0])
}
```

## normalizeFile

Normalize an image file.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(iNormalizedImageResult*) normalizeFile:(NSString*)fileFullePath quad:(iQuadrilateral*)quad error:(NSError**)error;
```
2. 
```swift
func normalizeFile(_ sourceFilePath: String, quad: iQuadrilateral?) throws -> iNormalizedImageResult
```

**Parameters**

`[in] fileFullPath`: A string defining the file path. It supports BMP, TIFF, JPG, PNG files.  
`[in] quad`: The detected quad for normalizing.  
`[in,out] error`: Input a pointer to an error object. If an error occurs, this pointer is set to an actual error object containing the error information. You may specify nil for this parameter if you do not want the error information.

**Return Value**

The normalized image result. Refer [`iNormalizedImageResult`](normalized-image-result.md)

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
DynamsoftDocumentNormalizer* normalizer = [[DynamsoftDocumentNormalizer alloc] init];
NSError* error;
NSArray<iDetectedQuadResult*>* detectedResults= [normalizer detectQuadFromFile:@"your image file path" error:&error];
if([detectedResults count] > 0) {
    iNormalizedImageResult* normalizedImage = [normalizer normalizeFile:"your image file path" quad:detectedResults[0] error:&error];
}
```
2. 
```swift
let normalizer = DynamsoftDocumentNormalizer()
let detectedResults = try? normalizer.detectQuadFromFile("your image file path")
if(detectedResults.count > 0) {
    let normalizedImage = try? normalizer.normalizeFile("your image file path", quad:detectedResults[0])
}
```

## normalizeImage

Normalize a buffered image (UIImage).

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(iNormalizedImageResult*) normalizeImage:(UIImage*)uiimage quad:(iQuadrilateral*)quad error:(NSError**)error;
```
2. 
```swift
func normalizeImage(_ image: UIImage, quad: iQuadrilateral?) throws -> iNormalizedImageResult
```

**Parameters**

`[in] uiimage`: The ios UIImage to be normalized.  
`[in] quad`: The detected quad for normalizing.  
`[in,out] error`: Input a pointer to an error object. If an error occurs, this pointer is set to an actual error object containing the error information. You may specify nil for this parameter if you do not want the error information.

**Return Value**

The normalized image result. Refer [`iNormalizedImageResult`](normalized-image-result.md)

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
DynamsoftDocumentNormalizer* normalizer = [[DynamsoftDocumentNormalizer alloc] init];
// user code: get UIImage from somewhere
UIImage* uiimage = GetUIImageFromSomeWhere;
NSError* error;
NSArray<iDetectedQuadResult*>* detectedResults= [normalizer detectQuadFromImage:uiimage error:&error];
if([detectedResults count] > 0) {
    iNormalizedImageResult* normalizedImage = [normalizer normalizeImage:uiimage  quad:detectedResults[0] error:&error];
}
```
2. 
```swift
let normalizer = DynamsoftDocumentNormalizer()
// user code: get UIImage from somewhere
let uiimage = GetUIImageFromSomeWhere()
let detectedResults = try? normalizer.detectQuadFromImage(uiimage)
if(detectedResults.count > 0) {
    let normalizedImage = try? normalizer.normalizeImage(uiimage, quad:detectedResults[0])
}
```
