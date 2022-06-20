---
layout: default-layout
title: ColourConversionModes
keywords: ColourConversionModes, parameters, reference, documentation
description: Dynamsoft Document Normalizer Parameter Reference - ColourConversionModes
---

# ColourConversionModes

This parameter helps control the process of colour conversion, i.e. converting a colour image to a grayscale image. If you input a colour image, the library will convert it to a grayscale image first for further processing. By default, the conversion will be based on the RGB channel with the default weights of each of the three channels. This parameter allows you to specify the referred colour channel (RGB or HSV) and the weight of each channel during the colour conversion. Assume your image has a very high contrast of one colour channel between the content area and background, you can use this parameter to put more weight on that specific colour channel to get a higher quality grayscale image.

It consists of one or more modes, each mode represents a way to implement the convertion.

## Candidate Mode List

- CICM_GENERAL
- CICM_HSV

### CICM_GENERAL

Converts a colour image to a grayscale image using the general RGB conversion algorithm. This mode has the following arguments for further customization.

- [BlueChannelWeight](#bluechannelweight)
- [GreenChannelWeight](#greenchannelweight)
- [RedChannelWeight](#redchannelweight)

### CICM_HSV

Converts a colour image to a grayscale image using one of the HSV channels. This mode has the following arguments for further customizing.

- [ReferChannel](#referchannel)

## Setting Methods

### As JSON Parameter

`ColourConversionModes` as a JSON parameter is a JSON Object array defined as below.

| Parent Json Object | Key Name | Key Value |
| ------------------ | ------------------- | ---------- |
| ImageParameter | ColourConversionModes | A JSON Object array while each Object is defined as below |

| Key Name | Key Value | Description |
| -------- | --------- | ----------- |
| Mode | Any one in Candidate Mode List as string | (Required) Specifies a mode for colour convertion.  |
| BlueChannelWeight | A number from value range of BlueChannelWeight | (Optional) Sets the Argument [BlueChannelWeight](#bluechannelweight). |
| GreenChannelWeight | A number from value range of GreenChannelWeight | (Optional) Sets the Argument [GreenChannelWeight](#greenchannelweight). |
| RedChannelWeight | A number from value range of RedChannelWeight | (Optional) Sets the Argument [RedChannelWeight](#redchannelweight). |
| ReferChannel | A string from value range of ReferChannel | (Optional) Sets the Argument [ReferChannel](#referchannel). |

**Default Value**

```json
{
    "ColourConversionModes":[
        {
            "Mode": "CICM_GENERAL",
            "BlueChannelWeight": -1,
            "GreenChannelWeight": -1,
            "RedChannelWeight": -1
        }
    ]
}
```

**JSON Parameter Example**

```json
{
    "ColourConversionModes": [
        {
            "Mode": "CICM_GENERAL", 
            "BlueChannelWeight": 1000,
            "GreenChannelWeight": 0,
            "RedChannelWeight": 0
        },
        {
            "Mode": "CICM_GENERAL", 
            "BlueChannelWeight": 0,
            "GreenChannelWeight": 500,
            "RedChannelWeight": 500
        }
    ]
}
```

## Candidate Argument List

- [BlueChannelWeight](#bluechannelweight)
- [GreenChannelWeight](#greenchannelweight)
- [RedChannelWeight](#redchannelweight)
- [ReferChannel](#referchannel)

### BlueChannelWeight

Sets the weight value of Blue Colour Channel used for converting a colour image to a grayscale image.

| Value Type | Value Range | Default Value | Valid For |
| ---------- | ----------- | ------------- | --------- |
| *int* | [-1, 1000] | -1 | CICM_GENERAL |

**Remarks**

- -1: The weight value will be set automatically by the SDK.
- -1 will be used if the sum of BlueChannelWeight, GreenChannelWeight and RedChannelWeight is not 1000.

### GreenChannelWeight

Sets the weight value of Green Colour Channel used for converting a colour image to a grayscale image.

| Value Type | Value Range | Default Value | Valid For |
| ---------- | ----------- | ------------- | --------- |
| *int* | [-1, 1000] | -1 | CICM_GENERAL |

**Remarks**

- -1: The weight value will be set automatically by the SDK.
- -1 will be used if the sum of BlueChannelWeight, GreenChannelWeight and RedChannelWeight is not 1000.

### RedChannelWeight

Sets the weight value of Red Colour Channel used for converting a colour image to a grayscale image.

| Value Type | Value Range | Default Value | Valid For |
| ---------- | ----------- | ------------- | --------- |
| *int* | [-1, 1000] | -1 | CICM_GENERAL |

**Remarks**

- -1: The weight value will be set automatically by the SDK.
- -1 will be used if the sum of BlueChannelWeight, GreenChannelWeight and RedChannelWeight is not 1000.

### ReferChannel

Sets reference channel used for converting a colour image to a grayscale image by HSV algorithm.

| Value Type | Value Range | Default Value | Valid For |
| ---------- | ----------- | ------------- | --------- |
| *string* | "H_CHANNEL"<br>"S_CHANNEL"<br>"V_CHANNEL" | "H_CHANNEL" | CICM_HSV |
