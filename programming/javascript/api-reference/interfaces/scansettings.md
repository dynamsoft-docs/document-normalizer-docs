---
layout: default-layout
title: Dynamsoft Document Normalizer JavaScript Interface - ScanSettings
description: This page shows the ScanSettings interface of Dynamsoft Document Normalizer for JavaScript.
keywords: ScanSettings, api reference, javascript, js
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
breadcrumbText: ScanSettings
---

# ScanSettings

Interface for scan behaviour customization.

## Attributes

| Attribute | Type |
|---------- | ---- |
| [`intervalTime`](#intervaltime-number) | *number* |

### intervalTime?: *number*

> Scan interval used to allow the library to release the CPU periodically. Measured in ms. Must be a positive value ( > 0 ).

```js
let scanSettings = await normalizer.getScanSettings();
scanSettings.intervalTime = 100; // 100ms
await normalizer.updateScanSettings(scanSettings);
```

