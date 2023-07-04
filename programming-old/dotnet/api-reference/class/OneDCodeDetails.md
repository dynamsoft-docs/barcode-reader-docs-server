---
layout: default-layout
title: OneDCodeDetails Class - Dynamsoft Barcode Reader SDK .NET Edition API Reference
description: This page shows the OneDCodeDetails Class of Dynamsoft Barcode Reader SDK .NET Edition.
keywords: OneDCodeDetails, class, api reference, .Net
needAutoGenerateSidebar: false
permalink: /programming/dotnet/api-reference/class/OneDCodeDetails.html
---

# OneDCodeDetails
Stores the OneD code details.

```csharp
public class OneDCodeDetails
```  

## Attributes
  
| Attribute | Type |
|---------- | ---- |
| [`ModuleSize`](#modulesize) | *int* |
| [`StartCharsBytes`](#startcharsbytes) | *byte[ ]* |
| [`StopCharsBytes`](#stopcharsbytes) | *byte[ ]* |
| [`CheckDigitBytes`](#checkdigitbytes) | *byte[ ]* |


### ModuleSize
The barcode module size (the minimum bar width in pixel).

```csharp
int Dynamsoft.OneDCodeDetails.ModuleSize
```

### StartCharsBytes
The start chars in a byte array.

```csharp
byte[] Dynamsoft.OneDCodeDetails.StartCharsBytes
```

### StopCharsBytes
The stop chars in a byte array.

```csharp
byte[] Dynamsoft.OneDCodeDetails.StopCharsBytes
```

### CheckDigitBytes
The check digit chars in a byte array.

```csharp
byte[] Dynamsoft.OneDCodeDetails.CheckDigitBytes
```
