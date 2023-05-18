---
layout: default-layout
title: Error Code - Dynamsoft Barcode Reader SDK C/C++ Edition
description: This article enumerates the error codes of Dynamsoft Barcode Reader v8.9.3
keywords: error code, enumeration
needAutoGenerateSidebar: true
noTitleIndex: true
permalink: /programming/c-cplusplus/enumeration/error-code-v8.9.3.html
---

# Error Code
  
## Error code common to all programming languages

### Error code 0

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DBR_OK` | 0 | Successful. |

### Error code -10000

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DBRERR_UNKNOWN` | -10000 | Unknown error. |

### Error code -10001

  | Error Code | Value | Description |  
  |-------------------|-------------------|-------------|
  | `DBRERR_NO_MEMORY` | -10001 | Not enough memory to perform the operation. |
  
### Error code -10002
 
  | Error Code | Value | Description |  
  |-------------------|-------------------|-------------|
  | `DBRERR_NULL_POINTER` | -10002 | Null pointer. |

### Error code -10003

  | Error Code | Value | Description |  
  |-------------------|-------------------|-------------|
  | `DBRERR_LICENSE_INVALID` | -10003 | The license is invalid. |

### Error code -10004
  
  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DBRERR_LICENSE_EXPIRED` | -10004 | The license has expired. |

### Error code -10005

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DBRERR_FILE_NOT_FOUND` | -10005 | The file is not found. |

### Error code -10006

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DBRERR_FILETYPE_NOT_SUPPORTED` | -10006 | The file type is not supported. |

### Error code -10007

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DBRERR_BPP_NOT_SUPPORTED` | -10007 | The BPP (Bits Per Pixel) is not supported. |

### Error code -10008

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DBRERR_INDEX_INVALID` | -10008 | The index is invalid. |

### Error code -10009

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DBRERR_BARCODE_FORMAT_INVALID` | -10009 | The barcode format is invalid. |
  
### Error code -10010

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DBRERR_CUSTOM_REGION_INVALID` | -10010 | The input region value parameter is invalid. |
  
### Error code -10011

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DBRERR_MAX_BARCODE_NUMBER_INVALID` | -10011 | The maximum barcode number is invalid. |
  
### Error code -10012

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DBRERR_IMAGE_READ_FAILED` | -10012 | Failed to read the image. |
  
### Error code -10013

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DBRERR_TIFF_READ_FAILED` | -10013 | Failed to read the TIFF image. |
  
### Error code -10016

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DBRERR_QR_LICENSE_INVALID` |	-10016 | The QR Code license is invalid. | 
  
### Error code -10017

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DBRERR_1D_LICENSE_INVALID` | -10017 | The 1D Barcode license is invalid. |
  
### Error code -10018

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DBRERR_DIB_BUFFER_INVALID` | -10018 | The DIB (Device-Independent Bitmaps) buffer is invalid. |
  
### Error code -10019

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DBRERR_PDF417_LICENSE_INVALID` | -10019 | The PDF417 license is invalid. |
  
### Error code -10020

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DBRERR_DATAMATRIX_LICENSE_INVALID` | -10020 | The DATAMATRIX license is invalid. |
  
### Error code -10021

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DBRERR_PDF_READ_FAILED` | -10021 | Failed to read the PDF file. |
  
### Error code -10022

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DBRERR_PDF_DLL_MISSING` | -10022 | The PDF DLL is missing. |
  
### Error code -10023

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DBRERR_PAGE_NUMBER_INVALID` | -10023 | The page number is invalid. |
  
### Error code -10024

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DBRERR_CUSTOM_SIZE_INVALID` | -10024 | The custom size is invalid. |
  
### Error code -10025

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DBRERR_CUSTOM_MODULESIZE_INVALID` | -10025 | The custom module size is invalid. |
  
### Error code -10026

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DBRERR_RECOGNITION_TIMEOUT` | -10026 | Recognition timeout. |
  
### Error code -10030

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DBRERR_JSON_PARSE_FAILED` | -10030 | Failed to parse JSON string. |
  
### Error code -10031

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DBRERR_JSON_TYPE_INVALID` | -10031 | The value type is invalid. |
  
### Error code -10032

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DBRERR_JSON_KEY_INVALID` | -10032 | The key is invalid. |
  
### Error code -10033

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DBRERR_JSON_VALUE_INVALID` | -10033 | The value is invalid or out of range. |
  
### Error code -10034

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DBRERR_JSON_NAME_KEY_MISSING` | -10034 | The mandatory key "Name" is missing. |
  
### Error code -10035

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DBRERR_JSON_NAME_VALUE_DUPLICATED` | -10035 | The value of the key "Name" is duplicated. |
  
### Error code -10036

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DBRERR_TEMPLATE_NAME_INVALID` | -10036 | The template name is invalid. |
  
### Error code -10037

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DBRERR_JSON_NAME_REFERENCE_INVALID` | -10037 | The name reference is invalid. |
  
### Error code -10038

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DBRERR_PARAMETER_VALUE_INVALID` | -10038 | The parameter value is invalid or out of range. |
  
### Error code -10039

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DBRERR_DOMAIN_NOT_MATCHED` | -10039 | The domain of your current site does not match the domain bound in the current product key. |
  
### Error code -10040

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DBRERR_RESERVEDINFO_NOT_MATCHED` |	-10040 | The reserved info does not match the reserved info bound in the current product key. |
  
### Error code -10041

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DBRERR_AZTEC_LICENSE_INVALID` | -10041	 | The AZTEC license is invalid. |
  
### Error code -10042

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DBRERR_LICENSE_DLL_MISSING` | -10042 | The License DLL is missing. |
  
### Error code -10043

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DBRERR_LICENSEKEY_NOT_MATCHED` | -10043 | The license key does not match the license content. |
  
### Error code -10044

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DBRERR_REQUESTED_FAILED` | -10044 | Failed to request the license content. |
  
### Error code -10045

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DBRERR_LICENSE_INIT_FAILED` | -10045 | Failed to init the license. |
  
### Error code -10046

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DBRERR_PATCHCODE_LICENSE_INVALID` | -10046 | The Patchcode license is invalid. |
  
### Error code -10047

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DBRERR_POSTALCODE_LICENSE_INVALID` | -10047 | The Postal code license is invalid. |
  
### Error code -10048

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DBRERR_DPM_LICENSE_INVALID` | -10048 | The DPM license is invalid. |
  
### Error code -10049

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DBRERR_FRAME_DECODING_THREAD_EXISTS` | -10049 | The frame decoding thread already exists. |
  
### Error code -10050

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DBRERR_STOP_DECODING_THREAD_FAILED` | -10050 | Failed to stop the frame decoding thread. |
  
### Error code -10051

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DBRERR_SET_MODE_ARGUMENT_ERROR` | -10051 | Failed to set mode's argument. |
  
### Error code -10052

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DBRERR_LICENSE_CONTENT_INVALID` | -10052 | The license content is invalid. |
  
### Error code -10053

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DBRERR_LICENSE_KEY_INVALID` | -10053 | The license key is invalid. |
  
### Error code -10054

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DBRERR_LICENSE_DEVICE_RUNS_OUT` | -10054 | The license key has no remaining quota. |
  
### Error code -10055

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DBRERR_GET_MODE_ARGUMENT_ERROR` | -10055 | Failed to get mode's argument. |
  
### Error code -10056

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DBRERR_IRT_LICENSE_INVALID` | -10056 | The Intermediate Result Types license is invalid. |
  
### Error code -10057

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DBRERR_MAXICODE_LICENSE_INVALID` | -10057 | The Maxicode license is invalid. |
  
### Error code -10058

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DBRERR_GS1_DATABAR_LICENSE_INVALID` | -10058 | The GS1 Databar license is invalid. |
  
### Error code -10059

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DBRERR_GS1_COMPOSITE_LICENSE_INVALID` | -10059 | The GS1 Composite code license is invalid. |
  
### Error code -10060

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DBRERR_PANORAMA_LICENSE_INVALID` | -10060 | The panorama license is invalid. |
  
### Error code -10061

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DBRERR_DOTCODE_LICENSE_INVALID` | -10061 | The DotCode license is invalid. |

### Error code -20000

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DMERR_NO_LICENSE` | -20000 | No license specified. |

### Error code -20001

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DMERR_HANDSHAKE_CODE_INVALID` | -20001 | The handshake code is invalid. |
 
### Error code -20002

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
   | `DMERR_LICENSE_BUFFER_FAILED` | -20002 | Failed to read or write license buffer. |
  
### Error code -20003

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DMERR_LICENSE_SYNC_FAILED` | -20003 | Failed to synchronize license info with License Server. |
  
### Error code -20004

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DMERR_DEVICE_NOT_MATCH` | -20004 | Device does not match with license buffer. |
  
### Error code -20005

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DMERR_BIND_DEVICE_FAILED` | -20005 | Failed to bind device. |
  
### Error code -20006

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DMERR_LICENSE_INTERFACE_CONFLICT` | -20006 | Interface InitLicenseFromDLS can not be used together with other license initiation interfaces. |
  
### Error code -20007

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DMERR_LICENSE_CLIENT_DLL_MISSING` | -20007 | The license client dll is missing. |
  
### Error code -20008

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DMERR_INSTANCE_COUNT_OVER_LIMIT` | -20008 | The number of instances used has exceeded the limit. |
  
### Error code -20009

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DMERR_LICENSE_INIT_SEQUENCE_FAILED` | -20009 | Interface InitLicenseFromDLS has to be called before creating any SDK objects. |

### Error code -20010

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DMERR_TRIAL_LICENSE` | -20010 | Using a trial license. |

### Error code -20200

  | Error Code | Value | Description |
  |-------------------|-------------------|-------------|
  | `DMERR_FAILED_TO_REACH_DLS` | -20200 | Failed to reach License Server. |

### More error codes

Error codes between -20199 and -20100 are thrown by the License Server. See <a href="https://www.dynamsoft.com/license-server/docs/common/errorlist.html?ver=latest" target="_blank">DLS Error List</a> for details.
