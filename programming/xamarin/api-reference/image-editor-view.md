---
layout: default-layout
title: Class DCVImageEditorView - Dynamsoft Document Normalizer Xamarin.Forms edition
description: This is the page of class DCVImageEditorView of Dynamsoft Document Normalizer Xamarin.Forms SDK.
keywords:  Camera Enhancer, Xamarin.Forms API references, class DCVImageEditorView
needAutoGenerateSidebar: true
noTitleIndex: true
needGenerateH3Content: true
breadcrumbText: DCVImageEditorView
---

# Class DCVImageEditorView

A view class for users to add editable UI elements on a static image.

```csharp
class DDNXamarin.DCVImageEditorView : View
```

## Properties Summary

| Property | Description |
| -------- | ----------- |
| [`OriginalImage`](#originalimage) | Set the image to display on the view. |
| [`DetectedQuadResults`](#detectedquadresults) | Set the coordinates of detected quads. |

## Methods Summary

| Method | Description |
| -------- | ----------- |
| [`getSelectedQuadResult`](#getselectedquadresult) | Get the user selected quad. It records the latest user edited information. |

## Properties Details

### OriginalImage

Set the image to display on the view.

```csharp
ImageData OriginalImage
```

### DetectedQuadResults

Set the coordinates of detected quads.

```csharp
DetectedQuadResult[] DetectedQuadResults
```

## Methods Details

### getSelectedQuadResult

Get the user selected quad. It records the latest user edited information.

```csharp
Quadrilateral getSelectedQuadResult()
```

**Code Snippet**

The following code snippet shows how to use `DCVImageEditorView` to display image and enable users to edit quads for document normalization.

In the **.xaml** file, configure `DCVImageEditorView` and a button for triggering normalization.

```xml
<ContentPage.Content>
    <AbsoluteLayout>
        <dynamsoft:DCVImageEditorView AbsoluteLayout.LayoutBounds="0,0,1,1" AbsoluteLayout.LayoutFlags="All"
            x:Name="imageEditor">
        </dynamsoft:DCVImageEditorView>
        <Button
            x:Name="normalize"
            Clicked="onNormalizeClicked"
            Text="Normalize"
            AbsoluteLayout.LayoutBounds="0.5,0.5,120,50"
            AbsoluteLayout.LayoutFlags="PositionProportional">
        </Button>
    </AbsoluteLayout> 
</ContentPage.Content>
```

In the **.xaml.cs** file, add the following code. You can get `imageData` and `DetectedQuadResult[]` from [`DetectQuad`](document-normalizer.md#detectquadfile) methods or [`IDetectResultListener`](detect-result-listener.md)

```csharp
namespace DDNDemo
{
    public partial class QuadEditorPage : ContentPage
    {
        ImageData data;
        DetectedQuadResult[] results;
        public QuadEditorPage(ImageData imageData, DetectedQuadResult[] results)
        {
            InitializeComponent();
            data = imageData;
            this.results = results;
        }

        protected override void OnAppearing()
        {
            base.OnAppearing();
            if (data != null) {
                imageEditor.OriginalImage = data;
            }
            if (results != null) {
                imageEditor.DetectedQuadResults = results;
            }
        }

        void onNormalizeClicked(object sender, EventArgs e) {
            var quad = imageEditor.getSelectedQuadResult();
            var result = App.ddn.Normalize(data, quad);
            Navigation.PushAsync(new ResultPage(result.image));
        }
    }
}
```
