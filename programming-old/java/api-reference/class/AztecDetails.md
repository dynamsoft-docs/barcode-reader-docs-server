---
layout: default-layout
title: AztecDetails Class - Dynamsoft Barcode Reader SDK Java Edition API Reference
description: This page shows the AztecDetails Class of Dynamsoft Barcode Reader SDK Java Edition API Reference.
keywords: AztecDetails, class, api reference, java
needAutoGenerateSidebar: false
---


# AztecDetails
Stores the Aztec details.
  

## Attributes
  
| Attribute | Type |
|---------- | ----------- | 
| [`moduleSize`](#modulesize) | *int* |
| [`rows`](#rows) | *int* | 
| [`columns`](#columns) | *int* |
| [`layerNumber`](#layernumber) | *int* |
  
  
### moduleSize
The barcode module size (the minimum bar width in pixel).
```java
int com.dynamsoft.dbr.AztecDetails.moduleSize
```  
   
### rows
The row count of the barcode.
```java
int com.dynamsoft.dbr.AztecDetails.rows
```  

### columns
The column count of the barcode.
```java
int com.dynamsoft.dbr.AztecDetails.columns
```  

### layerNumber
A negative number (-1, -2, -3, -4) specifies a compact Aztec code. A positive number (1, 2, .. 32) specifies a normal (full-rang) Aztec code.  
```java
int com.dynamsoft.dbr.AztecDetails.layerNumber
```  
