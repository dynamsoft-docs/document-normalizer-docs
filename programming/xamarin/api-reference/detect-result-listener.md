---
layout: default-layout
title: Interface IDetectResultListener - Dynamsoft Document Normalizer Xamarin.Forms API Reference
description: This the page of interface IDetectResultListener of Dynamsoft Document Normalizer Xamarin.Forms SDK.
keywords: IDetectResultListener, interface, Xamarin.Forms
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
---

# IDetectResultListener

`IDetectResultListener` is the interface to handle callbacks when the detection results are returned.

```csharp
interface DDNXamarin.IDetectResultListener
```

| Method | Description |
| ------ | ----------- |
| `DetectResultCallback` | The callback method to handle the detection results returned by the library. |

&nbsp;

## DetectResultCallback

The callback method to handle the detection results returned by the library.

```csharp
void DetectResultCallback(int id, ImageData imageData, DetectedQuadResult[] quadResults);
```

**Parameters**

`[in] id` The ID of the frame.  
`[in] imageData` The image data of frame.  
`[in] quadResults` Detected results of the frame.

**Code Snippet**

```csharp
public partial class App : Application, IDetectResultListener
{
    ...

    public void DetectResultCallback(int id, ImageData imageData, DetectedQuadResult[] quadResults)
    {
        // Add your code to execute on quad results are detected.
    }
}
```
