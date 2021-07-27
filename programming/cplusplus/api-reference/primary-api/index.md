---
layout: default-layout
title: Dynamsoft Content Normalizer - Primary Class for C++
keywords: primary api, c++ class, api reference, c++, cplusplus, dcn, documentation
description: Dynamsoft Content Normalizer - Primary Class for C++
---

# Class dynamsoft::dcn::ContentNormalizer - C++

## Initialization
  
  | Method | Description |
  |--------|-------------|
  | [`InitLicense`](#initlicense) | Sets the license key and activates the SDK. |

&nbsp;


### InitLicense
Sets the license key and activates the SDK.

```cpp
static int InitLicense (const char* pLicense)
```   

**Parameters**   
`[in] pLicense` The license key.


**Return value**   
The error code. Returns 0 if the function is completed successfully, otherwise call [`GetErrorString`](#geterrorstring) to get the detailed message. 


**Code Snippet**   
```cpp
ContentNormalizer::InitLicense("t0260NwAAAHV***************");
```


## Setting
  
  | Method | Description |
  |--------|-------------|
  | [`GetRuntimeSettings`](#getruntimesettings) | Gets current settings and saves them into a DCN_RuntimeSettings struct. |
  | [`UpdateRuntimeSettings`](#updateruntimesettings) | Updates runtime settings with given DCN_RuntimeSettings struct. |
  | [`ResetRuntimeSettings`](#resetruntimesettings) | Resets all runtime settings to default values. |
  | [`AppendSettingsFromString`](#appendsettingsfromstring) | Appends a new template string to the current runtime settings of SDK. |
  | [`AppendSettingsFromFile`](#appendsettingsfromfile) | Appends a new template file to the current runtime settings of SDK. |
  | [`OutputSettingsToFile`](#outputsettingstofile) | Outputs SDK runtime settings and save them into a setting file (JSON file). |
  | [`ClearAppendedSettings`](#clearappendedsettings) | Clears all appended parameter settings. |
  | [`SetModeArgument`](#setmodeargument) | Sets argument to give value for the specified mode parameter. |
  | [`GetModeArgument`](#getmodeargument) | Gets argument value for the specified mode parameter. |


&nbsp;

### GetRuntimeSettings
Gets current settings and saves them into a DCN_RuntimeSettings struct.

```cpp
int GetRuntimeSettings (DCN_RuntimeSettings* settings)
```   

**Parameters**      
`[in, out] settings` The struct of DCN_RuntimeSettings for storing runtime settings.


**Return value**   
The error code. Returns 0 if the function is completed successfully, otherwise call [`GetErrorString`](#geterrorstring) to get the detailed message. 


**Code Snippet**   
```cpp
ContentNormalizer::InitLicense("t0260NwAAAHV***************");
ContentNormalizer* normalizer = new ContentNormalizer();
DCN_RuntimeSettings settings;
int errorCode = normalizer->GetRuntimeSettings(&settings);
delete normalizer;
```

&nbsp;

### UpdateRuntimeSettings
Updates runtime settings with given DCN_RuntimeSettings struct.

```cpp
int UpdateRuntimeSettings (DCN_RuntimeSettings* settings, char errorMsgBuffer[] = NULL, const int errorMsgBufferLen = 0)
```   

**Parameters**    
`[in] settings` The struct of DCN_RuntimeSettings with customized settings.   
`[in, out] errorMsgBuffer` <sub>Optional</sub> The buffer is allocated by caller, and the recommending length is 256. The error message will be copied to the buffer.   
`[in] errorMsgBufferLen` <sub>Optional</sub> The length of allocated buffer.


**Return value**   
The error code. Returns 0 if the function is completed successfully, otherwise call [`GetErrorString`](#geterrorstring) to get the detailed message. 


**Code Snippet**   
```cpp
ContentNormalizer::InitLicense("t0260NwAAAHV***************");
ContentNormalizer* normalizer = new ContentNormalizer();
DCN_RuntimeSettings settings;
int errorCode = normalizer->GetRuntimeSettings(&settings);
settings.interiorAngleRange[0] = 70;
settings.interiorAngleRange[1] = 110;
char errorMessage[256];
errorCode = normalizer->UpdateRuntimeSettings(&settings, errorMessage, 256);
delete normalizer;
```

&nbsp;

### ResetRuntimeSettings
Resets all runtime settings to default values.

```cpp
int ResetRuntimeSettings ()
```   

**Return value**   
The error code. Returns 0 if the function is completed successfully, otherwise call [`GetErrorString`](#geterrorstring) to get the detailed message. 


**Code Snippet**   
```cpp
ContentNormalizer::InitLicense("t0260NwAAAHV***************");
ContentNormalizer* normalizer = new ContentNormalizer();
DCN_RuntimeSettings settings;
int errorCode = normalizer->GetRuntimeSettings(&settings);
settings.interiorAngleRange[0] = 70;
settings.interiorAngleRange[1] = 110;
char errorMessage[256];
errorCode = normalizer->UpdateRuntimeSettings(&settings, errorMessage, 256);
errorCode = normalizer->ResetRuntimeSettings();
delete normalizer;
```

&nbsp;


### AppendSettingsFromString
Appends a new template string to the current runtime settings of SDK.

```cpp
int AppendSettingsFromString (const char* content, char errorMsgBuffer[] = NULL, const int errorMsgBufferLen = 0)
```   

**Parameters**    
`[in] content` A JSON string that represents the content of the settings.   
`[in, out] errorMsgBuffer` <sub>Optional</sub> The buffer is allocated by caller, and the recommending length is 256. The error message will be copied to the buffer.   
`[in] errorMsgBufferLen` <sub>Optional</sub> The length of allocated buffer.


**Return value**   
The error code. Returns 0 if the function is completed successfully, otherwise call [`GetErrorString`](#geterrorstring) to get the detailed message. 


**Code Snippet**   
```cpp
ContentNormalizer::InitLicense("t0260NwAAAHV***************");
ContentNormalizer* normalizer = new ContentNormalizer();
char errorMessage[256];
normalizer->AppendSettingsFromString(normalizer, "{\"ContentNormalizerParameterArray\": [{\"Name\": \"CN_1\", \"Timeout\": 2000, \"MaxThreadCount\": 4, \"ScaleDownThreshold\": 2048, \"ExecutePhases\": [\"EP_ALL\"], \"NormalizationDefinitionName\": \"ND_1\", \"QuadrilateralDetectionModes\": [{\"Mode\":\"QDM_LINE_BASED_DETECTION\"}]}], \"NormalizationDefinitionArray\":[{\"Name\": \"ND_1\", \"ContentType\": \"CT_DOCUMENT\", \"ContentLocalization\":{\"SourceType\": \"CBLM_AUTO_DETECTION\"}, \"EnablePerspectiveCorrection\": 1, \"TargetContentPageSize\": [210, 297], \"EnableDeskewing\": 1}]}", errorMessage, 256);
delete normalizer;
```

&nbsp;


### AppendSettingsFromFile
Appends a new template file to the current runtime settings of SDK.

```cpp
int AppendSettingsFromFile (const char* filePath, char errorMsgBuffer[] = NULL, const int errorMsgBufferLen = 0)
```   

**Parameters**     
`[in] filePath` The settings file path.   
`[in, out] errorMsgBuffer` <sub>Optional</sub> The buffer is allocated by caller, and the recommending length is 256. The error message will be copied to the buffer.   
`[in] errorMsgBufferLen` <sub>Optional</sub> The length of allocated buffer.


**Return value**   
The error code. Returns 0 if the function is completed successfully, otherwise call [`GetErrorString`](#geterrorstring) to get the detailed message. 


**Code Snippet**   
```cpp
ContentNormalizer::InitLicense("t0260NwAAAHV***************");
ContentNormalizer* normalizer = new ContentNormalizer();
char errorMessage[256];
normalizer->AppendSettingsFromFile("your file path", errorMessage, 256);
delete normalizer;
```

&nbsp;


### OutputSettingsToFile
Outputs SDK runtime settings and save them into a setting file (JSON file). 

```cpp
int OutputSettingsToFile (const char* filePath, const char* templateName)
```   

**Parameters**   
`[in] filePath` The path of the output file used for storing current settings.   
`[in] templateName` A unique name for declaring current runtime settings.


**Return value**   
The error code. Returns 0 if the function is completed successfully, otherwise call [`GetErrorString`](#geterrorstring) to get the detailed message. 


**Code Snippet**   
```cpp
ContentNormalizer::InitLicense("t0260NwAAAHV***************");
ContentNormalizer* normalizer = new ContentNormalizer();
char errorMessage[256];
normalizer->AppendSettingsFromString(normalizer, "{\"ContentNormalizerParameterArray\": [{\"Name\": \"CN_1\", \"Timeout\": 2000, \"MaxThreadCount\": 4, \"ScaleDownThreshold\": 2048, \"ExecutePhases\": [\"EP_ALL\"], \"NormalizationDefinitionName\": \"ND_1\", \"QuadrilateralDetectionModes\": [{\"Mode\":\"QDM_LINE_BASED_DETECTION\"}]}], \"NormalizationDefinitionArray\":[{\"Name\": \"ND_1\", \"ContentType\": \"CT_DOCUMENT\", \"ContentLocalization\":{\"SourceType\": \"CBLM_AUTO_DETECTION\"}, \"EnablePerspectiveCorrection\": 1, \"TargetContentPageSize\": [210, 297], \"EnableDeskewing\": 1}]}", errorMessage, 256);
normalizer->OutputSettingsToFile("C:\\Program Files (x86)\\Dynamsoft\\{Version number}\\Templates\\CurrentRuntimeSettings.json", "currentRuntimeSettings");
delete normalizer;
```

&nbsp;

### ClearAppendedSettings
Clears all appended parameter settings.

```cpp
void ClearAppendedSettings ()
```   

**Code Snippet**   
```cpp
ContentNormalizer::InitLicense("t0260NwAAAHV***************");
ContentNormalizer* normalizer = new ContentNormalizer();
normalizer->ClearAppendedSettings();
delete normalizer;
```

&nbsp;

### SetModeArgument
Sets argument to give value for the specified mode parameter.

```cpp
int SetModeArgument (const char* modesName, const int index, const char* argumentName, const char* argumentValue, char errorMsgBuffer[] = NULL,  const int errorMsgBufferLen = 0)	
```   

**Parameters**   
`[in] modesName` The mode parameter name to get argument.   
`[in] index` The array index of mode parameter to indicate a specific mode.   
`[in] argumentName` The name of argument to set.   
`[in] argumentValue` The value of the argument to set.   
`[in, out] errorMsgBuffer` <sub>Optional</sub> The buffer is allocated by caller, and the recommending length is 256. The error message will be copied to the buffer.   
`[in] errorMsgBufferLen` <sub>Optional</sub> The length of allocated buffer.


**Return value**   
The error code. Returns 0 if the function is completed successfully, otherwise call [`GetErrorString`](#geterrorstring) to get the detailed message. 


**Code Snippet**   
```cpp
ContentNormalizer::InitLicense("t0260NwAAAHV***************");
ContentNormalizer* normalizer = new ContentNormalizer();
DCN_RuntimeSettings settings;
int errorCode = normalizer->GetRuntimeSettings(&settings);
settings.binarizationModes[0] = BM_THRESHOLD;
char errorMessage[256];
errorCode = normalizer->UpdateRuntimeSettings(&settings, errorMessage, 256);
errorCode = normalizer->SetModeArgument("BinarizationModes", 0, "BinarizationThreshold", "130", errorMessage, 256);
delete normalizer;
```


### GetModeArgument
Gets argument value for the specified mode parameter.

```cpp
int GetModeArgument (const char* modesName, const int index, const char* argumentName, char valueBuffer[], const int valueBufferLen, char errorMsgBuffer[] = NULL, const int errorMsgBufferLen = 0)
```   

**Parameters**     
`[in] modesName` The mode parameter name to get argument.   
`[in] index` The array index of mode parameter to indicate a specific mode.   
`[in] argumentName` The name of argument to get.   
`[in, out] valueBuffer` The buffer is allocated by caller, and the recommended length is 480. The argument value would be copied to the buffer.   
`[in] valueBufferLen` The length of allocated buffer.   
`[in, out] errorMsgBuffer` <sub>Optional</sub> The buffer is allocated by caller, and the recommending length is 256. The error message will be copied to the buffer.   
`[in] errorMsgBufferLen` <sub>Optional</sub> The length of allocated buffer.


**Return value**   
The error code. Returns 0 if the function is completed successfully, otherwise call [`GetErrorString`](#geterrorstring) to get the detailed message. 


**Code Snippet**   
```cpp
ContentNormalizer::InitLicense("t0260NwAAAHV***************");
ContentNormalizer* normalizer = new ContentNormalizer();
DCN_RuntimeSettings settings;
int errorCode = normalizer->GetRuntimeSettings(&settings);
settings.binarizationModes[0] = BM_THRESHOLD;
char errorMessage[256];
errorCode = normalizer->UpdateRuntimeSettings(&settings, errorMessage, 256);
errorCode = normalizer->SetModeArgument("BinarizationModes", 0, "BinarizationThreshold", "130", errorMessage, 256);
char argumentValue[480];
errorCode = normalizer->GetModeArgument("BinarizationModes", 0, "BinarizationThreshold", argumentValue, 480, errorMessage, 256);
delete normalizer;
```

&nbsp;


## Normalizing
  
  | Method | Description |
  |--------|-------------|
  | [`NormalizeByFile`](#normalizebyfile) | Normalizes content from a specified image file. |
  | [`NormalizeByBuffer`](#normalizebyfile) | Normalizes content from the memory buffer containing image pixels in a defined format. |

&nbsp;

### NormalizeByFile
Normalizes content from a specified image file.

```cpp
int NormalizeByFile (const char* filePath, const char* templateName)
```   

**Parameters**    
`[in] filePath` A string defining the source file path.   
`[in] templateName` The template name. A template name is the value of key ContentNormalizerParameter.Name defined in JSON formatted settings. If no template name is specified, current runtime settings will be used.


**Return value**   
The error code. Returns 0 if the function is completed successfully, otherwise call [`GetErrorString`](#geterrorstring) to get the detailed message. 


**Code Snippet**   
```cpp
ContentNormalizer::InitLicense("t0260NwAAAHV***************");
ContentNormalizer* normalizer = new ContentNormalizer();
int errorCode = normalizer->NormalizeByFile("C:\\Program Files (x86)\\Dynamsoft\\{Version number}\\Images\\SampleImage.png", "");
delete normalizer;
```

&nbsp;


### NormalizeByBuffer
Normalizes content from the memory buffer containing image pixels in a defined format.

```cpp
int NormalizeByBuffer (const ImageData* imageData, const char* templateName)
```   

**Parameters**    
`[in] imageData` A struct of ImageData that represents an image.   
`[in] templateName` The template name. A template name is the value of key ContentNormalizerParameter.Name defined in JSON formatted settings. If no template name is specified, current runtime settings will be used.


**Return value**   
The error code. Returns 0 if the function is completed successfully, otherwise call [`GetErrorString`](#geterrorstring) to get the detailed message. 


**Code Snippet**   
```cpp
ContentNormalizer::InitLicense("t0260NwAAAHV***************");
ContentNormalizer* normalizer = new ContentNormalizer();
ImageData* imageData;
//Generate imageData from somewhere else
int errorCode = normalizer->NormalizeByBuffer(imageData, "");
delete normalizer;
```

## Result
  
  | Method | Description |
  |--------|-------------|
  | [`GetResult`](#getresult) | Gets content normalized result. |
  | [`FreeResult`](#freeresult) | Free memory allocated for storing the result. |
  | [`OutputImageBufferToFile`](#outputimagebuffertofile) | Outputs image buffer into an image file. |
  | [`GetAdjustedImageBuffer`](#getadjustedimagebuffer) | Gets new image buffer after specified adjustments with given colour mode, contrast, and brightness. |
  | [`GetTransformedQuad`](#gettransformedquad) | Gets transformed quadrilateral with the given transformation matrix. |
  

&nbsp;

### GetResult
Gets content normalized result.

```cpp
int GetResult (DCN_Result** result)
```   

**Parameters**    
`[out] result` Normalized result returned by last calling function [`NormalizedByFile`](#normalizedbyfile)/[`NormalizedByBuffer`](#normalizedbybuffer). The result is allocated by SDK and should be freed by calling function [`FreeResult`](#freeresult).


**Return value**   
The error code. Returns 0 if the function is completed successfully, otherwise call [`GetErrorString`](#geterrorstring) to get the detailed message. 


**Code Snippet**   
```cpp
ContentNormalizer::InitLicense("t0260NwAAAHV***************");
ContentNormalizer* normalizer = new ContentNormalizer();
int errorCode = normalizer->NormalizeByFile("C:\\Program Files (x86)\\Dynamsoft\\{Version number}\\Images\\SampleImage.png", "");
DCN_Result* result = NULL;
normalizer->GetResult(normalizer, &result);
ContentNormalizer::FreeResult(&result);
delete normalizer;
```

&nbsp;

### FreeResult
Free memory allocated for storing the result.

```cpp
static void FreeResult (DCN_Result** result)
```   

**Parameters**   
`[in] result` Normalized result that needs to be freed.


**Code Snippet**   
```cpp
ContentNormalizer::InitLicense("t0260NwAAAHV***************");
ContentNormalizer* normalizer = new ContentNormalizer();
int errorCode = normalizer->NormalizeByFile("C:\\Program Files (x86)\\Dynamsoft\\{Version number}\\Images\\SampleImage.png", "");
DCN_Result* result = NULL;
normalizer->GetResult(normalizer, &result);
ContentNormalizer::FreeResult(&result);
delete normalizer;
```

&nbsp;


### OutputImageBufferToFile
Outputs image buffer into an image file.

```cpp
static int OutputImageBufferToFile (const char* filename, const ImageData* imageBuffer)
```   

**Parameters**   
`[in] filename` The path of the output image with the extension specified image format.   
`[in] imageBuffer` The input image buffer that needs to output.


**Return value**   
The error code. Returns 0 if the function is completed successfully, otherwise call [`GetErrorString`](#geterrorstring) to get the detailed message. 


**Code Snippet**   
```cpp
ContentNormalizer::InitLicense("t0260NwAAAHV***************");
ContentNormalizer* normalizer = new ContentNormalizer();
int errorCode = normalizer->NormalizeByFile("C:\\Program Files (x86)\\Dynamsoft\\{Version number}\\Images\\SampleImage.png", "");
DCN_Result* result = NULL;
normalizer->GetResult(normalizer, &result);
if (result != NULL)
{
  ImageData* resultImage = result->normalizedImage;
  if (resultImage != NULL)
  {
    ContentNormalizer::OutputImageBufferToFile("C:\\Program Files (x86)\\Dynamsoft\\{Version number}\\result\\resultImage.png", resultImage);
  }
}
ContentNormalizer::FreeResult(&result);
delete normalizer;
```

&nbsp;


### GetAdjustedImageBuffer
Gets new image buffer after specified adjustments with given colour mode, contrast, and brightness. 

```cpp
static int GetAdjustedImageBuffer (const ImageData* originalImageBuffer, ImageData* outputImageBuffer, ImageColourMode colourMode = ICM_BINARY, int contrast = 0, int brightness = 0)
```   

**Parameters**   
`[in] originalImageBuffer` The struct of ImageData contains the original image buffer before adjustments.   
`[out] outputImageBuffer` The struct of ImageData used for storing new image buffer after adjustments.   
`[in] colourMode` <sub>Optional</sub> The specified colour mode.   
`[in] contrast` <sub>Optional</sub> The specified contrast value.   
`[in] brightness` <sub>Optional</sub> The specified brightness value.


**Return value**   
The error code. Returns 0 if the function is completed successfully, otherwise call [`GetErrorString`](#geterrorstring) to get the detailed message. 


**Code Snippet**   
```cpp
ContentNormalizer::InitLicense("t0260NwAAAHV***************");
ContentNormalizer* normalizer = new ContentNormalizer();
int errorCode = normalizer->NormalizeByFile("C:\\Program Files (x86)\\Dynamsoft\\{Version number}\\Images\\SampleImage.png", "");
DCN_Result* result = NULL;
normalizer->GetResult(normalizer, &result);
if (result != NULL)
{
  ImageData* resultImage = result->normalizedImage;
  if (resultImage != NULL)
  {
    ImageData adjustedImage;
    ContentNormalizer::GetAdjustedImageBuffer(resultImage, &adjustedImage, ICM_GRAYSCALE, 50, 50);
    ContentNormalizer::OutputImageBufferToFile("C:\\Program Files (x86)\\Dynamsoft\\{Version number}\\result\\adjustedImage.png", &adjustedImage);
  }
}
ContentNormalizer::FreeResult(&result);
delete normalizer;
```

&nbsp;


### GetTransformedQuad
Gets transformed quadrilateral with the given transformation matrix.

```cpp
static int dynamsoft::dcn::ContentNormalizer::GetTransformedQuad (const Quadrilateral* originalQuad, float transformationMatrix[], Quadrilateral* transformedQuad)
```   

**Parameters**   
`[in] originalQuad` The original quadrilateral struct of Quadrilateral.   
`[in] transformationMatrix` The transformation matrix for transforming coordinates.   
`[out] transformedQuad` The struct of Quadrilateral used for storing transformed quadrilateral.


**Return value**   
The error code. Returns 0 if the function is completed successfully, otherwise call [`GetErrorString`](#geterrorstring) to get the detailed message. 


**Code Snippet**   
```cpp
ContentNormalizer::InitLicense("t0260NwAAAHV***************");
ContentNormalizer* normalizer = new ContentNormalizer();
int errorCode = normalizer->NormalizeByFile("C:\\Program Files (x86)\\Dynamsoft\\{Version number}\\Images\\SampleImage.png", "");
DCN_Result* result = NULL;
normalizer->GetResult(normalizer, &result);
if (result != NULL)
{
  if (candidateQuadrilateralCount > 0 && result->transformationMatrix != NULL)
  {
    Quadrilateral transformedQuad;
    ContentNormalizer::GetTransformedQuad(result->sourceImageCandidateQuadArray[0], result->transformationMatrix, &transformedQuad);
  }
}
ContentNormalizer::FreeResult(&result);
delete normalizer;
```

## General
  
  | Method | Description |
  |--------|-------------|
  | [`GetErrorString`](#geterrorstring) | Returns the corresponding error message of input error code. |
  | [`GetVersion`](#getversion) | Returns the version info string for the SDK. |
  

&nbsp;

### GetErrorString
Returns the corresponding error message of input error code.

```cpp
static const char* GetErrorString (const int errorCode)
```   

**Parameters**   
`[in] errorCode` The input error code.


**Return value**   
The corresponding error message. 


**Code Snippet**   
```cpp
int errorCode = ContentNormalizer::InitLicense("t0260NwAAAHV***************");
const char* errorString = ContentNormalizer::GetErrorString(errorCode);
```

&nbsp;


### GetVersion
Returns the version info string for the SDK.

```cpp
static const char* GetVersion ()
```   

**Return value**   
The version info string.


**Code Snippet**   
```cpp
const char* versionInfo = ContentNormalizer::GetVersion(errorCode);
```

