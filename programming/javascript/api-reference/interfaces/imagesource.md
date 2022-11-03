---
layout: default-layout
title: Dynamsoft Document Normalizer JavaScript Interface - ImageSource
description: This page shows the ImageSource interface of Dynamsoft Document Normalizer for JavaScript.
keywords: ImageSource, javascript, interface
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
breadcrumbText: ImageSource
---

# ImageSource

Interface that defines an Image Source.

## Members

### getImage()

Returns an image from the Image Source.

```typescript
/**
 * @param index Specifies the index of the image. If undefined, the Image Source will determine which image to return.
 */ 
getImage(index?: number): Promise<DSImage> | DSImage;
```
