---
layout: default-layout
title: Dynamsoft Document Normalizer JavaScript API - Initialization APIs
description: This page shows the initialization APIs of Dynamsoft Document Normalizer JavaScript SDK.
keywords: DocumentNormalizer, api reference, javascript, js, initialization
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
breadcrumbText: Initialization APIs
---

# Initialization Control

The following methods and properties help with the initialization of the library.

## API Index

### License Control

| API Name | Description |
|---|---|
| [license](#license) | Uses an alphanumeric string to specify the license. |

### Create and Destroy Instances

| API Name | Description |
|---|---|
| [createInstance()](#createinstance) | Creates a `DocumentNormalizer` instance. |
| [dispose()](#dispose) | Dispose the DocumentNormalizer instance. |
| [disposed](#disposed) | Returns whether the instance has been disposed. |

### Set Up the Environment

| API Name | Description |
|---|---|
| [engineResourcePath](#engineresourcepath) | Specifies the path from where the engine and models, etc. can be loaded. |
| [loadWasm()](#loadwasm) | Loads the engine. |
| [isWasmLoaded()](#iswasmloaded) | Returns whether the engine has been loaded. |
| [getVersion()](#getversion) | Returns the version of the library. |


## license

<!--Use an alphanumeric string to specify the license. Note that the license must be specified before the methods `createInstance()` and `loadWasm()` .-->

An online license or an offline license can be set here. Most license formats are supported. Dynamsoft usually provides an online license. 

`license` needs to be set before `createInstance()` or `loadWasm()`.

```typescript
static license: string
```

> Note:
>
> **Handshake Code and Organization ID**
>
> When you are using the online licenses, the license items can't be used directly. You need to use either a "Handshake Code" or an "Organization ID" instead.
> 
> The "Handshake Code" refers to an array of license items. When an "Handshake Code" is set, these license items will be consumed in a preset order.
>
> When an  "Organization ID" is set, the default "Handshake Code" of the "Organization ID" will be used.
>
> Generally, the first "Handshake Code" ever created for an organization is the default one. However, you can always configure another "Handshake Code" as the default.
>
> "Handshake Codes" can be configured in the [customer portal](https://www.dynamsoft.com/lts/#/handshakeCodes).


**Code Snippet**

```js
Dynamsoft.DDN.DocumentNormalizer.license =
  "YOUR-ORGANIZATION-ID or YOUR-HANDSHAKECODE or AN-OFFLINE-LICENSE or ANY-OTHER-TYPE-OF-SUPPORTED-LICENSE-STRING";
let normalizer = await Dynamsoft.DDN.DocumentNormalizer.createInstance();
```

For convenience, you can even set `license` in the `script` tag.

```html
<script src="/dist/ddn.js" data-license=
  "YOUR-ORGANIZATION-ID or YOUR-HANDSHAKECODE or AN-OFFLINE-LICENSE or ANY-OTHER-TYPE-OF-SUPPORTED-LICENSE-STRING"></script>
```

## createInstance

Creates a `DocumentNormalizer` instance.

```typescript
static createInstance(): Promise<DocumentNormalizer>
```

**Return value**

A promise resolving to the created `DocumentNormalizer` object.

**Code Snippet**

```js
let normalizer = await Dynamsoft.DDN.DocumentNormalizer.createInstance();
```

## dispose

Disposes the `DocumentNormalizer` instance. If your page needs to create a new instance from time to time, don't forget to dispose unused old instances.

```typescript
dispose(): void
```

**Return value**

A promise that resolves when the operation succeeds.

**Code Snippet**

```js
let normalizer = await Dynamsoft.DDN.DocumentNormalizer.createInstance();
// ... normalize ...
normalizer.dispose();
```

## disposed

Returns whether the instance has been disposed.

```typescript
disposed: boolean
```

## engineResourcePath

Specifies the path to find the engine(s). The property needs to be set before [loadWasm](#loadwasm). If not specified, the library will try to find the engine in the same location as the main JavaScript file (ddn.js).

```typescript
static engineResourcePath: string
```

**Code Snippet**

```js
Dynamsoft.DDN.DocumentNormalizer.engineResourcePath = "https://cdn.jsdelivr.net/npm/dynamsoft-document-normalizer@1.0.0/dist/";
await Dynamsoft.DDN.DocumentNormalizer.loadWasm();
```

## loadWasm

Downloads and compiles the engine to get it loaded/ready for a DocumentNormalizer instance to be created. You can call this API to silently set the operating environment of the library as soon as the page is loaded, avoiding unnecessary waiting time when using the library later.

If this API is not called beforehand, it will be called automatically when creating a DocumentNormalizer instance.

```typescript
static loadWasm(): Promise<void>
```

**Code Snippet**

```js
window.addEventListener('DOMContentLoaded', (event) => {
    Dynamsoft.DDN.DocumentNormalizer.loadWasm();
});
```

## isWasmLoaded

Returns whether the engine is loaded/ready.

```typescript
static isWasmLoaded(): boolean
```

## getVersion

Returns the version of the library including the detailed version numbers of the engine and the main JavaScript code.

The engine version only valid after [loadWasm](#loadwasm) has been called.

```typescript
readonly static getVersion(): string
```

**Code Snippet**

```js
console.log(Dynamsoft.DDN.DocumentNormalizer.getVersion());
```

