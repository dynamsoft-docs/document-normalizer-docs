---
layout: default-layout
title: Dynamsoft Document Normalizer iOS API Reference - DynamsoftDocumentNormalizer Runtime Settings Advanced Methods
description: This page shows advanced runtime settings methods of Dynamsoft Document Normalizer for iOS SDK.
keywords: initRuntimeSettingsFromFile, initRuntimeSettingsFromString, outputRuntimeSettingsToFile, outputRuntimeSettings, runtime settings advanced methods, DynamsoftDocumentNormalizer, api reference, ios
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

```objc
-(BOOL)initRuntimeSettingsFromFile:(NSString*)filePath error:(NSError**)error;
```

**Parameters**

[in] `filePath`: The path of the settings file.  
[in,out] `error`: Input a pointer to an error object. If an error occurs, this pointer is set to an actual error object containing the error information. You may specify nil for this parameter if you do not want the error information.

**Return Value**

The boolean value indicating whether the operation was successful.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
DynamsoftDocumentNormalizer* normalizer = [[DynamsoftDocumentNormalizer alloc] init];
NSError* error;
BOOL isSuccess = [normalizer initRuntimeSettingsFromFile:@"your template file path" error:&error];
```
2. 
```swift
let normalizer = DynamsoftDocumentNormalizer()
let isSuccess = try? normalizer.initRuntimeSettingsFromFile("your template file path")
```

## initRuntimeSettingsFromString

Initialize runtime settings from a given JSON string.

```objc
-(BOOL)initRuntimeSettingsFromString:(NSString*)content error:(NSError**)error;
```

**Parameters**

[in] `content`: A JSON string that represents the content of the settings.  
[in,out] `error`: Input a pointer to an error object. If an error occurs, this pointer is set to an actual error object containing the error information. You may specify nil for this parameter if you do not want the error information.

**Return Value**

The boolean value indicating whether the operation was successful.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
DynamsoftDocumentNormalizer* normalizer = [[DynamsoftDocumentNormalizer alloc] init];
NSError* error;
BOOL isSuccess = [normalizer initRuntimeSettingsFromString:@"your json template string" error:&error];
```
2. 
```swift
let normalizer = DynamsoftDocumentNormalizer()
let isSuccess = try? normalizer.initRuntimeSettingsFromString("your json template string")
```

## outputRuntimeSettingsToFile

Output runtime settings to a settings file (JSON file).

```objc
-(BOOL)outputRuntimeSettingsToFile:(NSString*)filePath, settingsName:(NSString*)settingsName error:(NSError**)error;
```

**Parameters**

[in] `filePath`: The output file path which stores runtime settings.  
[in] `settingsName`: A unique name for declaring runtime settings.
[in,out] `error`: Input a pointer to an error object. If an error occurs, this pointer is set to an actual error object containing the error information. You may specify nil for this parameter if you do not want the error information.

**Return Value**

The boolean value indicating whether the operation was successful.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
DynamsoftDocumentNormalizer* normalizer = [[DynamsoftDocumentNormalizer alloc] init];
NSError* error;
BOOL isSuccess = [normalizer outputRuntimeSettingsToFile:@"your template file path" settingsName:@"your template name" error:&error];
```
2. 
```swift
let normalizer = DynamsoftDocumentNormalizer()
let isSuccess = try? normalizer.outputRuntimeSettingsToFile("your template file path", settingsName:"your template name")
```

## outputRuntimeSettings

Output runtime settings to a JSON string.

```objc
-(NSString*)outputRuntimeSettings:(NSString*)settingsName error:(NSError**)error;
```

**Parameters** 

[in] `settingsName` A unique name for declaring runtime settings.  
[in,out] `error`: Input a pointer to an error object. If an error occurs, this pointer is set to an actual error object containing the error information. You may specify nil for this parameter if you do not want the error information.

**Return Value**

The output JSON string which stores the contents of runtime settings.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
DynamsoftDocumentNormalizer* normalizer = [[DynamsoftDocumentNormalizer alloc] init];
NSError* error;
NSString* settingsString = [normalizer outputRuntimeSettings:@"your template name" error:&error];
```
2. 
```swift
let normalizer = DynamsoftDocumentNormalizer()
let settingsString = try? normalizer.outputRuntimeSettings("your template name")
```
