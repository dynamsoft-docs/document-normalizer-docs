---
layout: default-layout
title: ColourChannelUsageType
keywords: ColourChannelUsageType, parameters, reference, documentation
description: Dynamsoft Document Normalizer Parameter Reference - ColourChannelUsageType
---

# ColourChannelUsageType

`ColourChannelUsageType` specifies how to use the colour channel from the source image buffer.

## Setting Methods

### As Json Parameter

`ColourChannelUsageType` as a JSON parameter is a string value defined as below.

| Parent Json Object | Key Name | Key Value Type | Key Value Range | Key Default Value |
| ------------------ | -------- | -------------- | ----------- | ------------- |
| ImageParameter | ColourChannelUsageType | *string* | "CCUT_AUTO"<br>"CCUT_FULL_CHANNEL"<br>"CCUT_NV21_Y_CHANNEL_ONLY"<br>"CCUT_RGB_R_CHANNEL_ONLY"<br>"CCUT_RGB_G_CHANNEL_ONLY"<br>"CCUT_RGB_B_CHANNEL_ONLY" | "CCUT_AUTO" |

**Example**

```json
{
    "ColourChannelUsageType": "CCUT_NV21_Y_CHANNEL_ONLY",
}
```
