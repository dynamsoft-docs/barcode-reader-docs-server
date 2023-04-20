---
layout: default-layout
title: BarcodeReader Constructor and Destructor - Dynamsoft Barcode Reader SDK .NET Edition API Reference
description: This page shows BarcodeReader Constructor and Destructor of Dynamsoft Barcode Reader SDK .NET Edition.
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
Returns an idle Dynamsoft Barcode Reader instance running on concurrent instance mode. If failed, returns `null`.

**Code Snippet**  

```csharp
//Make sure InitLicense have been called somewhere before GetInstance
BarcodeReader reader = BarcodeReader.GetInstance();
// If no instance is available right away, the application will wait until one becomes available
if (reader != null)
{
    // Add your code here to call decoding method, process barcode results and so on
    // ...
    // Recycle the instance to make it idle for other concurrent tasks
    reader.Recycle();
}
```

## Recycle

Recycles a Dynamsoft Barcode Reader instance running on concurrent instance mode.

```csharp
void Dynamsoft.DBR.BarcodeReader.Recycle()
```

**Code Snippet**  

```csharp
//Make sure InitLicense have been called somewhere before GetInstance
BarcodeReader reader = BarcodeReader.GetInstance();
// If no instance is available right away, the application will wait until one becomes available
if (reader != null)
{
    // Add your code here to call decoding method, process barcode results and so on
    // ...
    // Recycle the instance to make it idle for other concurrent tasks
    reader.Recycle();
}
```
