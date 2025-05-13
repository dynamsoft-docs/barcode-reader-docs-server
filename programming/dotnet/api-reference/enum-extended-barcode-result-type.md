---
layout: default-layout
title: ExtendedBarcodeResultType - Dynamsoft Barcode Reader .NET Enumerations
description: The enumeration ExtendedBarcodeResultType describes the type of the extended barcode result for .NET Edition.
keywords: Extended barcode result type
codeAutoHeight: true
---

# Enumeration ExtendedBarcodeResultType

`ExtendedBarcodeResultType` determines the type of text result returned from a barcode scan.

```csharp
public enum EnumExtendedBarcodeResultType
{
   /**Specifies the standard text. This means the barcode value. */
   EBRT_STANDARD_RESULT,
   /**Specifies all the candidate text. This means all the standard text results decoded from the barcode. */
   EBRT_CANDIDATE_RESULT,
   /**Specifies the partial text. This means part of the text result decoded from the barcode. */
   EBRT_PARTIAL_RESULT
}
```
