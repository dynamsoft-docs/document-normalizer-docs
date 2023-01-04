---
layout: default-layout
title: Interface IDocumentNormalizer - Dynamsoft Document Normalizer Xamarin.Forms API Reference
description: This is the page of interface IDocumentNormalizer of Dynamsoft Document Normalizer Xamarin.Forms SDK.
keywords: methods, IDocumentNormalizer, api reference, Xamarin.Forms
needAutoGenerateSidebar: true
noTitleIndex: true
needGenerateH3Content: true
breadcrumbText: Interface IDocumentNormalizer
pageStartVer: 1.0
---

# Interface IDocumentNormalizer

Interface `IDocumentNormalizer` includes methods that supports quad detection and image normalization features.

Common detections include:

- Document boundary detection
- Table boundary detection

Common normalizations include:

- Border crop
- Deskew
- Perspective correction
- Colour mode
- Brightness and Contrast

```java
interface DDNXamarin.IDocumentNormalizer
```

## Video Detecting Methods Summary

| Method | Description |
|--------|-------------|
| [`SetCameraEnhancer`](#setcameraenhancer) | Sets an instance of ImageSource to get images.  |
| [`StartDetecting`](#startdetecting) | Start the document quad detection thread in the video streaming scenario. |
| [`StopDetecting`](#stopdetecting) | Stop the document quad detection thread in the video streaming scenario. |
| [`AddResultListener`](#addresultlistener) | Set callback interface to process detection results generated during frame detecting. |

## Detect and Normalize Methods Summary

| Method               | Description |
|----------------------|-------------|
| [`DetectQuad(ImageData)`](#detectquadimagedata) | Detect quad from the memory buffer containing image pixels in defined format. |
| [`DetectQuad(File)`](#detectquadfile) | Detect quad from an image file. |
| [`Normalize(ImageData)`](#normalizeimagedata) | Normalize image from the memory buffer containing image pixels in defined format. |
| [`Normalize(File)`](#normalizefile) | Normalize an image file. |
  
## Runtime Settings Methods Summary

| Method               | Description |
|----------------------|-------------|
| [`InitRuntimeSettingsFromFile`](#initruntimesettingsfromfile)  | Initialize runtime settings with the settings in a given JSON file. |
| [`InitRuntimeSettings`](#initruntimesettings) | Initialize runtime settings with the settings in a given JSON string. |
| [`OutputRuntimeSettingsToFile`](#outputruntimesettingstofile) | Output runtime settings to a settings file (JSON file). |
| [`OutputRuntimeSettings`](#outputruntimesettings) | Output runtime settings to a string. |

## General Methods Summary

| Method               | Description |
|----------------------|-------------|
| [`SaveToFile`](#savetofile) | Save a `NormalizedImageResult` to the targeting file path. |
| [`GetVersion`](#getversion) | Get version information of SDK.|

&nbsp;

## Video Detecting Methods Details

### SetCameraEnhancer

Sets an instance of ImageSource to get images. `CameraEnhancer` is a specific implementation of ImageSource, which can help the Document Normalizer to acquire video frames continuously for recognition.

```csharp
void SetCameraEnhancer(ICameraEnhancer cameraEnhancer);
```

**Parameters**

`[in] source`: An instance of ImageSource. If you are using `Dynamsoft Camera Enhancer`(DCE) to capture camera frames, pass an instance of `CameraEnhancer`.

**Code Snippet**

This code snippet displays a complete code on how to add CameraEnhancer to your project and start detecting and get detection results from the video streaming.

In **App.xaml.cs**:

```csharp
public partial class App : Application, ILicenseVerificationListener
{
    public static ICameraEnhancer dce;
    public static IDocumentNormalizer ddn;
    public static ILicenseManager licenseManager;

    public App(ICameraEnhancer enhancer, IDocumentNormalizer normalizer, ILicenseManager manager)
    {
        dce = enhancer;
        ddn = normalizer;
        licenseManager = manager;
        // A valid license is required to detect quadrilaterals.
        licenseManager.InitLicense("Put your license here.", this);
        MainPage = new NavigationPage(new MainPage());
    }
}
```

In **MainPage.cs**:

```csharp
public partial class App : Application, IDetectResultListener
{
    public MainPage()
    {
        InitializeComponent();
        App.ddn.SetCameraEnhancer(App.dce);
        App.ddn.AddResultListener(this);
    }

    public void DetectResultCallback(int id, ImageData imageData, DetectedQuadResult[] quadResults)
    {
        // Add your code to execute on quad results are detected.
    }

    protected override void OnAppearing()
    {

        base.OnAppearing();
        App.dce.Open();
        App.ddn.StartDetecting();
    }

    protected override void OnDisappearing()
    {
        base.OnDisappearing();
        App.dce.Close();
        App.ddn.StopDetecting();
    }
}
```

### StartDetecting

Start the document quad detection thread in the video streaming scenario. Please be sure that you have bound a Camera Enhancer to the document normalizer before you trigger `StartDetecting`.

```csharp
void StartDetecting();
```

**Code Snippet**

You can view the complete code snippet in [`SetCameraEnhancer`](#setcameraenhancer).

### stopDetecting

Stop the document quad detection thread in the video streaming scenario.

```csharp
void StopDetecting();
```

**Code Snippet**

You can view the complete code snippet in [`SetCameraEnhancer`](#setcameraenhancer).

### AddResultListener

Set the callback interface to process detection results generated during frame detecting.

```csharp
void AddResultListener(IDetectResultListener resultListener);
```

**Parameters**

`[in] IDetectResultListener`: The Callback interface.

**Code Snippet**

You can view the complete code snippet in [`SetCameraEnhancer`](#setcameraenhancer).

## Detect and Normalize Methods Details

### DetectQuad(ImageData)

Detect quad from the memory buffer containing image pixels in defined format.

```csharp
DetectedQuadResult[] DetectQuad(ImageData imageData);
```

**Parameters**

`[in] imageData`: The memory buffer containing image pixels in defined format.

**Return Value**

The detected quads in the raw image buffer. Refer [`DetectedQuadResult`](detected-quad-result.md).

**Code Snippet**

```csharp
ImageData imageData = new ImageData();
// assign value for imageData
try 
{
    var quadResult = App.ddn.DetectQuad(imageData);
} 
catch(DDNException ex)
{
    Console.WriteLine("Exception caught: ", ex.Message);
}
```

### DetectQuad(File)

Detect quad from an image file.

```csharp
DetectedQuadResult[] DetectQuad(string filePath);
```

**Parameters**

`[in]filePath`: A string defining the file path. It supports BMP, TIFF, JPG, PNG files.  

**Return Value**

The detected quads in the image file. Refer [`DetectedQuadResult`](detected-quad-result.md).

**Code Snippet**

```csharp
try 
{
    var quadResult = App.ddn.DetectQuad("Your file path.");
}
catch(DDNException ex)
{
    Console.WriteLine("Exception caught: ", ex.Message);
}
```

### Normalize(ImageData)

Normalize image from the memory buffer containing image pixels in defined format.

```csharp
NormalizedImageResult Normalize(ImageData imageData, Quadrilateral quadrilateral);
```

**Parameters**

`[in] imageData`: The memory buffer containing image pixels in defined format.
`[in] quadrilateral`: The detected quad for normalizing.

**Return Value**

The normalized image result. Refer [`NormalizedImageResult`](normalized-image-result.md)

**Code Snippet**

```csharp
// You can get ImageData and detected quadlaterals from DetectResultCallback.
public void DetectResultCallback(int id, ImageData imageData, DetectedQuadResult[] quadResults)
{
    if (imageData != null && quadResults != null)
    {
        try 
        {
            var result = App.ddn.Normalize(data, quadResult[0].Location);
        } 
        catch(DDNException ex)
        {
            Console.WriteLine("Exception caught: ", ex.Message);
        }
    }
}
// ImageData in the callback is always a null value unless EnableReturnImageOnNextCallback is triggered.
// Trigger EnableReturnImageOnNextCallback so that you can get ImageData from the next callback.
App.ddn.EnableReturnImageOnNextCallback();
```

### Normalize(File)

Normalize an image file.

```csharp
NormalizedImageResult Normalize(string filePath, Quadrilateral quadrilateral);
```

**Parameters**

`[in] filePath`: A string defining the file path. It supports BMP, TIFF, JPG, PNG files.  
`[in] quadrilateral`: The detected quad for normalizing.

**Return Value**

The normalized image result. Refer [`NormalizedImageResult`](normalized-image-result.md)

**Code Snippet**

```csharp
try 
{
    var quadResult = App.ddn.DetectQuad("Your file path.");
    var normalizeResult = App.ddn.Normalize("Your file path.", quadResult[0].Location);
} 
catch(DDNException ex)
{
    Console.WriteLine("Exception caught: ", ex.Message);
}
```

## Runtime Settings Methods Details

### InitRuntimeSettingsFromFile

Initialize runtime settings from a given JSON file.

```csharp
void IntiRuntimeSettingsFromFile(string filePath);
```

**Parameters**

`[in] filePath`: The path of the settings file.  

**Code Snippet**

```csharp
try 
{
    App.ddn.IntiRuntimeSettingsFromFile("Your file path");
}
catch(DDNException ex)
{
    Console.WriteLine("Exception caught: ", ex.Message);
}
```

### InitRuntimeSettings

Initialize runtime settings from a given JSON string.

```csharp
void InitRuntimeSettings(string content);
```

**Parameters**

`[in] content`: A JSON string that represents the content of the settings.  

**Code Snippet**

```csharp
try 
{
    App.ddn.InitRuntimeSettings("Your template JSON string");
}
catch(DDNException ex)
{
    Console.WriteLine("Exception caught: ", ex.Message);
}
```

### OutputRuntimeSettingsToFile

Output runtime settings to a settings file (JSON file).

```csharp
void OutputRuntimeSettingsToFile(string filePath, string settingsName);
```

**Parameters**

`[in] filePath`: The output file path which stores runtime settings.  
`[in] settingsName`: A unique name for declaring runtime settings.

**Code Snippet**

```csharp
try 
{
    App.ddn.OutputRuntimeSettingsToFile("Your file path", "");
}
catch(DDNException ex)
{
    Console.WriteLine("Exception caught: ", ex.Message);
}
```

### OutputRuntimeSettings

Output runtime settings to a JSON string.

```csharp
string OutputRuntimeSettings(string settingsName);
```

**Parameters** 

`[in] settingsName`: A unique name for declaring runtime settings.  

**Return Value**

The output JSON string which stores the contents of runtime settings.

**Code Snippet**

```csharp
try 
{
    String OutputTemplate = App.ddn.OutputRuntimeSettings("Your template name.");
}
catch(DDNException ex)
{
    Console.WriteLine("Exception caught: ", ex.Message);
}
```

## General Methods Details

### SaveToFile

Save a `NormalizedImageResult` to the targeting file path.

```csharp
void SaveToFile(NormalizedImageResult result, string filePath);
```

**Parameters** 

`[in] result`: A `NormalizedImageResult` object, which is the output of `Normalize` methods.  
`[in] filePath`: The path of the output image with the extension specifying the image format. It supports BMP, PNG, JPEG and PDF file types. If the target file exists, the image will be appended to the last page of the PDF file while the BMP, PNG and JPEG file will be replaced.

**Code Snippet**

```csharp
try 
{
    var quadResult = App.ddn.DetectQuad("Path of original image.");
    var normalizeResult = App.ddn.Normalize("Path of original image.", quadResult[0].Location);
    App.ddn.SaveToFile(normalizeResult, "Path that you want to save the normalized image.");
}
catch(DDNException ex)
{
    Console.WriteLine("Exception caught: ", ex.Message);
}
```

### getVersion

Get version information of SDK.

```csharp
string GetVersion();
```

**Return Value**

The version information string.
