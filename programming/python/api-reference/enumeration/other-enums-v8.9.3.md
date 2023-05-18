---
layout: default-layout
title: Other Enumerations - Dynamsoft Barcode Reader SDK Python Edition
description: This article shows other Enumerations of Dynamsoft Barcode Reader v8.9.3 for Python Programming Laguage
keywords: DM_ChargeWay, DM_DeploymentType, DM_LicenseModule, DM_UUIDGenerationMethod, ImagePixelFormat, QRCodeErrorCorrectionLevel, other enumeration, enumeration
needGenerateH3Content: false
permalink: /programming/python/api-reference/enumeration/other-enums-v8.9.3.html
---


# Other Enumeration

  | Enumeration | Description |
  |-------------|-------------|
  | [`DM_ChargeWay`](#dm_chargeway) | Describes the charge way. |
  | [`DM_DeploymentType`](#dm_deploymenttype) | Describes the deployment type. |
  | [`DM_LicenseModule`](#dm_licensemodule) | Describes Dynamsoft license modules. |
  | [`DM_UUIDGenerationMethod`](#dm_uuidgenerationmethod) | Describes the UUID generation method. |
  | [`ImagePixelFormat`](#imagepixelformat) | Describes the image pixel format. |
  | [`QRCodeErrorCorrectionLevel`](#qrcodeerrorcorrectionlevel) | Describes the QR Code error correction level.   |
  | [`Product`](#product) | Describes Dynamsoft products.   |

## DM_ChargeWay
Describes charge way.


### Declarations
   



```python
class EnumDMChargeWay(IntEnum)
```




### Members
   
| Member | Value | Description |
| --------------------------  | ----- | ----------- |
| DM_CW_AUTO | 0 | The charge way automatically determined by the license server. |
| DM_CW_DEVICE_COUNT | 1 | Charges by the count of devices. |
| DM_CW_SCAN_COUNT | 2 | Charges by the count of barcode scans.|
| DM_CW_CONCURRENT_DEVICE_COUNT | 3 | Charges by the count of concurrent devices. |
| DM_CW_APP_DOMAIN_COUNT | 6 | Charges by the count of app domains. |
| DM_CW_ACTIVE_DEVICE_COUNT | 8 | Charges by the count of active devices. |
| DM_CW_INSTANCE_COUNT | 9 | Charges by the count of instances. |
| DM_CW_CONCURRENT_INSTANCE_COUNT | 10 | Charges by the count of concurrent instances. |






## DM_DeploymentType
Describes the deployment type.


### Declarations
   



```python
class EnumDMDeploymentType(IntEnum)
```





### Members
   
| Member | Value | Description |
| --------------------------  | ----- | ----------- |
| DM_DT_SERVER | 1 | Server deployment type |
| DM_DT_DESKTOP | 2 | Desktop |
| DM_DT_EMBEDDED_DEVICE | 6 | Embedded device deployment type |
| DM_DT_OEM | 7 | OEM deployment type |





## DM_LicenseModule
Describes Dynamsoft license modules.


### Declarations
   



```python
class EnumDMLicenseModule(IntEnum)
```




### Members
   
| Member | Value | Description |
| --------------------------  | ----- | ----------- |
| DM_LM_ONED | 1 | One-D barcodes license module |
| DM_LM_QR_CODE | 2 | QR Code barcodes license module |
| DM_LM_PDF417 | 3 | PDF417 barcodes license module |
| DM_LM_DATAMATRIX | 4 | DATAMATRIX barcodes license module |
| DM_LM_AZTEC | 5 | Aztec barcodes license module |
| DM_LM_MAXICODE | 6 | MAXICODE barcodes license module|
| DM_LM_PATCHCODE | 7 |Patch code barcodes license module |
| DM_LM_GS1_DATABAR | 8 | GS1 Databar barcodes license module |
| DM_LM_GS1_COMPOSITE | 9 | GS1 Composite Code barcodes license module |
| DM_LM_POSTALCODE | 10 | Postal code barcodes license module |
| DM_LM_DOTCODE | 11 | DotCode barcodes license module|
| DM_LM_DDM_LM_INTERMEDIATE_RESULTATAMATRIX | 12 | Intermediate result license module |
| DM_LM_DPM | 13 |DATAMATRIX DPM (Direct Part Marking) license module |
| DM_LM_NONSTANDARD_BARCODE | 16 | Nonstandard barcodes license module|




## DM_UUIDGenerationMethod
Describes UUID generation method.


### Declarations
   



```python
class EnumDMUUIDGenerationMethod(IntEnum)
```




### Members
   
| Member | Value | Description |
| --------------------------  | ----- | ----------- |
| DM_UUIDGM_RANDOM | 1 | Generates UUID with random values. |
| DM_UUIDGM_HARDWARE | 2 | Generates UUID based on hardware info. |







## ImagePixelFormat
Describes the image pixel format.


### Declarations
   



```python
class EnumImagePixelFormat(IntEnum)
```





### Members
   
| Member | Value | Description |
| --------------------------  | ----- | ----------- |
| IPF_BINARY  | 0 | 0: Black, 1: White |
| IPF_BINARYINVERTED  | 1 | 0: Black, 1: White |
| IPF_GRAYSCALED  | 2 | 8 bit gray |
| IPF_NV21 | 3 | NV21 |
| IPF_RGB_565 | 4 | 16bit with RGB channel order stored in memory from high to low address |
| IPF_RGB_555 | 5 | 16bit with RGB channel order stored in memory from high to low address |
| IPF_RGB_888 | 6 | 24bit with RGB channel order stored in memory from high to low address |
| IPF_ARGB_8888 | 7 | 32bit with ARGB channel order stored in memory from high to low address |
| IPF_RGB_161616 | 8 | 48bit with RGB channel order stored in memory from high to low address |
| IPF_ARGB_16161616 | 9 | 64bit with ARGB channel order stored in memory from high to low address |
| IPF_ABGR_8888 | 10 | 32bit with ABGR channel order stored in memory from high to low address |
| IPF_ABGR_16161616 | 11 | 64bit with ABGR channel order stored in memory from high to low address |
| IPF_BGR_888 | 12 | 24bit with BGR channel order stored in memory from high to low address |






## QRCodeErrorCorrectionLevel
Describes the QR Code error correction level.  


### Declarations
   


```python
class EnumQRCodeErrorCorrectionLevel(IntEnum)
```





### Members
   
| Member | Value | Description |
| --------------------------  | ----- | ----------- |
| QRECL_ERROR_CORRECTION_H  | 0 | Error Correction Level H (high) |
| QRECL_ERROR_CORRECTION_L  | 1 | Error Correction Level L (low) |
| QRECL_ERROR_CORRECTION_M  | 2 | Error Correction Level M (medium-low) |
| QRECL_ERROR_CORRECTION_Q  | 3 | Error Correction Level Q (medium-high) |



## Product
Describes Dynamsoft products.


### Declarations
   



```python
class EnumProduct(IntEnum)
```



### Members
   
| Member | Value | Description |
| --------------------------  | ----- | ----------- |
| PROD_DBR | 0x0001 | Dynamsoft Barcode Reader |
| PROD_DLR | 0x0002 | Dynamsoft Label Recognition |
| PROD_DWT | 0x0004 | Dynamic Web Twain |
| PROD_DCE | 0x0008 | Dynamsoft Camera Enhancer |
| PROD_DPS | 0x0010 | Dynamsoft Panorama |
| PROD_ALL | 0xFFFF | All Dynamsoft products |
