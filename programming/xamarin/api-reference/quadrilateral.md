---
layout: default-layout
title: Class Quadrilateral - Dynamsoft Document Normalizer Xamarin.Forms edition
description: This is the page of class Quadrilateral of Dynamsoft Document Normalizer Xamarin.Forms SDK.
keywords: Quadrilateral, Xamarin.Forms
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---


# Quadrilateral

Stores the quadrilateral.  

```csharp
class DDNXamarin.Quadrilateral
```

## Attributes
  
| Attribute | Type | Description |
|---------- | ---- | ----------- |
| [`points`](#points) | `Xamarin.Forms.Point[]` | Four vertexes in a clockwise direction of a quadrilateral. Index 0 represents the left-most vertex. |

&nbsp;

### Points

Four vertexes in a clockwise direction of a quadrilateral. Index 0 represents the left-most vertex.

```csharp
Xamarin.Forms.Point[] points
```

## Methods

| Method | Description |
|---------- | ----------- |
| [`getBoundingRect`](#points) | Get the bounding rectangle of the quadrilateral. |

### getBoundingRect

Get the bounding rectangle of the quadrilateral.

```csharp
public Rect getBoundingRect();
```

**Return Value**

The bounding rectangle of the quadrilateral.
