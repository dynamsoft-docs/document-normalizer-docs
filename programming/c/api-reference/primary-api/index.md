---
layout: default-layout
title: Dynamsoft Content Normalizer - Primary API for C
keywords: primary api, c functions, api reference, c, c language, dcn, documentation
description: Dynamsoft Content Normalizer - Primary API for C
---

# Primary API - C Functions

## Initialization
  
  | Method | Description |
  |--------|-------------|
  | [`DCN_CreateInstance`](#dcn_createinstance) | Creates an instance of Dynamsoft Content Normalizer. |
  | [`DCN_DestroyInstance`](#dcn_destroyinstance) | Destroy the instance of Dynamsoft Content Normalizer. |
  | [`DCN_InitLicense`](#dcn_initlicense) | Sets the license key and activates the SDK. |

&nbsp;

### DCN_CreateInstance
Creates an instance of Dynamsoft Content Normalizer.

```c
void* DCN_CreateInstance ()	
```   

**Return value**   
An instance of Dynamsoft Content Normalizer. If failed, returns a null pointer.


**Code Snippet**   
```c
void* normalizer = DCN_CreateInstance();
DCN_InitLicense("t0260NwAAAHV***************");
DCN_DestroyInstance(normalizer);
```

&nbsp;

### DCN_DestroyInstance
Destroy the instance of Dynamsoft Content Normalizer.

```c
void DCN_DestroyInstance (void* normalizer)
```   

**Parameters**   
`[in] normalizer` Handle of the Dynamsoft Content Normalizer instance.


**Code Snippet**   
```c
void* normalizer = DCN_CreateInstance();
DCN_InitLicense("t0260NwAAAHV***************");
DCN_DestroyInstance(normalizer);
```

&nbsp;

### DCN_InitLicense
Sets the license key and activates the SDK.

```c
int DCN_InitLicense (const char* pLicense)
```   

**Parameters**   
`[in] pLicense` The license key.


**Return value**   
The error code. Returns 0 if the function is completed successfully, otherwise call DCN_GetErrorString to get the detailed message. 


**Code Snippet**   
```c
void* normalizer = DCN_CreateInstance();
DCN_InitLicense("t0260NwAAAHV***************");
DCN_DestroyInstance(normalizer);
```


## Setting
  
  | Method | Description |
  |--------|-------------|
  | [`DCN_GetRuntimeSettings`](#dcn_getruntimesettings) | Gets current settings and saves them into a DCN_RuntimeSettings struct. |
  | [`DCN_UpdateRuntimeSettings`](#dcn_updateruntimesettings) | Updates runtime settings with given DCN_RuntimeSettings struct. |
  | [`DCN_ResetRuntimeSettings`](#dcn_resetruntimesettings) | Resets all runtime settings to default values. |
  | [`DCN_AppendSettingsFromString`](#dcn_appendsettingsfromstring) | Appends a new template string to the current runtime settings of SDK. |
  | [`DCN_AppendSettingsFromFile`](#dcn_appendsettingsfromfile) | Appends a new template file to the current runtime settings of SDK. |
  | [`DCN_OutputSettingsToFile`](#dcn_outputsettingstofile) | Outputs SDK runtime settings and save them into a setting file (JSON file). |
  | [`DCN_ClearAppendedSettings`](#dcn_clearappendedsettings) | Clears all appended parameter settings. |
  | [`DCN_GetModeArgument`](#dcn_getmodeargument) | Gets argument value for the specified mode parameter. |
  | [`DCN_SetModeArgument`](#dcn_setmodeargument) | Sets argument to give value for the specified mode parameter. |

&nbsp;

### DCN_GetRuntimeSettings
Gets current settings and saves them into a DCN_RuntimeSettings struct.

```c
int DCN_GetRuntimeSettings (void* normalizer, DCN_RuntimeSettings* settings)
```   

**Parameters**   
`[in] normalizer` Handle of the content normalizer instance.   
`[in, out] settings` The struct of DCN_RuntimeSettings for storing runtime settings.


**Return value**   
The error code. Returns 0 if the function is completed successfully, otherwise call DCN_GetErrorString to get the detailed message. 


**Code Snippet**   
```c

```

&nbsp;

### DCN_UpdateRuntimeSettings
Updates runtime settings with given DCN_RuntimeSettings struct.

```c
int DCN_UpdateRuntimeSettings (void* normalizer, DCN_RuntimeSettings* settings, char errorMsgBuffer[], const int errorMsgBufferLen)
```   

**Parameters**   
`[in] normalizer` Handle of the content normalizer instance.   
`[in] settings` The struct of DCN_RuntimeSettings with customized settings.   
`[in, out] errorMsgBuffer` The buffer is allocated by caller, and the recommending length is 256. The error message will be copied to the buffer.   
`[in] errorMsgBufferLen` The length of allocated buffer.


**Return value**   
The error code. Returns 0 if the function is completed successfully, otherwise call DCN_GetErrorString to get the detailed message. 


**Code Snippet**   
```c

```

&nbsp;

### DCN_ResetRuntimeSettings
Resets all runtime settings to default values.

```c
int DCN_ResetRuntimeSettings (void* normalizer)
```   

**Parameters**   
`[in] normalizer` Handle of the content normalizer instance.


**Return value**   
The error code. Returns 0 if the function is completed successfully, otherwise call DCN_GetErrorString to get the detailed message. 


**Code Snippet**   
```c

```

&nbsp;


### DCN_AppendSettingsFromString
Appends a new template string to the current runtime settings of SDK.

```c
int DCN_AppendSettingsFromString (void* normalizer, const char* content, char errorMsgBuffer[], const int errorMsgBufferLen)
```   

**Parameters**   
`[in] normalizer` Handle of the content normalizer instance.   
`[in] content` A JSON string that represents the content of the settings.   
`[in, out] errorMsgBuffer` The buffer is allocated by caller, and the recommending length is 256. The error message will be copied to the buffer.   
`[in] errorMsgBufferLen` The length of allocated buffer.


**Return value**   
The error code. Returns 0 if the function is completed successfully, otherwise call DCN_GetErrorString to get the detailed message. 


**Code Snippet**   
```c

```

&nbsp;


### DCN_AppendSettingsFromFile
Appends a new template file to the current runtime settings of SDK.

```c
int DCN_AppendSettingsFromFile (void* normalizer, const char* filePath, char errorMsgBuffer[], const int errorMsgBufferLen)
```   

**Parameters**   
`[in] normalizer` Handle of the content normalizer instance.   
`[in] filePath` The settings file path.   
`[in, out] errorMsgBuffer` The buffer is allocated by caller, and the recommending length is 256. The error message will be copied to the buffer.   
`[in] errorMsgBufferLen` The length of allocated buffer.


**Return value**   
The error code. Returns 0 if the function is completed successfully, otherwise call DCN_GetErrorString to get the detailed message. 


**Code Snippet**   
```c

```

&nbsp;


### DCN_OutputSettingsToFile
Outputs SDK runtime settings and save them into a setting file (JSON file). 

```c
int DCN_OutputSettingsToFile (void* normalizer, const char* filePath, const char* templateName)
```   

**Parameters**   
`[in] normalizer` Handle of the content normalizer instance.   
`[in] filePath` The path of the output file used for storing current settings.   
`[in] templateName` A unique name for declaring current runtime settings.


**Return value**   
The error code. Returns 0 if the function is completed successfully, otherwise call DCN_GetErrorString to get the detailed message. 


**Code Snippet**   
```c

```

&nbsp;

### DCN_ClearAppendedSettings
Clears all appended parameter settings.

```c
void DCN_ClearAppendedSettings (void* normalizer)
```   

**Parameters**   
[in] normalizer: Handle of the content normalizer instance.


**Code Snippet**   
```c

```

&nbsp;

### DCN_GetModeArgument
Gets argument value for the specified mode parameter.

```c
int DCN_GetModeArgument (void* normalizer, const char* modesName, const int index, const char* argumentName, char valueBuffer[], const int valueBufferLen, char errorMsgBuffer[], const int errorMsgBufferLen)
```   

**Parameters**   
`[in] normalizer` Handle of the content normalizer instance.   
`[in] modesName` The mode parameter name to get argument.   
`[in] index` The array index of mode parameter to indicate a specific mode.   
`[in] argumentName` The name of argument to get.   
`[in, out] valueBuffer` The buffer is allocated by caller, and the recommended length is 480. The argument value would be copied to the buffer.   
`[in] valueBufferLen` The length of allocated buffer.   
`[in, out] errorMsgBuffer` The buffer is allocated by caller, and the recommending length is 256. The error message will be copied to the buffer.   
`[in] errorMsgBufferLen` The length of allocated buffer.


**Return value**   
The error code. Returns 0 if the function is completed successfully, otherwise call DCN_GetErrorString to get the detailed message. 


**Code Snippet**   
```c

```

&nbsp;


### DCN_SetModeArgument
Sets argument to give value for the specified mode parameter.

```c
int DCN_SetModeArgument (void* normalizer, const char* modesName, const int index, const char* argumentName, const char* argumentValue, char errorMsgBuffer[],  const int errorMsgBufferLen)
```   

**Parameters**   
`[in] normalizer` Handle of the content normalizer instance.   
`[in] modesName` The mode parameter name to get argument.   
`[in] index` The array index of mode parameter to indicate a specific mode.   
`[in] argumentName` The name of argument to set.   
`[in] argumentValue` The value of the argument to set.   
`[in, out] errorMsgBuffer` The buffer is allocated by caller, and the recommending length is 256. The error message will be copied to the buffer.   
`[in] errorMsgBufferLen` The length of allocated buffer.


**Return value**   
The error code. Returns 0 if the function is completed successfully, otherwise call DCN_GetErrorString to get the detailed message. 


**Code Snippet**   
```c

```


## Normalizing
  
  | Method | Description |
  |--------|-------------|
  | [`DCN_NormalizeByFile`](#dcn_normalizebyfile) | Normalizes content from a specified image file. |
  | [`DCN_NormalizeByBuffer`](#dcn_normalizebyfile) | Normalizes content from the memory buffer containing image pixels in a defined format. |

&nbsp;

### DCN_NormalizeByFile
Normalizes content from a specified image file.

```c
int DCN_NormalizeByFile (void* normalizer, const char* filePath, const char* templateName)
```   

**Parameters**   
`[in] normalizer` Handle of the content normalizer instance.   
`[in] filePath` A string defining the source file path.   
`[in] templateName` The template name. A template name is the value of key ContentNormalizerParameter.Name defined in JSON formatted settings. If no template name is specified, current runtime settings will be used.


**Return value**   
The error code. Returns 0 if the function is completed successfully, otherwise call DCN_GetErrorString to get the detailed message. 


**Code Snippet**   
```c

```

&nbsp;


### DCN_NormalizeByBuffer
Normalizes content from the memory buffer containing image pixels in a defined format.

```c
int DCN_NormalizeByBuffer (void* normalizer, const ImageData* imageData, const char* templateName)
```   

**Parameters**   
`[in] normalizer` Handle of the content normalizer instance.   
`[in] imageData` A struct of ImageData that represents an image.   
`[in] templateName` The template name. A template name is the value of key ContentNormalizerParameter.Name defined in JSON formatted settings. If no template name is specified, current runtime settings will be used.


**Return value**   
The error code. Returns 0 if the function is completed successfully, otherwise call DCN_GetErrorString to get the detailed message. 


**Code Snippet**   
```c

```

## Result
  
  | Method | Description |
  |--------|-------------|
  | [`DCN_GetResult`](#dcn_getresult) | Gets content normalized result. |
  | [`DCN_FreeResult`](#dcn_freeresult) | Free memory allocated for storing the result. |
  | [`DCN_OutputImageBufferToFile`](#dcn_outputimagebuffertofile) | Outputs image buffer into an image file. |
  | [`DCN_GetAdjustedImageBuffer`](#dcn_getadjustedimagebuffer) | Gets new image buffer after specified adjustments with given colour mode, contrast, and brightness. |
  | [`DCN_GetTransformedQuad`](#dcn_gettransformedquad) | Gets transformed quadrilateral with the given transformation matrix. |
  

&nbsp;

### DCN_GetResult
Gets content normalized result.

```c
int DCN_GetResult (void* normalizer, DCN_Result** result)
```   

**Parameters**   
`[in] normalizer` Handle of the content normalizer instance.   
`[out] result` Normalized result returned by last calling function [`DCN_NormalizedByFile`](#dcn_normalizedbyfile)/[`DCN_NormalizedByBuffer`](#dcn_normalizedbybuffer). The result is allocated by SDK and should be freed by calling function [`DCN_FreeResult`](#dcn_freeresult).


**Return value**   
The error code. Returns 0 if the function is completed successfully, otherwise call DCN_GetErrorString to get the detailed message. 


**Code Snippet**   
```c

```

&nbsp;

### DCN_FreeResult
Free memory allocated for storing the result.

```c
void DCN_FreeResults (DCN_Result** results)
```   

**Parameters**   
`[in] result` Normalized result that needs to be freed.


**Code Snippet**   
```c

```

&nbsp;


### DCN_OutputImageBufferToFile
Outputs image buffer into an image file.

```c
int DCN_ OutputImageBufferToFile (const char* filename, const ImageData* imageBuffer)
```   

**Parameters**   
`[in] filename` The path of the output image with the extension specified image format.   
`[in] imageBuffer` The input image buffer that needs to output.


**Return value**   
The error code. Returns 0 if the function is completed successfully, otherwise call DCN_GetErrorString to get the detailed message. 


**Code Snippet**   
```c

```

&nbsp;


### DCN_GetAdjustedImageBuffer
Gets new image buffer after specified adjustments with given colour mode, contrast, and brightness. 

```c
int DCN_GetAdjustedImageBuffer (const ImageData* originalImageBuffer, ImageData* outputImageBuffer, ImageColourMode colourMode, int contrast, int brightness)
```   

**Parameters**   
`[in] originalImageBuffer` The struct of ImageData contains the original image buffer before adjustments.   
`[out] outputImageBuffer` The struct of ImageData used for storing new image buffer after adjustments.   
`[in] colourMode` The specified colour mode.   
`[in] contrast` The specified contrast value.   
`[in] brightness` The specified brightness value.


**Return value**   
The error code. Returns 0 if the function is completed successfully, otherwise call DCN_GetErrorString to get the detailed message. 


**Code Snippet**   
```c

```

&nbsp;


### DCN_GetTransformedQuad
Gets transformed quadrilateral with the given transformation matrix.

```c
int DCN_GetTransformedQuad (const Quadrilateral* originalQuad, float transformationMatrix[], Quadrilateral* transformedQuad)
```   

**Parameters**   
`[in] originalQuad` The original quadrilateral struct of Quadrilateral.   
`[in] transformationMatrix` The transformation matrix for transforming coordinates.   
`[out] transformedQuad` The struct of Quadrilateral used for storing transformed quadrilateral.


**Return value**   
The error code. Returns 0 if the function is completed successfully, otherwise call DCN_GetErrorString to get the detailed message. 


**Code Snippet**   
```c

```

## General
  
  | Method | Description |
  |--------|-------------|
  | [`DCN_GetErrorString`](#dcn_geterrorstring) | Returns the corresponding error message of input error code. |
  | [`DCN_GetVersion`](#dcn_getversion) | Returns the version info string for the SDK. |
  

&nbsp;

### DCN_GetErrorString
Returns the corresponding error message of input error code.

```c
const char* DCN_GetErrorString (const int errorCode)
```   

**Parameters**   
`[in] errorCode` The input error code.


**Return value**   
The corresponding error message. 


**Code Snippet**   
```c

```

&nbsp;


### DCN_GetVersion
Returns the version info string for the SDK.

```c
const char* DCN_GetVersion ()
```   

**Return value**   
The version info string.


**Code Snippet**   
```c

```
