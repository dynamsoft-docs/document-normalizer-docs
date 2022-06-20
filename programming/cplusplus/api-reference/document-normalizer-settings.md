---
layout: default-layout
title: CDocumentNormalizer - Setting Methods
description: This page shows Setting Methods of class CDocumentNormalizer of Dynamsoft Document Normalizer SDK C++ Edition.
keywords: InitRuntimeSettingsFromFile, InitRuntimeSettingsFromString, OutputRuntimeSettingsToFile, OutputRuntimeSettingsToString, CDocumentNormalizer, api reference, c++
---

# Setting Methods

| Method               | Description |
|----------------------|-------------|
| [`InitRuntimeSettingsFromFile`](#initruntimesettingsfromfile)  | Initializes runtime settings with the settings in a given JSON file. |
| [`InitRuntimeSettingsFromString`](#initruntimesettingsfromstring) | Initializes runtime settings with the settings in a given JSON string. |
| [`OutputRuntimeSettingsToFile`](#outputruntimesettingstofile) | Output runtime settings to a settings file (JSON file). |
| [`OutputRuntimeSettingsToString`](#outputruntimesettingstostring) | Output runtime settings to a string. |

## InitRuntimeSettingsFromFile

Initializes runtime settings with the settings in a given JSON file.

```cpp
int dynamsoft::ddn::CDocumentNormalizer::InitRuntimeSettingsFromFile(const char* pFilePath, char errorMsgBuffer[] = NULL, const int errorMsgBufferLen = 0)
```

**Parameters**

`[in] pFilePath` The path of the settings file.

`[in, out] errorMsgBuffer` <sub>Optional</sub> The buffer is allocated by caller and the recommended length is 256. The error message will be copied to the buffer.

`[in] errorMsgBufferLen` <sub>Optional</sub> The length of the allocated buffer.

**Return Value**

Returns error code (returns 0 if the function operates successfully).

**Code Snippet**

```cpp
CDocumentNormalizer ddn;
char szErrorMsg[256];
ddn.InitRuntimeSettingsFromFile("YOUR-SOURCE-FILE-PATH", szErrorMsg, 256);
```

## InitRuntimeSettingsFromString

Initializes runtime settings with the settings in a given JSON string.

```cpp
int dynamsoft::ddn::CDocumentNormalizer::InitRuntimeSettingsFromString(const char* content, char errorMsgBuffer[] = NULL, const int errorMsgBufferLen = 0)
```

**Parameters**

`[in] content` A JSON string that represents the content of the settings.

`[in, out] errorMsgBuffer` <sub>Optional</sub> The buffer is allocated by caller and the recommended length is 256. The error message will be copied to the buffer.

`[in] errorMsgBufferLen` <sub>Optional</sub> The length of the allocated buffer.

**Return Value**

Returns error code (returns 0 if the function operates successfully).

**Code Snippet**

```cpp
CDocumentNormalizer ddn;
char szErrorMsg[256];
ddn.InitRuntimeSettingsFromString("YOUR-SETTINGS-STRING", szErrorMsg, 256);
```

## OutputRuntimeSettingsToFile

Output runtime settings to a settings file (JSON file).

```cpp
int dynamsoft::ddn::CDocumentNormalizer::OutputRuntimeSettingsToFile(const char* templateName, const char* filePath)
```

**Parameters**

`[in] templateName` A unique name for declaring the runtime settings to be output.

`[in] filePath` The path of the output file used for storing current settings.

**Return Value**

Returns error code (returns 0 if the function operates successfully).

*You can call [`DC_GetErrorString`](document-normalizer-general.md#dc_geterrorstring) to get detailed error message.*

**Code Snippet**

```cpp
CDocumentNormalizer ddn;
ddn.OutputRuntimeSettingsToFile("", "YOUR-TARGET-FILE-PATH");
```

## OutputRuntimeSettingsToString

Output runtime settings to a string.

```cpp
int dynamsoft::ddn::CDocumentNormalizer::OutputRuntimeSettingsToString(const char* templateName, char** content)
```

**Parameters**

`[in] templateName` A unique name for declaring the runtime settings to be output.

`[in, out] content` The output string which stores the contents of current settings.  

**Return Value**

Returns error code (returns 0 if the function operates successfully).

*You can call [`DC_GetErrorString`](document-normalizer-general.md#dc_geterrorstring) to get detailed error message.*

**Code Snippet**

```cpp
CDocumentNormalizer ddn;
char* content = NULL;
ddn.OutputRuntimeSettingsToString("", &content);
//...do something with the content
if (content != NULL)
    CDocumentNormalizer::FreeString(&content);
```
