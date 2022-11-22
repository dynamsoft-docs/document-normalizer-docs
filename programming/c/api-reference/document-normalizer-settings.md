---
layout: default-layout
title: Setting Methods - Dynamsoft Document Normalizer SDK C Edition
description: This page shows Setting Methods of Dynamsoft Document Normalizer SDK C Edition.
keywords: DDN_InitRuntimeSettingsFromFile, DDN_InitRuntimeSettingsFromString, DDN_OutputRuntimeSettingsToFile, DDN_OutputRuntimeSettingsToString, api reference, c
---

# Setting Methods

| Method               | Description |
|----------------------|-------------|
| [`DDN_InitRuntimeSettingsFromFile`](#ddn_initruntimesettingsfromfile)  | Initializes runtime settings with the settings in a given JSON file. |
| [`DDN_InitRuntimeSettingsFromString`](#ddn_initruntimesettingsfromstring) | Initializes runtime settings with the settings in a given JSON string. |
| [`DDN_OutputRuntimeSettingsToFile`](#ddn_outputruntimesettingstofile) | Output runtime settings to a settings file (JSON file). |
| [`DDN_OutputRuntimeSettingsToString`](#ddn_outputruntimesettingstostring) | Output runtime settings to a string. |

## DDN_InitRuntimeSettingsFromFile

Initializes runtime settings with the settings in a given JSON file.

```c
int DDN_InitRuntimeSettingsFromFile(void* normalizer, const char* filePath, char errorMsgBuffer[], const int errorMsgBufferLen)
```

**Parameters**

`[in] normalizer` Handle of the Dynamsoft Document Normalizer instance.

`[in] pFilePath` The path of the settings file.

`[in, out] errorMsgBuffer` The buffer is allocated by caller and the recommended length is 256. The error message will be copied to the buffer.

`[in] errorMsgBufferLen` The length of the allocated buffer.

**Return Value**

Returns error code (returns 0 if the function operates successfully).

**Code Snippet**

```c
char szErrorMsg[256];
void* ddn = DDN_CreateInstance();
DDN_InitRuntimeSettingsFromFile(ddn, "YOUR-SOURCE-FILE-PATH", szErrorMsg, 256);
//...do something else
DDN_DestroyInstance(ddn);
```

## DDN_InitRuntimeSettingsFromString

Initializes runtime settings with the settings in a given JSON string.

```c
int DDN_InitRuntimeSettingsFromString(void* normalizer, const char* content, char errorMsgBuffer[], const int errorMsgBufferLen)
```

**Parameters**

`[in] normalizer` Handle of the Dynamsoft Document Normalizer instance.

`[in] content` A JSON string that represents the content of the settings.

`[in, out] errorMsgBuffer` The buffer is allocated by caller and the recommended length is 256. The error message will be copied to the buffer.

`[in] errorMsgBufferLen` The length of the allocated buffer.

**Return Value**

Returns error code (returns 0 if the function operates successfully).

**Code Snippet**

```c
char szErrorMsg[256];
void* ddn = DDN_CreateInstance();
DDN_InitRuntimeSettingsFromString(ddn, "YOUR-SETTINGS-STRING", szErrorMsg, 256);
//...do something else
DDN_DestroyInstance(ddn);
```

## DDN_OutputRuntimeSettingsToFile

Output runtime settings to a settings file (JSON file).

```c
int DDN_OutputRuntimeSettingsToFile(void* normalizer, const char* templateName, const char* filePath)
```

**Parameters**

`[in] normalizer` Handle of the Dynamsoft Document Normalizer instance.

`[in] templateName` A unique name for declaring the runtime settings to be output.

`[in] filePath` The path of the output file used for storing current settings.

**Return Value**

Returns error code (returns 0 if the function operates successfully).

*You can call [`DC_GetErrorString`](document-normalizer-general.md#dc_geterrorstring) to get detailed error message.*

**Code Snippet**

```c
void* ddn = DDN_CreateInstance();
char* content = NULL;
DDN_OutputRuntimeSettingsToFile(ddn, "", "YOUR-TARGET-FILE-PATH");
//...do something else
DDN_DestroyInstance(ddn);
```

## DDN_OutputRuntimeSettingsToString

Output runtime settings to a string.

```c
int DDN_OutputRuntimeSettingsToString(void* normalizer, const char* templateName, char** content)
```

**Parameters**

`[in] normalizer` Handle of the Dynamsoft Document Normalizer instance.

`[in] templateName` A unique name for declaring the runtime settings to be output.

`[in, out] content` The output string which stores the contents of current settings.  

**Return Value**  
Returns error code (returns 0 if the function operates successfully).

*You can call [`DC_GetErrorString`](document-normalizer-general.md#dc_geterrorstring) to get detailed error message.*

**Code Snippet**

```c
void* ddn = DDN_CreateInstance();
char* content = NULL;
DDN_OutputRuntimeSettingsToString(ddn, "", &content);
//...do something with the content
if (content != NULL)
    DDN_FreeString(&content);
DDN_DestroyInstance(ddn);
```
