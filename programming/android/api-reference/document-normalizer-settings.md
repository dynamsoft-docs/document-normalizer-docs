---
layout: default-layout
title: Dynamsoft Document Normalizer Android API Reference - DocumentNormalizer Runtime Settings Advanced Methods
description: This page shows DocumentNormalizer advanced runtime settings methods of Dynamsoft Document Normalizer for Android SDK.
keywords: initRuntimeSettingsFromFile, initRuntimeSettingsFromString, outputRuntimeSettingsToFile, outputRuntimeSettings, runtime settings advanced methods, DocumentNormalizer, api reference, android
needAutoGenerateSidebar: true
noTitleIndex: true
---

# Runtime Settings Methods

  | Method               | Description |
  |----------------------|-------------|
  | [`initRuntimeSettingsFromFile`](#initruntimesettingsfromfile)  | Initialize runtime settings with the settings in a given JSON file. |
  | [`initRuntimeSettingsFromString`](#initruntimesettingsfromstring) | Initialize runtime settings with the settings in a given JSON string. |
  | [`outputRuntimeSettingsToFile`](#outputruntimesettingstofile) | Output runtime settings to a settings file (JSON file). |
  | [`outputRuntimeSettings`](#outputruntimesettings) | Output runtime settings to a string. |

  ---

## initRuntimeSettingsFromFile

Initialize runtime settings from a given JSON file.

```java
void initRuntimeSettingsFromFile(String filePath) throws DocumentNormalizerException
```

**Parameters**

`[in] filePath`: The path of the settings file.  

**Exceptions**

[`DocumentNormalizerException`](document-normalizer-exception.md)

**Code Snippet**

```java
DocumentNormalizer reader = new DocumentNormalizer();
reader.initRuntimeSettingsFromFile("your template file path");
```

## initRuntimeSettingsFromString

Initialize runtime settings from a given JSON string.

```java
void initRuntimeSettingsFromString(String content)throws DocumentNormalizerException
```

**Parameters**

`[in] content`: A JSON string that represents the content of the settings.  

**Exceptions**

[`DocumentNormalizerException`](document-normalizer-exception.md)

**Code Snippet**

```java
DocumentNormalizer reader = new DocumentNormalizer();
reader.initRuntimeSettingsFromString("{\"Version\":\"3.0\", \"ImageParameter\":{\"Name\":\"IP1\"}}");
```

## outputRuntimeSettingsToFile

Output runtime settings to a settings file (JSON file).

```java
void outputRuntimeSettingsToFile(String filePath, String settingsName) throws DocumentNormalizerException
```

**Parameters**

`[in] filePath`: The output file path which stores runtime settings.  
`[in] settingsName`: A unique name for declaring runtime settings.

**Exceptions**

[`DocumentNormalizerException`](document-normalizer-exception.md)

**Code Snippet**

```java
DocumentNormalizer reader = new DocumentNormalizer();
reader.outputRuntimeSettingsToFile("your saving file path", "");
```

## outputRuntimeSettings

Output runtime settings to a JSON string.

```java
String outputRuntimeSettings(String settingsName) throws DocumentNormalizerException
```

**Parameters** 

`[in] settingsName`: A unique name for declaring runtime settings.  

**Return Value**

The output JSON string which stores the contents of runtime settings.

**Code Snippet**

```java
DocumentNormalizer reader = new DocumentNormalizer();
String settingStr = reader.outputRuntimeSettings("");
```
