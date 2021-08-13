---
title: Dynamsoft Content Normalizer Parameter Reference - ContentType
keywords: contenttype, parameters, reference, dcn, documentation
description: Dynamsoft Content Normalizer Parameter Reference - ContentType
needGenerateH3Content: true
---


# ContentType
Sets the target content type to be normalized.

## Setting Methods
### As Json Parameter

| Parent Json Object | Json Parameter Name | Value Type | 
| ------------------ | ------------------- | ---------- |
| NormalizationDefinition | ContentType | *string* |

**Value Range**  
    Any one of the [`ContentType`]({{ site.enumerations }}content-type.html) items.

**Default Value**  
    "CT_DOCUMENT"

**Example**  
```json
{
    "ColourMode": "CT_TABLE",
}
```

### As Struct Member

| Struct | Struct Member Name | Value Type | 
| ------ | ------------------ | ---------- |
| DCN_RuntimeSettings->normalizationSettings | contentType | [`ContentType`]({{ site.enumerations }}content-type.html) |

**Value Range**  
    Any one of the [`ContentType`]({{ site.enumerations }}content-type.html) items.

**Default Value**  
    `CT_DOCUMENT`

**Code Snippet**  
```cpp
// This is a c++ sample code.
ContentNormalizer::InitLicense("t0260NwAAAHV***************");
ContentNormalizer* normalizer = new ContentNormalizer();
DCN_RuntimeSettings settings;
int errorCode = normalizer->GetRuntimeSettings(&settings);
settings->normalizationSettings.contentType = CT_TABLE;
char errorMessage[256];
errorCode = normalizer->UpdateRuntimeSettings(&settings, errorMessage, 256);
delete normalizer;
```

