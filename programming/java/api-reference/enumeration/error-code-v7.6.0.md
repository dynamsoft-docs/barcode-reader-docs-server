---
layout: default-layout
title: Error Code - Dynamsoft Barcode Reader SDK Java Edition
description: This article shows Error Code of Dynamsoft Barcode Reader.
keywords: error code, enumeration, -10000, -10001, -10002, -10003, -10004, -10005, -10006, -10007, -10008, -10009, -10010, -10011, -10012, -10013, -10014, -10015, -10016, -10017, -10018, -10019, -10020, -10021, -10022, -10023, -10024, -10025, -10026, -10027, -10028, -10029, -10030, -10031, -10032, -10033, -10034, -10035, -10036, -10037, -10038, -10039, -10040, -10041, -10042, -10043, -10044, -10045, -10046, -10047, -10048, -10049, -10050, -10051, -10052, -10053, -10054, -10055, -10056, -10057, -10058, -10059, -10060, -10061, 10000, 10001, 10002, 10003, 10004, 10005, 10006, 10007, 10008, 10009, 10010, 10011, 10012, 10013, 10014, 10015, 10016, 10017, 10018, 10019, 10020, 10021, 10022, 10023, 10024, 10025, 10026, 10027, 10028, 10029, 10030, 10031, 10032, 10033, 10034, 10035, 10036, 10037, 10038, 10039, 10040, 10041, 10042, 10043, 10044, 10045, 10046, 10047, 10048, 10049, 10050, 10051, 10052, 10053, 10054, 10055, 10056, 10057, 10058, 10059, 10060, 10061
needAutoGenerateSidebar: false
permalink: /programming/java/api-reference/enumeration/error-code-v7.6.0.html
---

# Error Code

## Declarations

```java
class EnumErrorCode
```

## Members

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DBR_SUCCESS` | 0 | Successful. |
  | `DBR_SYSTEM_EXCEPTION` | 1 | System exception. |
  | `DBR_UNKNOWN` | -10000 | Unknown error. |
  | `DBR_NO_MEMORY` | -10001 | Not enough memory to perform the operation. |
  | `DBR_NULL_POINTER` | -10002 | Null pointer. |
  | `DBR_LICENSE_INVALID` | -10003 | The license is invalid. |
  | `DBR_LICENSE_EXPIRED` | -10004 | The license has expired. |
  | `DBR_FILE_NOT_FOUND` | -10005 | The file is not found. |
  | `DBR_FILETYPE_NOT_SUPPORTED` | -10006 | The file type is not supported. |
  | `DBR_BPP_NOT_SUPPORTED` | -10007 | The BPP (Bits Per Pixel) is not supported. |
  | `DBR_INDEX_INVALID` | -10008 | The index is invalid. |
  | `DBR_BARCODE_FORMAT_INVALID` | -10009 | The barcode format is invalid. |
  | `DBR_CUSTOM_REGION_INVALID` | -10010 | The input region value parameter is invalid. |
  | `DBR_MAX_BARCODE_NUMBER_INVALID` | -10011 | The maximum barcode number is invalid. |
  | `DBR_IMAGE_READ_FAILED` | -10012 | Failed to read the image. |
  | `DBR_TIFF_READ_FAILED` | -10013 | Failed to read the TIFF image. |
  | `DBR_QR_LICENSE_INVALID` | -10016 | The QR Code license is invalid. |
  | `DBR_1D_LICENSE_INVALID` | -10017 | The 1D Barcode license is invalid. |
  | `DBR_DIB_BUFFER_INVALID` | -10018 | The DIB (Device-Independent Bitmaps) buffer is invalid. |
  | `DBR_PDF417_LICENSE_INVALID` | -10019 | The PDF417 license is invalid. |
  | `DBR_DATAMATRIX_LICENSE_INVALID` | -10020 | The DATAMATRIX license is invalid. |
  | `DBR_PDF_READ_FAILED` | -10021 | Failed to read the PDF file. |
  | `DBR_PDF_DLL_MISSING` | -10022 | The PDF DLL is missing. |
  | `DBR_PAGE_NUMBER_INVALID` | -10023 | The page number is invalid. |
  | `DBR_CUSTOM_SIZE_INVALID` | -10024 | The custom size is invalid. |
  | `DBR_CUSTOM_MODULESIZE_INVALID` | -10025 | The custom module size is invalid. |
  | `DBR_RECOGNITION_TIMEOUT` | -10026 | Recognition timeout. |
  | `DBR_JSON_PARSE_FAILED` | -10030 | Failed to parse JSON string. |
  | `DBR_JSON_TYPE_INVALID` | -10031 | The value type is invalid. |
  | `DBR_JSON_KEY_INVALID` | -10032 | The key is invalid. |
  | `DBR_JSON_VALUE_INVALID` | -10033 | The value is invalid or out of range. |
  | `DBR_JSON_NAME_KEY_MISSING` | -10034 | The mandatory key "Name" is missing. |
  | `DBR_JSON_NAME_VALUE_DUPLICATED` | -10035 | The value of the key "Name" is duplicated. |
  | `DBR_TEMPLATE_NAME_INVALID` | -10036 | The template name is invalid. |
  | `DBR_JSON_NAME_REFERENCE_INVALID` | -10037 | The name reference is invalid. |
  | `DBR_PARAMETER_VALUE_INVALID` | -10038 | The parameter value is invalid or out of range. |
  | `DBR_DOMAIN_NOT_MATCHED` | -10039 | The domain of your current site does not match the domain bound in the current product key. |
  | `DBR_RESERVEDINFO_NOT_MATCHED` | -10040 | The reserved info does not match the reserved info bound in the current product key. |
  | `DBR_AZTEC_LICENSE_INVALID` | -10041 | The AZTEC license is invalid. |
  | `DBR_LICENSE_DLL_MISSING` | -10042 | The License DLL is missing. |
  | `DBR_LICENSEKEY_NOT_MATCHED` | -10043 | The license key does not match the license content. |
  | `DBR_REQUESTED_FAILED` | -10044 | Failed to request the license content. |
  | `DBR_LICENSE_INIT_FAILED` | -10045 | Failed to init the license. |
  | `DBR_PATCHCODE_LICENSE_INVALID` | -10046 | The Patchcode license is invalid. |
  | `DBR_POSTALCODE_LICENSE_INVALID` | -10047 | The Postal code license is invalid. |
  | `DBR_DPM_LICENSE_INVALID` | -10048 | The DPM license is invalid. |
  | `DBR_FRAME_DECODING_THREAD_EXISTS` | -10049 | The frame decoding thread already exists. |
  | `DBR_STOP_DECODING_THREAD_FAILED` | -10050 | Failed to stop the frame decoding thread. |
  | `DBR_SET_MODE_ARGUMENT_ERROR` | -10051 | Failed to set mode's argument. |
  | `DBR_LICENSE_CONTENT_INVALID` | -10052 | The license content is invalid. |
  | `DBR_LICENSE_KEY_INVALID` | -10053 | The license key is invalid. |
  | `DBR_LICENSE_DEVICE_RUNS_OUT` | -10054 | The device number in the license key runs out. |
  | `DBR_GET_MODE_ARGUMENT_ERROR` | -10055 | Failed to get mode's argument. |
  | `DBR_IRT_LICENSE_INVALID` | -10056 | The Intermediate Result Types license is invalid. |
  | `DBR_MAXICODE_LICENSE_INVALID` | -10057 | The Maxicode license is invalid. |
  | `DBR_GS1_DATABAR_LICENSE_INVALID` | -10058 | The GS1 Databar license is invalid. |
  | `DBR_GS1_COMPOSITE_LICENSE_INVALID` | -10059 | The GS1 Composite code license is invalid. |
  | `DBR_PANORAMA_LICENSE_INVALID` | -10060 | The panorama license is invalid. |
  | `DBR_DOTCODE_LICENSE_INVALID` | -10061 | The DotCode license is invalid. |
