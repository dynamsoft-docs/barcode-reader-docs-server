---
layout: default-layout
title: CBarcodeReader Decode Methods - Dynamsoft Barcode Reader SDK C++ Edition API Reference
description: This page shows CBarcodeReader Decode methods of Dynamsoft Barcode Reader SDK C++ Edition.
keywords: DecodeFile, DecodeFileInMemory, DecodeBuffer, DecodeBase64String, DecodeDIB, decode methods, CBarcodeReader, api reference, c++
needAutoGenerateSidebar: true
permalink: /programming/cplusplus/api-reference/cbarcodereader-methods/decode-v9.6.20.html
---


# Decode Methods

  | Method               | Description |
  |----------------------|-------------|
  | [`DecodeFile`](#decodefile) | Decode barcodes from a specified image file. |
  | [`DecodeFileInMemory`](#decodefileinmemory) | Decode barcodes from an image file in memory. |
  | [`DecodeBuffer`](#decodebuffer) | Decode barcodes from raw buffer. |
  | [`DecodeBase64String`](#decodebase64string) | Decode barcodes from a base64 encoded string. |
  | [`DecodeDIB`](#decodedib) | Decode barcode from a handle of device-independent bitmap (DIB). |
  | [`InitIntermediateResult`](#initintermediateresult) | Inits an intermediateResult struct with default values. |
  | [`DecodeIntermediateResults`](#decodeintermediateresults) | Decodes barcode from intermediate results. |

## DecodeFile

Decode barcodes from a specified image file.

```cpp
int dynamsoft::dbr::CBarcodeReader::DecodeFile (const char* pFileName, const char* pTemplateName = "")	
```   
   
**Parameters**  
`[in] pFileName`	A string defining the file name. It supports BMP, JPEG, PNG, TIFF and PDF files.  
`[in] pTemplateName`<sub>Optional</sub> The template name.

**Return Value**  
Returns error code (returns 0 if the function operates successfully).    
*You can call [`GetErrorString`](general.md#geterrorstring) to get detailed error message.*

**Code Snippet**  
```cpp
char errorBuf[512];
dynamsoft::dbr::CBarcodeReader::InitLicense("YOUR-LICENSE-KEY", errorBuf, 512);
CBarcodeReader* reader = new CBarcodeReader();
int errorCode = reader->DecodeFile("C:\\Program Files (x86)\\Dynamsoft\\{Version number}\\Images\\AllSupportedBarcodeTypes.tif", "");
delete reader;
```

**Remarks**  
If no template name is specified, current runtime settings will be used. To get the actual text results, please refer to [`GetAllTextResults`](result.md#getalltextresults).







## DecodeFileInMemory

Decode barcodes from an image file in memory.   

```cpp
int dynamsoft::dbr::CBarcodeReader::DecodeFileInMemory (const unsigned char* pFileBytes, int fileSize, const char* pTemplateName = "")	
```   
   
**Parameters**  
`[in]	pFileBytes` The image file bytes in memory.   
`[in]	fileSize` The length of the file bytes in memory.   
`[in] pTemplateName`<sub>Optional</sub> The template name.

**Return Value**  
Returns error code (returns 0 if the function operates successfully).    
*You can call [GetErrorString()](general.md#geterrorstring) to get detailed error message.*   

**Code Snippet**  
```cpp
char errorBuf[512];
dynamsoft::dbr::CBarcodeReader::InitLicense("YOUR-LICENSE-KEY", errorBuf, 512);
CBarcodeReader* reader = new CBarcodeReader();
unsigned char* pFileBytes;
int nFileSize = 0;
GetFileStream("C:\\Program Files (x86)\\Dynamsoft\\{Version number}\\Images\\AllSupportedBarcodeTypes.tif", &pFileBytes, &nFileSize);
int errorCode = reader->DecodeFileInMemory(pFileBytes, nFileSize, "");
delete reader;
```

**Remarks**  
If no template name is specified, current runtime settings will be used. To get the actual text results, please refer to [`GetAllTextResults`](result.md#getalltextresults).







## DecodeBuffer

Decode barcodes from the memory buffer containing image pixels in defined format.

```cpp
int dynamsoft::dbr::CBarcodeReader::DecodeBuffer (const unsigned char* pBufferBytes, const int iWidth, const int iHeight, const int iStride, const ImagePixelFormat format, const char* pszTemplateName = "")

int dynamsoft::dbr::CBarcodeReader::DecodeBuffer (const unsigned char* pBufferBytes, const int iWidth, const int iHeight, const int iStride, const ImagePixelFormat format, const int orientation, const char* pszTemplateName = "")

```

**Parameters**  
`[in] pBufferBytes` The array of bytes which contain the image data.  
`[in] iWidth` The width of the image in pixels.  
`[in] iHeight` The height of the image in pixels.  
`[in] iStride` The stride (or scan width) of the image.  
`[in] format` The image pixel format used in the image byte array.  
`[in] orientation` The orientation of the image data. The value is the angle that the image needs to be rotated clockwise so it shows correctly on the display in its natural orientation. It can be 0, 90, 180, or 270.  
`[in] pTemplateName`<sub>Optional</sub> The template name.

**Return Value**  
Returns error code (returns 0 if the function operates successfully).  
*You can call [`GetErrorString`](general.md#geterrorstring) to get detailed error message.*

**Code Snippet**  
```cpp
char errorBuf[512];
dynamsoft::dbr::CBarcodeReader::InitLicense("YOUR-LICENSE-KEY", errorBuf, 512);
CBarcodeReader* reader = new CBarcodeReader();
unsigned char* pBufferBytes;
int iWidth = 0;
int iHeight = 0;
int iStride = 0;
ImagePixelFormat format;
int iOrientation = 0;
//get image data (pBufferBytes, iWidth, iHeight, iStride, format, iOrientation) somewhere else
int errorCode = reader->DecodeBuffer(pBufferBytes, iWidth, iHeight, iStride, format, "");
//int errorCode = reader->DecodeBuffer(pBufferBytes, iWidth, iHeight, iStride, format, iOrientation, "");
delete reader;
```

**Remarks**  
If no template name is specified, current runtime settings will be used. To get the actual text results, please refer to [`GetAllTextResults`](result.md#getalltextresults).







## DecodeBase64String

Decode barcode from an image file encoded as a base64 string.

```cpp
int dynamsoft::dbr::CBarcodeReader::DecodeBase64String (const char* pBase64String, const char* pTemplateName = "")	
```   
   
**Parameters**  
`[in]	pBase64String`	A base64 encoded string that represents an image.   
`[in] pTemplateName`<sub>Optional</sub> The template name.

**Return Value**  
Returns error code (returns 0 if the function operates successfully).    
*You can call [`GetErrorString`](general.md#geterrorstring) to get detailed error message.*


**Code Snippet**  
```cpp
char errorBuf[512];
dynamsoft::dbr::CBarcodeReader::InitLicense("YOUR-LICENSE-KEY", errorBuf, 512);
CBarcodeReader* reader = new CBarcodeReader();
unsigned char* pFileBytes;
int nFileSize = 0;
GetFileStream("C:\\Program Files (x86)\\Dynamsoft\\{Version number}\\Images\\AllSupportedBarcodeTypes.tif", &pFileBytes, &nFileSize);
char* strBase64String;
GetFileBase64String(pBufferBytes, &strBase64String);
int errorCode = reader->DecodeBase64String(strBase64String, "");
delete reader;
```

**Remarks**  
If no template name is specified, current runtime settings will be used. To get the actual text results, please refer to [`GetAllTextResults`](result.md#getalltextresults).






## DecodeDIB

Decode barcode from a handle of device-independent bitmap (DIB).

```cpp
int dynamsoft::dbr::CBarcodeReader::DecodeDIB (const HANDLE hDIB, const char* pszTemplateName = "")	
```   
   
**Parameters**  
`[in]	hDIB` Handle of the device-independent bitmap.    
`[in] pTemplateName`<sub>Optional</sub> The template name.

**Return Value**  
Returns error code (returns 0 if the function operates successfully).    
*You can call [`GetErrorString`](general.md#geterrorstring) to get detailed error message.*   


**Code Snippet**  
```cpp
char errorBuf[512];
dynamsoft::dbr::CBarcodeReader::InitLicense("YOUR-LICENSE-KEY", errorBuf, 512);
CBarcodeReader* reader = new CBarcodeReader();
HANDLE pDIB;
GetDIBFromImage("C:\\Program Files (x86)\\Dynamsoft\\{Version number}\\Images\\AllSupportedBarcodeTypes.tif", &pDIB);
int errorCode = reader->DecodeDIB(pDIB, "");
delete reader;
```

**Remarks**  
If no template name is specified, current runtime settings will be used. To get the actual text results, please refer to [`GetAllTextResults`](result.md#getalltextresults).





## InitIntermediateResult
Inits an intermediateResult struct with default values.

```cpp
int dynamsoft::dbr::CBarcodeReader::InitIntermediateResult(IntermediateResultType intermediateResultType, IntermediateResult* pIntermediateResult)	
```   
   
**Parameters**  
`[in]	intermediateResultType` The type of the intermediate result to init. Please see [`EnumIntermediateResultType`]({{site.dbr_c_cpp_enumerations}}result-enums.html?scr=cpp#intermediateresulttype).  
`[in, out]	pIntermediateResult` The resulting [`IntermediateResult`]({{site.dbr_structs}}IntermediateResult.html?src=cpp) struct.  

**Return Value**  
Returns error code (returns 0 if the function operates successfully).    
*You can call [`DBR_GetErrorString`](general.md#dbr_geterrorstring) to get detailed error message.*

**Code Snippet**  
```cpp
IntermediateResult imResult;
dynamsoft::dbr::CBarcodeReader::InitIntermediateResult(IRT_ORIGINAL_IMAGE, &imResult);
```






## DecodeIntermediateResults
Decodes barcode from intermediate results.

```cpp
int dynamsoft::dbr::CBarcodeReader::DecodeIntermediateResults(const IntermediateResultArray *pIntermediateResultArray, const char* pTemplateName = "")	
```   
   
**Parameters**  
`[in]	pIntermediateResultArray` The [`IntermediateResult`]({{site.dbr_structs}}IntermediateResult.html?src=cpp) array for decoding.
`[in]	pTemplateName`<sub>Optional</sub> The template name.

**Return Value**  
Returns error code (returns 0 if the function operates successfully).    
*You can call [`DBR_GetErrorString`](general.md#dbr_geterrorstring) to get detailed error message.*

**Code Snippet**  
```cpp
char errorBuf[512];
dynamsoft::dbr::CBarcodeReader::InitLicense("YOUR-LICENSE-KEY", errorBuf, 512);
CBarcodeReader * reader = new CBarcodeReader();
char fileName[] = "Your barcode file";

PublicRuntimeSettings settings;
reader->GetRuntimeSettings(&settings);
settings.intermediateResultTypes = IRT_ORIGINAL_IMAGE;
reader->UpdateRuntimeSettings(&settings);
reader->DecodeFile(fileName, "");
IntermediateResultArray * imResults = NULL;
reader->GetIntermediateResults(&imResults);
reader->DecodeIntermediateResults(imResults, "");
TextArray * results = NULL;
reader->GetAllTextResults(&results);
```

**Remarks**
If no template name is specified, current runtime settings will be used. To get the actual text results, please refer to [`GetAllTextResults`](result.md#getalltextresults).

