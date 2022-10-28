---
layout: default-layout
title: Class DetectedQuadResult - Dynamsoft Document Normalizer Xamarin.Forms API Reference
description: This is the page of class DetectedQuadResult of Dynamsoft Document Normalizer Xamarin.Forms SDK.
keywords: DetectedQuadResult, class, api reference, Xamarin.Forms
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# DetectedQuadResult

Stores the detected quad result.

```csharp
namespace DDNXamarin
{
    public class DetectedQuadResult
    {
        // The location of the detected quadrilateral.
        public Quadrilateral Location { get; set; }
        // How much confidence do we define the quad as a document boundary.
        public int ConfidenceAsDocumentBoundary { get; set; }
    }
}
```

## Attributes

| Attribute | Type | Description |
|---------- | ---- | ----------- |
| [`Location`](#location) | *Quadrilateral* | The location of the detected quadrilateral. |
| [`ConfidenceAsDocumentBoundary`](#confidenceasdocumentboundary) | *int* | How much confidence do we define the quad as a document boundary. |

&nbsp;

### Location

The location of the detected quadrilateral.

```csharp
public Quadrilateral Location
```

### ConfidenceAsDocumentBoundary

How much confidence do we define the quad as a document boundary.

```csharp
public int ConfidenceAsDocumentBoundary
```
