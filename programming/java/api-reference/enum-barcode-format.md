---
layout: default-layout
title: BarcodeFormat - Dynamsoft Barcode Reader Java Enumerations
description: The enumeration BarcodeFormat of Dynamsoft Barcode Reader defines the supported barcode formats.
keywords: Barcode formats
codeAutoHeight: true
---

# Enumeration BarcodeFormat

`BarcodeFormat` defines the supported barcode formats.

```java
@Retention(RetentionPolicy.CLASS)
public @interface EnumBarcodeFormat {
    //All supported formats in BarcodeFormat
    long BF_ALL = 0xFFFFFFFEFFFFFFFFL;
    //The default barcode format settings. It's a combined value of BF_ONED, BF_GS1_DATABAR, BF_PDF417, BF_QR_CODE, BF_DATAMATRIX, BF_AZTEC, BF_MAXICODE, BF_MICRO_QR, BF_MICRO_PDF417, BF_GS1_COMPOSITE
    long BF_DEFAULT = 0xFE3BFFFFL;
    //Combined value of BF_CODABAR, BF_CODE_128, BF_CODE_39, BF_CODE_39_EXTENDED, BF_CODE_93, BF_EAN_13, BF_EAN_8, INDUSTRIAL_25, BF_ITF, BF_UPC_A, BF_UPC_E, BF_MSI_CODE, BF_CODE_11;  
    long BF_ONED = 0x003007FFL;
    //Combined value of BF_GS1_DATABAR_OMNIDIRECTIONAL, BF_GS1_DATABAR_TRUNCATED, BF_GS1_DATABAR_STACKED, BF_GS1_DATABAR_STACKED_OMNIDIRECTIONAL,BF_GS1_DATABAR_EXPANDED, BF_GS1_DATABAR_EXPANDED_STACKED, BF_GS1_DATABAR_LIMITED
    long BF_GS1_DATABAR = 0x0003F800L;
    //Combined value of BF_USPSINTELLIGENTMAIL, BF_POSTNET, BF_PLANET, BF_AUSTRALIANPOST, BF_RM4SCC, BF_KIX.
    long BF_POSTALCODE = 0x3F0000000000000L;
    //Code 39 
    long BF_CODE_39 = 0x1L;
    //Code 128 
    long BF_CODE_128 = 0x2L;
    //Code 93 
    long BF_CODE_93 = 0x4L;
    //Codabar 
    long BF_CODABAR = 0x8L;
    //Interleaved 2 of 5 
    long BF_ITF = 0x10L;
    //EAN-13 
    long BF_EAN_13 = 0x20L;
    //EAN-8 
    long BF_EAN_8 = 0x40L;
    //UPC-A 
    long BF_UPC_A = 0x80L;
    //UPC-E 
    long BF_UPC_E = 0x100L;
    //Industrial 2 of 5 
    long BF_INDUSTRIAL_25 = 0x200L;
    //CODE39 Extended 
    long BF_CODE_39_EXTENDED = 0x400L;
    //GS1 Databar Omnidirectional
    long BF_GS1_DATABAR_OMNIDIRECTIONAL = 0x800L;
    //GS1 Databar Truncated
    long BF_GS1_DATABAR_TRUNCATED = 0x1000L;
    //GS1 Databar Stacked
    long BF_GS1_DATABAR_STACKED = 0x2000L;
    //GS1 Databar Stacked Omnidirectional
    long BF_GS1_DATABAR_STACKED_OMNIDIRECTIONAL = 0x4000L;
    //GS1 Databar Expanded
    long BF_GS1_DATABAR_EXPANDED = 0x8000L;
    //GS1 Databar Expaned Stacked
    long BF_GS1_DATABAR_EXPANDED_STACKED = 0x10000L;
    //GS1 Databar Limited
    long BF_GS1_DATABAR_LIMITED = 0x20000L;
    //Patch code
    long BF_PATCHCODE = 0x00040000L;
    //Code 32
    long BF_CODE_32 = 0x1000000L;
    //PDF417 
    long BF_PDF417 = 0x02000000L;
    //QRCode 
    long BF_QR_CODE = 0x04000000L;
    //DataMatrix 
    long BF_DATAMATRIX = 0x08000000L;
    //AZTEC 
    long BF_AZTEC = 0x10000000L;
    //MAXICODE 
    long BF_MAXICODE = 0x20000000L;
    //Micro QR Code
    long BF_MICRO_QR = 0x40000000L;
    //Micro PDF417
    long BF_MICRO_PDF417 = 0x00080000L;
    //GS1 Composite Code
    long BF_GS1_COMPOSITE = 0x80000000L;
    //MSI Code
    long BF_MSI_CODE = 0x100000L;
    //Code 11
    long BF_CODE_11 = 0x200000L;
    //Decode barcode with 2 digital addons
    long BF_TWO_DIGIT_ADD_ON = 0x400000L;
    //Decode barcode with 5 digital addons
    long BF_FIVE_DIGIT_ADD_ON = 0x800000L;
    //Matrix 25
    long BF_MATRIX_25 = 0x1000000000L;
    //Nonstandard barcode 
    long BF_NONSTANDARD_BARCODE = 0x100000000L;
    //USPS Intelligent Mail.
    long BF_USPSINTELLIGENTMAIL = 0x10000000000000L;
    //Postnet.
    long BF_POSTNET = 0x20000000000000L;
    //Planet.
    long BF_PLANET = 0x40000000000000L;
    //Australian Post.
    long BF_AUSTRALIANPOST = 0x80000000000000L;
    //Royal Mail 4-State Customer Barcode.
    long BF_RM4SCC = 0x100000000000000L;
    //KIX.
    long BF_KIX = 0x200000000000000L;
    //DotCode.
    long BF_DOTCODE = 0x200000000L;
    //_PHARMACODE_ONE_TRACK.
    long BF_PHARMACODE_ONE_TRACK = 0x400000000L;
    //PHARMACODE_TWO_TRACK.
    long BF_PHARMACODE_TWO_TRACK = 0x800000000L;
    //PHARMACODE.
    long BF_PHARMACODE = 0xC00000000L;
    //No barcode format in BarcodeFormat
    long BF_NULL = 0x00L;
}
```
