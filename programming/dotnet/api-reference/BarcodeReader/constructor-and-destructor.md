---
layout: default-layout
title: Dynamsoft Barcode Reader .NET API Reference - BarcodeReader Constructor and Destructor
description: This page shows BarcodeReader Constructor and Destructor of Dynamsoft Barcode Reader for .NET SDK.
keywords: BarcodeReader, Dispose, api reference, .Net
needAutoGenerateSidebar: true
---

# Constructor and Destructor

  | Method               | Description |
  |----------------------|-------------|
  | [`BarcodeReader`](#barcodereader) | Default constructor of `BarcodeReader` object.|
  | [`Dispose`](#dispose) | Destroys an instance of Dynamsoft Barcode Reader. |
  | [`GetInstance`](#getinstance) | Gets an idle Dynamsoft Barcode Reader instance running on concurrent instance mode. |
  | [`Recycle`](#recycle) | Recycles a Dynamsoft Barcode Reader instance running on concurrent instance mode. |

## BarcodeReader

### BarcodeReader()

Default constructor of a `BarcodeReader` object.

```csharp
Dynamsoft.DBR.BarcodeReader.BarcodeReader()
```

### BarcodeReader(string productKey)

`Deprecated`. It still works in this version but could be removed in the near future.

```csharp
Dynamsoft.DBR.BarcodeReader.BarcodeReader(string productKey)
```

### BarcodeReader(string modulePath, string productKey)

`Deprecated`. It still works in this version but could be removed in the near future.

```csharp
Dynamsoft.DBR.BarcodeReader.BarcodeReader(string modulePath, string productKey)
```


## Dispose

### Dispose()

Destroys an instance of Dynamsoft Barcode Reader.

```csharp
void Dynamsoft.DBR.BarcodeReader.Dispose() 
```

## GetInstance

Gets an idle Dynamsoft Barcode Reader instance running on concurrent instance mode.

```csharp
static BarcodeReader Dynamsoft.DBR.BarcodeReader.GetInstance()
```

**Return Value**  
Returns an idle Dynamsoft Barcode Reader instance running on concurrent instance mode. If failed, returns `NULL`.

**Code Snippet**  

```csharp
string errorMsg;
BarcodeReader.InitLicense("YOUR-LICENSE-KEY", out errorMsg);
BarcodeReader barcodeReader = BarcodeReader.GetInstance();
// Add your code here to call decoding method, process barcode results and so on
// ...
// Recycle the barcodeReader instance to make it idle for other concurrent tasks
barcodeReader.Recycle();
```

## Recycle

Recycles a Dynamsoft Barcode Reader instance running on concurrent instance mode.

```csharp
void Dynamsoft.DBR.BarcodeReader.Recycle()
```

**Code Snippet**  

```csharp
string errorMsg;
BarcodeReader.InitLicense("YOUR-LICENSE-KEY", out errorMsg);
BarcodeReader barcodeReader = BarcodeReader.GetInstance();
// Add your code here to call decoding method, process barcode results and so on
// ...
// Recycle the barcodeReader instance to make it idle for other concurrent tasks
barcodeReader.Recycle();
```
