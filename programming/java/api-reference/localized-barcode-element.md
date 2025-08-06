---
layout: default-layout
title: LocalizedBarcodeElement Class - Dynamsoft Barcode Reader Java Edition API Reference
description: This page shows LocalizedBarcodeElement class definition of Dynamsoft Barcode Reader SDK Java Edition.
keywords: getAngle, getConfidence, getPossibleFormats, getPossibleFormatsString, getModuleSize, setPossibleFormats, LocalizedBarcodeElement, api reference
---
# LocalizedBarcodeElement Class

The `LocalizedBarcodeElement` class represents a localized barcode element detected in an image. It is inherited from `RegionObjectElement` class.

## Definition

*Package:* com.dynamsoft.dbr.intermediate_results

*Inheritance:* [RegionObjectElement]({{ site.dcvb_java_api }}core/intermediate-results/region-object-element.html) -> LocalizedBarcodeElement

```java
public class LocalizedBarcodeElement extends RegionObjectElement
```

## Methods

| Method | Description |
|--------|-------------|
| [`LocalizedBarcodeElement`](#localizedbarcodeelement) | Initializes a new instance of the `LocalizedBarcodeElement` class. |
| [`getAngle`](#getangle) | Gets the orientation angle of the barcode. |
| [`getConfidence`](#getconfidence) | Gets the confidence score of the barcode localization result. |
| [`getPossibleFormats`](#getpossibleformats) | Gets the possible format of the barcode. |
| [`getPossibleFormatsString`](#getpossibleformatsstring) | Get all possible formats of the localized barcode in one string splited by ",". |
| [`getModuleSize`](#getmodulesize) | Gets the module size of the barcode. |
| [`setPossibleFormats`](#setpossibleformats) | Sets the posssible formats of the barcode. |
| [`setLocation`](#setlocation) | Sets the location of the localized barcode. |

### LocalizedBarcodeElement

Initializes a new instance of the `LocalizedBarcodeElement` class.

```java
public LocalizedBarcodeElement()
```

### getAngle

Gets the orientation angle of the barcode.

```java
public int getAngle()
```

**Return value**

Returns the orientation angle of the barcode.

### getConfidence

Gets the confidence score of the barcode localization result.

```java
public int getConfidence()
```

**Return value**

Returns the confidence score of the barcode recognition result. It represents the confidence that the positioning area is a barcode.

### getPossibleFormats

Gets the format of the barcode.

```java
public long getPossibleFormats()
```

**Return value**

Returns the format of the barcode.

**See Also**

[EnumBarcodeFormat]({{ site.dbr_java_api }}enum-barcode-format.html)

### getPossibleFormatsString

Gets all possible formats of the localized barcode in one string splited by ",".

```java
public String getPossibleFormatsString()
```

**Return value**

Returns the string representation of the barcode format in one string splited by ",".

### getModuleSize

Gets the module size of the barcode.

```java
public int getModuleSize()
```

**Return value**

Returns the module size of the barcode.

### setPossibleFormats

Sets the posssible formats of the barcode.

```java
public void setPossibleFormats(long possibleFormats)
```

**Parameters**

`possibleFormats` The posssible formats of the barcode.

**See Also**

[EnumBarcodeFormat]({{ site.dbr_java_api }}enum-barcode-format.html)

### setLocation

Sets the location of the localized barcode.

```java
public void setLocation(Quadrilateral location) throws BarcodeReaderException
```

**Parameters**

`location` The location of the localized barcode.

**Exceptions**

`BarcodeReaderException` If an error occurs while setting the location.

**See Also**

[Quadrilateral]({{ site.dcvb_java_api }}core/basic-classes/quadrilateral.html)

[BarcodeReaderException]({{ site.dbr_java_api }}barcode-reader-exception.html)