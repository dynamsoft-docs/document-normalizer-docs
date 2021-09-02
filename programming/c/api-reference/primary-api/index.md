---
title: Dynamsoft Document Normalizer - Primary API for C
keywords: primary api, c functions, api reference, c, c language, ddn, documentation
description: Dynamsoft Document Normalizer - Primary API for C
---

# Primary API - C Functions

## Initialization
  
  | Method | Description |
  |--------|-------------|
  | [`DDN_CreateInstance`](#ddn_createinstance) | Creates an instance of Dynamsoft Document Normalizer. |
  | [`DDN_DestroyInstance`](#ddn_destroyinstance) | Destroy the instance of Dynamsoft Document Normalizer. |
  | [`DDN_InitLicense`](#ddn_initlicense) | Sets the license key and activates the SDK. |

&nbsp;

### DDN_CreateInstance
Creates an instance of Dynamsoft Document Normalizer.

```c
void* DDN_CreateInstance ()	
```   

**Return value**   
An instance of Dynamsoft Document Normalizer. If failed, returns a null pointer.


**Code Snippet**   
```c
DDN_InitLicense("t0260NwAAAHV***************");
void* normalizer = DDN_CreateInstance();
DDN_DestroyInstance(normalizer);
```

&nbsp;

### DDN_DestroyInstance
Destroy the instance of Dynamsoft Document Normalizer.

```c
void DDN_DestroyInstance (void* normalizer)
```   

**Parameters**   
`[in] normalizer` Handle of the Dynamsoft Document Normalizer instance.


**Code Snippet**   
```c
DDN_InitLicense("t0260NwAAAHV***************");
void* normalizer = DDN_CreateInstance();
DDN_DestroyInstance(normalizer);
```

&nbsp;

### DDN_InitLicense
Sets the license key and activates the SDK.

```c
int DDN_InitLicense (const char* pLicense)
```   

**Parameters**   
`[in] pLicense` The license key.


**Return value**   
The error code. Returns 0 if the function is completed successfully, otherwise call [`DDN_GetErrorString`](#ddn_geterrorstring) to get the detailed message. 


**Code Snippet**   
```c
DDN_InitLicense("t0260NwAAAHV***************");
void* normalizer = DDN_CreateInstance();
DDN_DestroyInstance(normalizer);
```


## Setting
  
  | Method | Description |
  |--------|-------------|
  | [`DDN_GetRuntimeSettings`](#ddn_getruntimesettings) | Gets current settings and saves them into a DDN_RuntimeSettings struct. |
  | [`DDN_UpdateRuntimeSettings`](#ddn_updateruntimesettings) | Updates runtime settings with given DDN_RuntimeSettings struct. |
  | [`DDN_ResetRuntimeSettings`](#ddn_resetruntimesettings) | Resets all runtime settings to default values. |
  | [`DDN_AppendSettingsFromString`](#ddn_appendsettingsfromstring) | Appends a new template string to the current runtime settings of SDK. |
  | [`DDN_AppendSettingsFromFile`](#ddn_appendsettingsfromfile) | Appends a new template file to the current runtime settings of SDK. |
  | [`DDN_OutputSettingsToFile`](#ddn_outputsettingstofile) | Outputs SDK runtime settings and save them into a setting file (JSON file). |
  | [`DDN_ClearAppendedSettings`](#ddn_clearappendedsettings) | Clears all appended parameter settings. |
  | [`DDN_SetModeArgument`](#ddn_setmodeargument) | Sets argument to give value for the specified mode parameter. |
  | [`DDN_GetModeArgument`](#ddn_getmodeargument) | Gets argument value for the specified mode parameter. |


&nbsp;

### DDN_GetRuntimeSettings
Gets current settings and saves them into a DDN_RuntimeSettings struct.

```c
int DDN_GetRuntimeSettings (void* normalizer, DDN_RuntimeSettings* settings)
```   

**Parameters**   
`[in] normalizer` Handle of the document normalizer instance.   
`[in, out] settings` The struct of DDN_RuntimeSettings for storing runtime settings.


**Return value**   
The error code. Returns 0 if the function is completed successfully, otherwise call [`DDN_GetErrorString`](#ddn_geterrorstring) to get the detailed message. 


**Code Snippet**   
```c
DDN_InitLicense("t0260NwAAAHV***************");
void* normalizer = DDN_CreateInstance();
DDN_RuntimeSettings settings;
int errorCode = DDN_GetRuntimeSettings(normalizer, &settings);
DDN_DestroyInstance(normalizer);
```

&nbsp;

### DDN_UpdateRuntimeSettings
Updates runtime settings with given DDN_RuntimeSettings struct.

```c
int DDN_UpdateRuntimeSettings (void* normalizer, DDN_RuntimeSettings* settings, char errorMsgBuffer[], const int errorMsgBufferLen)
```   

**Parameters**   
`[in] normalizer` Handle of the document normalizer instance.   
`[in] settings` The struct of DDN_RuntimeSettings with customized settings.   
`[in, out] errorMsgBuffer` The buffer is allocated by caller, and the recommending length is 256. The error message will be copied to the buffer.   
`[in] errorMsgBufferLen` The length of allocated buffer.


**Return value**   
The error code. Returns 0 if the function is completed successfully, otherwise call [`DDN_GetErrorString`](#ddn_geterrorstring) to get the detailed message. 


**Code Snippet**   
```c
DDN_InitLicense("t0260NwAAAHV***************");
void* normalizer = DDN_CreateInstance();
DDN_RuntimeSettings settings;
int errorCode = DDN_GetRuntimeSettings(normalizer, &settings);
settings.interiorAngleRange[0] = 70;
settings.interiorAngleRange[1] = 110;
char errorMessage[256];
errorCode = DDN_UpdateRuntimeSettings(normalizer, &settings, errorMessage, 256);
DDN_DestroyInstance(normalizer);
```

&nbsp;

### DDN_ResetRuntimeSettings
Resets all runtime settings to default values.

```c
int DDN_ResetRuntimeSettings (void* normalizer)
```   

**Parameters**   
`[in] normalizer` Handle of the document normalizer instance.


**Return value**   
The error code. Returns 0 if the function is completed successfully, otherwise call [`DDN_GetErrorString`](#ddn_geterrorstring) to get the detailed message. 


**Code Snippet**   
```c
DDN_InitLicense("t0260NwAAAHV***************");
void* normalizer = DDN_CreateInstance();
DDN_RuntimeSettings settings;
int errorCode = DDN_GetRuntimeSettings(normalizer, &settings);
settings.interiorAngleRange[0] = 70;
settings.interiorAngleRange[1] = 110;
char errorMessage[256];
DDN_UpdateRuntimeSettings(normalizer, &settings, errorMessage, 256);
errorCode = DDN_ResetRuntimeSettings(normalizer);
DDN_DestroyInstance(normalizer);
```

&nbsp;


### DDN_AppendSettingsFromString
Appends a new template string to the current runtime settings of SDK.

```c
int DDN_AppendSettingsFromString (void* normalizer, const char* content, char errorMsgBuffer[], const int errorMsgBufferLen)
```   

**Parameters**   
`[in] normalizer` Handle of the document normalizer instance.   
`[in] content` A JSON string that represents the content of the settings.   
`[in, out] errorMsgBuffer` The buffer is allocated by caller, and the recommending length is 256. The error message will be copied to the buffer.   
`[in] errorMsgBufferLen` The length of allocated buffer.


**Return value**   
The error code. Returns 0 if the function is completed successfully, otherwise call [`DDN_GetErrorString`](#ddn_geterrorstring) to get the detailed message. 


**Code Snippet**   
```c
DDN_InitLicense("t0260NwAAAHV***************");
void* normalizer = DDN_CreateInstance();
char errorMessage[256];
DDN_AppendSettingsFromString(normalizer, "{\"DocumentNormalizerParameterArray\": [{\"Name\": \"CN_1\", \"Timeout\": 2000, \"MaxThreadCount\": 4, \"ScaleDownThreshold\": 2048, \"ExecutePhases\": [\"EP_ALL\"], \"NormalizationDefinitionName\": \"ND_1\", \"QuadrilateralDetectionModes\": [{\"Mode\":\"QDM_LINE_BASED_DETECTION\"}]}], \"NormalizationDefinitionArray\":[{\"Name\": \"ND_1\", \"ContentType\": \"CT_DOCUMENT\", \"ContentLocalization\":{\"SourceType\": \"CBLM_AUTO_DETECTION\"}, \"EnablePerspectiveCorrection\": 1, \"TargetContentPageSize\": [210, 297], \"EnableDeskewing\": 1}]}", errorMessage, 256);
DDN_DestroyInstance(normalizer);
```

&nbsp;


### DDN_AppendSettingsFromFile
Appends a new template file to the current runtime settings of SDK.

```c
int DDN_AppendSettingsFromFile (void* normalizer, const char* filePath, char errorMsgBuffer[], const int errorMsgBufferLen)
```   

**Parameters**   
`[in] normalizer` Handle of the document normalizer instance.   
`[in] filePath` The settings file path.   
`[in, out] errorMsgBuffer` The buffer is allocated by caller, and the recommending length is 256. The error message will be copied to the buffer.   
`[in] errorMsgBufferLen` The length of allocated buffer.


**Return value**   
The error code. Returns 0 if the function is completed successfully, otherwise call [`DDN_GetErrorString`](#ddn_geterrorstring) to get the detailed message. 


**Code Snippet**   
```c
DDN_InitLicense("t0260NwAAAHV***************");
void* normalizer = DDN_CreateInstance();
char errorMessage[256];
DDN_AppendSettingsFromFile(normalizer, "your file path", errorMessage, 256);
DDN_DestroyInstance(normalizer);
```

&nbsp;


### DDN_OutputSettingsToFile
Outputs SDK runtime settings and save them into a setting file (JSON file). 

```c
int DDN_OutputSettingsToFile (void* normalizer, const char* filePath, const char* templateName)
```   

**Parameters**   
`[in] normalizer` Handle of the document normalizer instance.   
`[in] filePath` The path of the output file used for storing current settings.   
`[in] templateName` A unique name for declaring current runtime settings.


**Return value**   
The error code. Returns 0 if the function is completed successfully, otherwise call [`DDN_GetErrorString`](#ddn_geterrorstring) to get the detailed message. 


**Code Snippet**   
```c
DDN_InitLicense("t0260NwAAAHV***************");
void* normalizer = DDN_CreateInstance();
char errorMessage[256];
DDN_AppendSettingsFromString(normalizer, "{\"DocumentNormalizerParameterArray\": [{\"Name\": \"CN_1\", \"Timeout\": 2000, \"MaxThreadCount\": 4, \"ScaleDownThreshold\": 2048, \"ExecutePhases\": [\"EP_ALL\"], \"NormalizationDefinitionName\": \"ND_1\", \"QuadrilateralDetectionModes\": [{\"Mode\":\"QDM_LINE_BASED_DETECTION\"}]}], \"NormalizationDefinitionArray\":[{\"Name\": \"ND_1\", \"ContentType\": \"CT_DOCUMENT\", \"ContentLocalization\":{\"SourceType\": \"CBLM_AUTO_DETECTION\"}, \"EnablePerspectiveCorrection\": 1, \"TargetContentPageSize\": [210, 297], \"EnableDeskewing\": 1}]}", errorMessage, 256);
DDN_OutputSettingsToFile(normalizer, "C:\\Program Files (x86)\\Dynamsoft\\{Version number}\\Templates\\CurrentRuntimeSettings.json", "currentRuntimeSettings");
DDN_DestroyInstance(normalizer);
```

&nbsp;

### DDN_ClearAppendedSettings
Clears all appended parameter settings.

```c
void DDN_ClearAppendedSettings (void* normalizer)
```   

**Parameters**   
[in] normalizer: Handle of the document normalizer instance.


**Code Snippet**   
```c
DDN_InitLicense("t0260NwAAAHV***************");
void* normalizer = DDN_CreateInstance();
DDN_ClearAppendedSettings(normalizer);
DDN_DestroyInstance(normalizer);
```

&nbsp;

### DDN_SetModeArgument
Sets argument to give value for the specified mode parameter.

```c
int DDN_SetModeArgument (void* normalizer, const char* modesName, const int index, const char* argumentName, const char* argumentValue, char errorMsgBuffer[],  const int errorMsgBufferLen)
```   

**Parameters**   
`[in] normalizer` Handle of the document normalizer instance.   
`[in] modesName` The mode parameter name to get argument.   
`[in] index` The array index of mode parameter to indicate a specific mode.   
`[in] argumentName` The name of argument to set.   
`[in] argumentValue` The value of the argument to set.   
`[in, out] errorMsgBuffer` The buffer is allocated by caller, and the recommending length is 256. The error message will be copied to the buffer.   
`[in] errorMsgBufferLen` The length of allocated buffer.


**Return value**   
The error code. Returns 0 if the function is completed successfully, otherwise call [`DDN_GetErrorString`](#ddn_geterrorstring) to get the detailed message. 


**Code Snippet**   
```c
DDN_InitLicense("t0260NwAAAHV***************");
void* normalizer = DDN_CreateInstance();
DDN_RuntimeSettings settings;
int errorCode = DDN_GetRuntimeSettings(normalizer, &settings);
settings.binarizationModes[0] = BM_THRESHOLD;
char errorMessage[256];
errorCode = DDN_UpdateRuntimeSettings(normalizer, &settings, errorMessage, 256);
errorCode = DDN_SetModeArgument(normalizer, "BinarizationModes", 0, "BinarizationThreshold", "130", errorMessage, 256);
DDN_DestroyInstance(normalizer);
```


### DDN_GetModeArgument
Gets argument value for the specified mode parameter.

```c
int DDN_GetModeArgument (void* normalizer, const char* modesName, const int index, const char* argumentName, char valueBuffer[], const int valueBufferLen, char errorMsgBuffer[], const int errorMsgBufferLen)
```   

**Parameters**   
`[in] normalizer` Handle of the document normalizer instance.   
`[in] modesName` The mode parameter name to get argument.   
`[in] index` The array index of mode parameter to indicate a specific mode.   
`[in] argumentName` The name of argument to get.   
`[in, out] valueBuffer` The buffer is allocated by caller, and the recommended length is 480. The argument value would be copied to the buffer.   
`[in] valueBufferLen` The length of allocated buffer.   
`[in, out] errorMsgBuffer` The buffer is allocated by caller, and the recommending length is 256. The error message will be copied to the buffer.   
`[in] errorMsgBufferLen` The length of allocated buffer.


**Return value**   
The error code. Returns 0 if the function is completed successfully, otherwise call [`DDN_GetErrorString`](#ddn_geterrorstring) to get the detailed message. 


**Code Snippet**   
```c
DDN_InitLicense("t0260NwAAAHV***************");
void* normalizer = DDN_CreateInstance();
DDN_RuntimeSettings settings;
int errorCode = DDN_GetRuntimeSettings(normalizer, &settings);
settings.binarizationModes[0] = BM_THRESHOLD;
char errorMessage[256];
errorCode = DDN_UpdateRuntimeSettings(normalizer, &settings, errorMessage, 256);
errorCode = DDN_SetModeArgument(normalizer, "BinarizationModes", 0, "BinarizationThreshold", "130", errorMessage, 256);
char argumentValue[480];
errorCode = DDN_GetModeArgument(normalizer, "BinarizationModes", 0, "BinarizationThreshold", argumentValue, 480, errorMessage, 256);
DDN_DestroyInstance(normalizer);
```

&nbsp;


## Normalizing
  
  | Method | Description |
  |--------|-------------|
  | [`DDN_NormalizeByFile`](#ddn_normalizebyfile) | Normalizes content from a specified image file. |
  | [`DDN_NormalizeByBuffer`](#ddn_normalizebyfile) | Normalizes content from the memory buffer containing image pixels in a defined format. |

&nbsp;

### DDN_NormalizeByFile
Normalizes content from a specified image file.

```c
int DDN_NormalizeByFile (void* normalizer, const char* filePath, const char* templateName)
```   

**Parameters**   
`[in] normalizer` Handle of the document normalizer instance.   
`[in] filePath` A string defining the source file path.   
`[in] templateName` The template name. A template name is the value of key DocumentNormalizerParameter.Name defined in JSON formatted settings. If no template name is specified, current runtime settings will be used.


**Return value**   
The error code. Returns 0 if the function is completed successfully, otherwise call [`DDN_GetErrorString`](#ddn_geterrorstring) to get the detailed message. 


**Code Snippet**   
```c
DDN_InitLicense("t0260NwAAAHV***************");
void* normalizer = DDN_CreateInstance();
int errorCode = DDN_NormalizeByFile(normalizer, "C:\\Program Files (x86)\\Dynamsoft\\{Version number}\\Images\\SampleImage.png", "");
DDN_DestroyInstance(normalizer);
```

&nbsp;


### DDN_NormalizeByBuffer
Normalizes content from the memory buffer containing image pixels in a defined format.

```c
int DDN_NormalizeByBuffer (void* normalizer, const ImageData* imageData, const char* templateName)
```   

**Parameters**   
`[in] normalizer` Handle of the document normalizer instance.   
`[in] imageData` A struct of ImageData that represents an image.   
`[in] templateName` The template name. A template name is the value of key DocumentNormalizerParameter.Name defined in JSON formatted settings. If no template name is specified, current runtime settings will be used.


**Return value**   
The error code. Returns 0 if the function is completed successfully, otherwise call [`DDN_GetErrorString`](#ddn_geterrorstring) to get the detailed message. 


**Code Snippet**   
```c
DDN_InitLicense("t0260NwAAAHV***************");
void* normalizer = DDN_CreateInstance();
ImageData* imageData;
//Generate imageData from somewhere else
int errorCode = DDN_NormalizeByBuffer(normalizer, imageData, "");
DDN_DestroyInstance(normalizer);
```

## Result
  
  | Method | Description |
  |--------|-------------|
  | [`DDN_GetResult`](#ddn_getresult) | Gets content normalized result. |
  | [`DDN_FreeResult`](#ddn_freeresult) | Free memory allocated for storing the result. |
  | [`DDN_OutputImageBufferToFile`](#ddn_outputimagebuffertofile) | Outputs image buffer into an image file. |
  | [`DDN_GetAdjustedImageBuffer`](#ddn_getadjustedimagebuffer) | Gets new image buffer after specified adjustments with given colour mode, contrast, and brightness. |
  | [`DDN_GetTransformedQuad`](#ddn_gettransformedquad) | Gets transformed quadrilateral with the given transformation matrix. |
  

&nbsp;

### DDN_GetResult
Gets content normalized result.

```c
int DDN_GetResult (void* normalizer, DDN_Result** result)
```   

**Parameters**   
`[in] normalizer` Handle of the document normalizer instance.   
`[out] result` Normalized result returned by last calling function [`DDN_NormalizedByFile`](#ddn_normalizedbyfile)/[`DDN_NormalizedByBuffer`](#ddn_normalizedbybuffer). The result is allocated by SDK and should be freed by calling function [`DDN_FreeResult`](#ddn_freeresult).


**Return value**   
The error code. Returns 0 if the function is completed successfully, otherwise call [`DDN_GetErrorString`](#ddn_geterrorstring) to get the detailed message. 


**Code Snippet**   
```c
DDN_InitLicense("t0260NwAAAHV***************");
void* normalizer = DDN_CreateInstance();
int errorCode = DDN_NormalizeByFile(normalizer, "C:\\Program Files (x86)\\Dynamsoft\\{Version number}\\Images\\SampleImage.png", "");
DDN_Result* result = NULL;
DDN_GetResult(normalizer, &result);
DDN_FreeResult(&result);
DDN_DestroyInstance(normalizer);
```

&nbsp;

### DDN_FreeResult
Free memory allocated for storing the result.

```c
void DDN_FreeResults (DDN_Result** results)
```   

**Parameters**   
`[in] result` Normalized result that needs to be freed.


**Code Snippet**   
```c
DDN_InitLicense("t0260NwAAAHV***************");
void* normalizer = DDN_CreateInstance();
int errorCode = DDN_NormalizeByFile(normalizer, "C:\\Program Files (x86)\\Dynamsoft\\{Version number}\\Images\\SampleImage.png", "");
DDN_Result* result = NULL;
DDN_GetResult(normalizer, &result);
DDN_FreeResult(&result);
DDN_DestroyInstance(normalizer);
```

&nbsp;


### DDN_OutputImageBufferToFile
Outputs image buffer into an image file.

```c
int DDN_OutputImageBufferToFile (const char* filename, const ImageData* imageBuffer)
```   

**Parameters**   
`[in] filename` The path of the output image with the extension specified image format.   
`[in] imageBuffer` The input image buffer that needs to output.


**Return value**   
The error code. Returns 0 if the function is completed successfully, otherwise call [`DDN_GetErrorString`](#ddn_geterrorstring) to get the detailed message. 


**Code Snippet**   
```c
DDN_InitLicense("t0260NwAAAHV***************");
void* normalizer = DDN_CreateInstance();
int errorCode = DDN_NormalizeByFile(normalizer, "C:\\Program Files (x86)\\Dynamsoft\\{Version number}\\Images\\SampleImage.png", "");
DDN_Result* result = NULL;
DDN_GetResult(normalizer, &result);
if (result != NULL)
{
  ImageData* resultImage = result->normalizedImage;
  if (resultImage != NULL)
  {
    DDN_OutputImageBufferToFile("C:\\Program Files (x86)\\Dynamsoft\\{Version number}\\result\\resultImage.png", resultImage);
  }
}
DDN_FreeResult(&result);
DDN_DestroyInstance(normalizer);
```

&nbsp;


### DDN_GetAdjustedImageBuffer
Gets new image buffer after specified adjustments with given colour mode, contrast, and brightness. 

```c
int DDN_GetAdjustedImageBuffer (const ImageData* originalImageBuffer, ImageData* outputImageBuffer, ImageColourMode colourMode, int contrast, int brightness)
```   

**Parameters**   
`[in] originalImageBuffer` The struct of ImageData contains the original image buffer before adjustments.   
`[out] outputImageBuffer` The struct of ImageData used for storing new image buffer after adjustments.   
`[in] colourMode` The specified colour mode.   
`[in] contrast` The specified contrast value.   
`[in] brightness` The specified brightness value.


**Return value**   
The error code. Returns 0 if the function is completed successfully, otherwise call [`DDN_GetErrorString`](#ddn_geterrorstring) to get the detailed message. 


**Code Snippet**   
```c
DDN_InitLicense("t0260NwAAAHV***************");
void* normalizer = DDN_CreateInstance();
int errorCode = DDN_NormalizeByFile(normalizer, "C:\\Program Files (x86)\\Dynamsoft\\{Version number}\\Images\\SampleImage.png", "");
DDN_Result* result = NULL;
DDN_GetResult(normalizer, &result);
if (result != NULL)
{
  ImageData* resultImage = result->normalizedImage;
  if (resultImage != NULL)
  {
    ImageData adjustedImage;
    DDN_GetAdjustedImageBuffer(resultImage, &adjustedImage, ICM_GRAYSCALE, 50, 50);
    DDN_OutputImageBufferToFile("C:\\Program Files (x86)\\Dynamsoft\\{Version number}\\result\\adjustedImage.png", &adjustedImage);
  }
}
DDN_FreeResult(&result);
DDN_DestroyInstance(normalizer);
```

&nbsp;


### DDN_GetTransformedQuad
Gets transformed quadrilateral with the given transformation matrix.

```c
int DDN_GetTransformedQuad (const Quadrilateral* originalQuad, float transformationMatrix[], Quadrilateral* transformedQuad)
```   

**Parameters**   
`[in] originalQuad` The original quadrilateral struct of Quadrilateral.   
`[in] transformationMatrix` The transformation matrix for transforming coordinates.   
`[out] transformedQuad` The struct of Quadrilateral used for storing transformed quadrilateral.


**Return value**   
The error code. Returns 0 if the function is completed successfully, otherwise call [`DDN_GetErrorString`](#ddn_geterrorstring) to get the detailed message. 


**Code Snippet**   
```c
DDN_InitLicense("t0260NwAAAHV***************");
void* normalizer = DDN_CreateInstance();
int errorCode = DDN_NormalizeByFile(normalizer, "C:\\Program Files (x86)\\Dynamsoft\\{Version number}\\Images\\SampleImage.png", "");
DDN_Result* result = NULL;
DDN_GetResult(normalizer, &result);
if (result != NULL)
{
  if (candidateQuadrilateralCount > 0 && result->transformationMatrix != NULL)
  {
    Quadrilateral transformedQuad;
    DDN_GetTransformedQuad(result->sourceImageCandidateQuadArray[0], result->transformationMatrix, &transformedQuad);
  }
}
DDN_FreeResult(&result);
DDN_DestroyInstance(normalizer);
```

## General
  
  | Method | Description |
  |--------|-------------|
  | [`DDN_GetErrorString`](#ddn_geterrorstring) | Returns the corresponding error message of input error code. |
  | [`DDN_GetVersion`](#ddn_getversion) | Returns the version info string for the SDK. |
  

&nbsp;

### DDN_GetErrorString
Returns the corresponding error message of input error code.

```c
const char* DDN_GetErrorString (const int errorCode)
```   

**Parameters**   
`[in] errorCode` The input error code.


**Return value**   
The corresponding error message. 


**Code Snippet**   
```c
int errorCode = DDN_InitLicense("t0260NwAAAHV***************");
const char* errorString = DDN_GetErrorString(errorCode);
```

&nbsp;


### DDN_GetVersion
Returns the version info string for the SDK.

```c
const char* DDN_GetVersion ()
```   

**Return value**   
The version info string.


**Code Snippet**   
```c
const char* versionInfo = DDN_GetVersion(errorCode);
```
