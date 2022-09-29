---
layout: default-layout
title: Dynamsoft Document Normalizer Enumerations - Error Code
description: This article shows Error Code of Dynamsoft Document Normalizer.
keywords: error code, enumeration
---

# Error Code

## For all programming languages

  | Erorr Code | Value | Description |
  |------------|-------|-------------|
  | `DM_OK`                                | 0 | Successful. |
  | `DMERR_UNKNOWN`                        | -10000 | Unknown error. |
  | `DMERR_NO_MEMORY`                      | -10001 | Not enough memory to perform the operation. |
  | `DMERR_NULL_POINTER`                   | -10002 | Null pointer. |
  | `DMERR_LICENSE_INVALID`                | -10003 | The license is invalid. |
  | `DMERR_LICENSE_EXPIRED`                | -10004 | The license is expired. |
  | `DMERR_FILE_NOT_FOUND`                 | -10005 | The file is not found. |
  | `DMERR_FILETYPE_NOT_SUPPORTED`         | -10006 | The file type is not supported. |
  | `DMERR_IMAGE_READ_FAILED`              | -10012 | Failed to read the image. |
  | `DMERR_TIMEOUT`                        | -10026 | Operation timeout. |
  | `DMERR_JSON_PARSE_FAILED`              | -10030 | Failed to parse JSON string. |
  | `DMERR_JSON_TYPE_INVALID`              | -10031 | The value type is invalid. |
  | `DMERR_JSON_KEY_INVALID`               | -10032 | The key is invalid. |
  | `DMERR_JSON_VALUE_INVALID`             | -10033 | The value is invalid or out of range. |
  | `DMERR_JSON_NAME_KEY_MISSING`          | -10034 | The mandatory key "Name" is missing. |
  | `DMERR_JSON_NAME_VALUE_DUPLICATED`     | -10035 | The value of the key "Name" is duplicated. |
  | `DMERR_TEMPLATE_NAME_INVALID`          | -10036 | The template name is invalid. |
  | `DMERR_PARAMETER_VALUE_INVALID`        | -10038 | The parameter value is invalid or out of range. |
  | `DDNERR_CONTENT_NOT_FOUND`             | -50001 | No content has been detected. |
  | `DMERR_QUADRILATERAL_INVALID`          | -10057 | The quadrilateral is invalid. |
  | `DMERR_FILE_SAVE_FAILED`               | -10058 | Failed to save the file. |
  | `DMERR_STAGE_TYPE_INVALID`             | -10059 | The stage type is invalid. |
  | `DMERR_IMAGE_ORIENTATION_INVALID`      | -10060 | The image orientation is invalid. |
  | `DMERR_NO_LICENSE`                     | -20000 | No license specified. |
  | `DMERR_HANDSHAKE_CODE_INVALID`         | -20001 | The handshake code is invalid. |
  | `DMERR_LICENSE_BUFFER_FAILED`          | -20002 | Failed to read or write license buffer. |
  | `DMERR_LICENSE_SYNC_FAILED`            | -20003 | Failed to synchronize license info with license server. |
  | `DMERR_DEVICE_NOT_MATCH`               | -20004 | Device does not match with license buffer. |
  | `DMERR_BIND_DEVICE_FAILED`             | -20005 | Failed to bind device. |
  | `DMERR_LICENSE_INTERFACE_CONFLICT`     | -20006 | Interface InitLicenseFromLTS can not be used together with other license initiation interfaces.|
  | `DMERR_LICENSE_CLIENT_DLL_MISSING`     | -20007 | The license client dll is missing. |
  | `DMERR_INSTANCE_COUNT_OVER_LIMIT`      | -20008 | The number of instances used has exceeded the limit. |
  | `DMERR_LICENSE_INIT_SEQUENCE_FAILED`   | -20009 | Interface InitLicenseFromLTS has to be called before creating any SDK objects. |
  | `DMERR_TRIAL_LICENSE`                  | -20010 | Using a trial license. |
  | `DMERR_FAILED_TO_REACH_DLS`            | -20200 | Failed to reach License Server. |
