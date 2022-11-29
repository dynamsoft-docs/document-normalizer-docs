---
layout: default-layout
title: Dynamsoft Document Normalizer JavaScript API - Settings APIs
description: This page shows the settings APIs of Dynamsoft Document Normalizer JavaScript SDK.
keywords: document normalizer, api reference, javascript, js, settings
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
breadcrumbText: Settings APIs
---

# Settings

## API Index

### Scan Settings

| API Name | Description |
|---|---|
| [getScanSettings()](#getscansettings) | Returns the current [`ScanSettings`](./interfaces/scansettings.md). |
| [updateScanSettings()](#updatescansettings) | Updates scan settings with the object passed in. |

### Runtime Settings

| API Name | Description |
|---|---|
| [getRuntimeSettings()](#getruntimesettings) | Gets runtime settings with a template represented by a JSON object. |
| [setRuntimeSettings()](#setruntimesettings) | Sets runtime settings with a JSON object or a built-in template or a template string. |
| [resetRuntimeSettings()](#resetruntimesettings) | Resets all runtime setting parameters to default values. |

## getScanSettings

Returns the current scan settings.

```typescript
getScanSettings(): Promise<ScanSettings>
```

**Return value**

A promise resolving to a [`ScanSettings`](./interfaces/scansettings.md) .

**Code Snippet**

```js
let scanSettings = await normalizer.getScanSettings();
scanSettings.intervalTime = 50;
await normalizer.updateScanSettings(scanSettings);
```

## updateScanSettings

Updates scan settings with the object passed in.

```typescript
updateScanSettings(settings: ScanSettings): Promise<void>
```

**Parameters**

`settings` : specifies the new scan settings using [`ScanSettings`](./interfaces/scansettings.md).

**Return value**

A promise that resolves when the operation succeeds.

**Code Snippet**

```js
let scanSettings = await normalizer.getScanSettings();
scanSettings.intervalTime = 50;
await normalizer.updateScanSettings(scanSettings);
```

## getRuntimeSettings

Gets current runtime settings with a template represented by [`a JSON object`](../../../parameters/parameter-organization-structure.md#example).

```typescript
getRuntimeSettings(): Promise<object>
```

**Return value**

A promise resolving to a JSON object that contains the settings for label recognizing.

**Code snippet**

```js
let settings = await normalizer.getRuntimeSettings();
```

## setRuntimeSettings

Sets runtime settings with a JSON object or a built-in template or a template string.

```typescript
setRuntimeSettings(settings: object | string): Promise<void>
```

**Parameters**

`settings` : a JSON object that contains the new runtime settings or a string which refers to a built-in template or a template string. As of version 1.0.10, the only built-in template is "lowcontrast", which, as the name suggests, is optimized for detecting document boundaries with colors similar to the surrounding environment.

**Return value**

A promise that resolves when the operation succeeds.

**Code snippet**

```js
let settings = await normalizer.getRuntimeSettings();
settings.ImageParameterArray[0].BinarizationModes[0].ThresholdCompensation = 3;
settings.ImageParameterArray[0].ScaleDownThreshold = 512;
await normalizer.setRuntimeSettings(settings);

//or use a built-in template "lowcontrast"
await normalizer.setRuntimeSettings("lowcontrast");
```

## resetRuntimeSettings

Resets all runtime setting parameters to default values.

```typescript
resetRuntimeSettings(): Promise<void>
```

**Return value**

A promise that resolves when the operation succeeds.

**Code snippet**

```js
await normalizer.resetRuntimeSettings();
```
