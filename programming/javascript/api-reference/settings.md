---
layout: default-layout
title: Dynamsoft Label Recognizer JavaScript API - Settings APIs
description: This page shows the settings APIs of Dynamsoft Label Recognizer JavaScript SDK.
keywords: label recognizer, api reference, javascript, js, settings
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
breadcrumbText: Settings APIs
---

# Settings

## Scan Settings

| API Name | Description |
|---|---|
| [getScanSettings()](#getscansettings) | Returns the current [`ScanSettings`](./interfaces/scansettings.md). |
| [updateScanSettings()](#updatescansettings) | Updates scan settings with the object passed in. |

## Runtime Settings

| API Name | Description |
|---|---|
| [getRuntimeSettings()](#getruntimesettings) | Gets runtime settings with a template represented by a JSON object. |
| [setRuntimeSettings()](#setruntimesettings) | Sets runtime settings with a JSON object. |
| [resetRuntimeSettings()](#resetruntimesettings) | Resets all parameters to default values. |

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

Gets current runtime settings with a template represented by a JSON object.

```typescript
getRuntimeSettings(): Promise<object>
```

**Return value**

A promise resolving to a JSON object that contains the settings for label recognizing.

**Code snippet**

```js
let settings = await normalizer.getRuntimeSettings();
settings.maxThreadCount = 4;
await normalizer.updateRuntimeSettings(settings);
```

## setRuntimeSettings

Sets runtime settings with a given JSON object.

```typescript
setRuntimeSettings(settings: object): Promise<void>
```

**Parameters**

`settings` : a JSON object that contains the new runtime settings.

**Return value**

A promise that resolves when the operation succeeds.

**Code snippet**

```js
let settings = await normalizer.getRuntimeSettings();
settings.maxThreadCount = 4;
await recognizer.setRuntimeSettings(settings);
```

## resetRuntimeSettings

Resets all parameters to default values.

```typescript
resetRuntimeSettings(): Promise<void>
```

**Return value**

A promise that resolves when the operation succeeds.

**Code snippet**

```js
await normalizer.resetRuntimeSettings();
```
