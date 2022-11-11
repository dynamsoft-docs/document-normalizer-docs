---
layout: default-layout
title: Class DCVCameraView - Dynamsoft Document Normalizer Xamarin.Forms edition
description: This is the page of class DCVCameraView of Dynamsoft Document Normalizer Xamarin.Forms SDK.
keywords:  Camera Enhancer, Xamarin.Forms API references, class DCVCameraView
needAutoGenerateSidebar: true
noTitleIndex: true
needGenerateH3Content: true
breadcrumbText: DCVCameraView
---

# Class DCVCameraView

`DCVCameraView` is the class that enables users to display video streaming.

```csharp
class DCVCameraView : View
```

**Code Snippet**

You can use the following code to add a camera view on your page if you have initialize `ICameraEnhancer`.

```xml
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:dynamsoft = "clr-namespace:DDNXamarin;assembly=DDN-Xamarin"
             Title="DDN"
             x:Class="DDNDemo.MainPage">
    <AbsoluteLayout>
        <dynamsoft:DCVCameraView AbsoluteLayout.LayoutBounds="0,0,1,1" AbsoluteLayout.LayoutFlags="All">
        </dynamsoft:DCVCameraView>
    </AbsoluteLayout>
</ContentPage>
```
