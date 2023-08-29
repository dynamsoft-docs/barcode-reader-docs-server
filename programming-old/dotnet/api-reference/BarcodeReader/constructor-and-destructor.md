---
layout: default-layout
title: BarcodeReader Constructor and Destructor - Dynamsoft Barcode Reader SDK .NET Edition API Reference
description: This page shows BarcodeReader Constructor and Destructor of Dynamsoft Barcode Reader SDK .NET Edition.
keywords: BarcodeReader, Dispose, api reference, .Net
needAutoGenerateSidebar: true
permalink: /programming/dotnet/api-reference/BarcodeReader/constructor-and-destructor.html
---

# Constructor and Destructor

  | Method               | Description |
  |----------------------|-------------|
  | [`BarcodeReader`](#barcodereader) | Default constructor of `BarcodeReader` object.|
  | [`Dispose`](#dispose) | Destroys an instance of Dynamsoft Barcode Reader. |
  | [`GetInstance`](#getinstance) | Creates an instance of Dynamsoft Barcode Reader. |
  | [`Recycle`](#recycle) | Destroys an instance of Dynamsoft Barcode Reader. |

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

Creates an instance of Dynamsoft Barcode Reader.

```csharp
static BarcodeReader Dynamsoft.DBR.BarcodeReader.GetInstance()
```

**Return Value**  
Returns an instance of Dynamsoft Barcode Reader. If failed, returns `null`.

**Code Snippet**  

```csharp
//Make sure InitLicense have been called somewhere before GetInstance
BarcodeReader reader = BarcodeReader.GetInstance();
// If no instance is available right away, the application will wait until one becomes available
if (reader != null)
{
    // Add your code here to call decoding method, process barcode results and so on
    // ...
    reader.Recycle();
}
```

## Recycle

Recycles an instance of Dynamsoft Barcode Reader.

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
    reader.Recycle();
}
```
