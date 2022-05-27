---
layout: default-layout
title: CDetectedQuadResult Class
description: This page shows CDetectedQuadResult class definition of Dynamsoft Document Normalizer SDK C++ Edition.
keywords: GetLocation, GetConfidenceAsDocumentBoundary, CDetectedQuadResult, api reference
---

# CDetectedQuadResult Class

Stores the detected quad result.

```cpp
class dynamsoft::ddn::CDetectedQuadResult
```

| Method | Description |
|--------|-------------|
| [`GetLocation`](#getlocation) | Gets the location of the detected quad result.|
| [`GetConfidenceAsDocumentBoundary`](#getconfidenceasdocumentboundary) | Gets the confidence as document boundary of the detected quad result.|

## GetLocation

Gets the location of the detected quad result.

```cpp
const CQuadrilateral* GetLocation() 
```

**Return Value**

The location of the detected quad result.

## GetConfidenceAsDocumentBoundary

Gets the confidence as document boundary of the detected quad result.

```cpp
int GetConfidenceAsDocumentBoundary() 
```

**Return Value**

The confidence as document boundary of the detected quad result.
