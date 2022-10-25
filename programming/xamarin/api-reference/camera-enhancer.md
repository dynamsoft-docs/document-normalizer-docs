---
layout: default-layout
title: Interface ICameraEnhancer - Dynamsoft Document Normalizer Xamarin.Forms edition
description: This is the page of interface ICameraEnhancer of Dynamsoft Document Normalizer Xamarin.Forms SDK.
keywords:  Camera Enhancer, Xamarin.Forms API references, Interface ICameraEnhancer
needAutoGenerateSidebar: true
noTitleIndex: true
needGenerateH3Content: true
breadcrumbText: Xamarin.Forms Interface ICameraEnhancer
---

# Interface ICameraEnhancer

Interface `ICameraEnhaancer` includes the camera control APIs. It supports document scanning from the video streaming.

```csharp
interface DDNXamarin.ICameraEnhancer
```

## ICameraEnhancer Methods Summary

| Method | Description |
| ------ | ----------- |
| [`Open`](#open) | Turn on the current selected camera. |
| [`Close`](#close) | Turn off the current selected camera. |
| [`TurnOnTorch`](#turnontorch) | Turn on the torch. |
| [`TurnOffTorch`](#turnofftorch) | Turn off the torch. |

## ICameraEnhancer Methods Details

### Open

Turn on the camera.

```csharp
void Open();
```

&nbsp;

### close

Turn off the camera.

```csharp
void Close();
```

&nbsp;

### TurnOnTorch

Turn on the torch (if the torch of the mobile device is available).

```csharp
void TurnOnTorch();
```

&nbsp;

### TurnOffTorch

Turn off the torch.

```csharp
void TurnOffTorch();
```
