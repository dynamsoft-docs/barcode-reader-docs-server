---
layout: default-layout
title: DecodedBarcodeElement Class - Dynamsoft Barcode Reader Java Edition API Reference
description: This page shows DecodedBarcodeElement class definition of Dynamsoft Barcode Reader SDK Java Edition.
keywords: getFormat, getText, getBytes, getAngle, getConfidence, isDPM, DecodedBarcodeElement, api reference
---
# DecodedBarcodeElement Class

The `DecodedBarcodeElement` class represents a decoded barcode element. It inherits from the `RegionObjectElement` class and provides additional functionality for retrieving information about the decoded barcode.

## Definition

*Package:* com.dynamsoft.dbr.intermediate_results

*Inheritance:* [RegionObjectElement]({{ site.dcvb_java_api }}core/intermediate-results/region-object-element.html) -> DecodedBarcodeElement

```java
public class DecodedBarcodeElement extends RegionObjectElement
```

## Methods

| Method | Description |
| --- | --- |
| [`DecodedBarcodeElement`](#decodedbarcodeelement) | Initializes a new instance of the `DecodedBarcodeElement` class. |
| [`getFormat`](#getformat) | Gets the format of the barcode. |
| [`getFormatString`](#getformatstring) | Gets the string representation of the barcode format. |
| [`getText`](#gettext) | Gets the text of the decoded barcode. |
| [`getBytes`](#getbytes)| Gets the raw bytes of the decoded barcode.|
| [`getDetails`](#getdetails) | Gets the details of the decoded barcode.|
| [`isDPM`](#isdpm)| Determines whether the decoded barcode is a DPM (Direct Part Marking) code.|
| [`isMirrored`](#ismirrored)| Determines whether the decoded barcode is mirrored.|
| [`getAngle`](#getangle) | Gets the orientation angle of the barcode. |
| [`getModuleSize`](#getmodulesize) | Gets the module size of the barcode. |
| [`getConfidence`](#getconfidence) | Gets the confidence score of the barcode recognition result. |
| [`getExtendedBarcodeResultsCount`](#getextendedbarcoderesultscount) | Gets the number of extended barcode results for the decoded barcode.|
| [`getExtendedBarcodeResult`](#getextendedbarcoderesult) | Gets the extended barcode result at the specified index for the decoded barcode.|
| [`getExtendedBarcodeResults`](#getextendedbarcoderesults) | Gets all extended barcode results for the decoded barcode.|
| [`setFormat`](#setformat) | Sets the format of the barcode. |
| [`setText`](#settext) | Sets the text of the decoded barcode. |
| [`setBytes`](#setbytes)| Sets the raw bytes of the decoded barcode.|
| [`setConfidence`](#setconfidence) | Sets the confidence score of the barcode recognition result. |
| [`setLocation`](#setlocation) | Sets the location of the decoded barcode. |
| [`getECISegments`](#getecisegments) | Gets all the ECI segments in the barcode. |

### DecodedBarcodeElement

Initializes a new instance of the `DecodedBarcodeElement` class.

```java
public DecodedBarcodeElement()
```

### getFormat

Gets the format of the barcode.

```java
public @EnumBarcodeFormat long getFormat()
```

**Return value**

Returns the format of the barcode. This is one of the values of the `EnumBarcodeFormat` enumeration.

**See Also**

[EnumBarcodeFormat]({{ site.dbr_java_api }}enum-barcode-format.html)

### getFormatString

Gets the string representation of the barcode format.

```java
public String getFormatString()
```

**Return value**

Returns the string representation of the barcode format.

### getText

Gets the text of the decoded barcode.

```java
public String getText()
```

**Return value**

Returns a string representing the text of the decoded barcode.

### getBytes

Gets the raw bytes of the decoded barcode.

```java
public byte[] getBytes()
```

**Return value**

Returns the raw bytes of the decoded barcode.

### getDetails

Gets the details of the decoded barcode.

```java
public BarcodeDetails getDetails()
```

**Return value**

Returns the details of the decoded barcode.

**See Also**

- [AztecDetails]({{ site.dbr_java_api }}aztec-details.html)
- [BarcodeDetails]({{ site.dbr_java_api }}barcode-details.html)
- [DataMatrixDetails]({{ site.dbr_java_api }}datamatrix-details.html)
- [OneDCodeDetails]({{ site.dbr_java_api }}oned-code-details.html)
- [PDF417Details]({{ site.dbr_java_api }}pdf417-details.html)
- [QRCodeDetails]({{ site.dbr_java_api }}qr-code-details.html)

### isDPM

Determines whether the decoded barcode is a DPM (Direct Part Marking) code.

```java
public boolean isDPM()
```

**Return value**

Returns true if the decoded barcode is a DPM code, false otherwise.

### isMirrored

Determines whether the decoded barcode is mirrored.

```java
public boolean isMirrored()
```

**Return value**

Returns true if the decoded barcode is mirrored, false otherwise.

### getAngle

Gets the orientation angle of the barcode.

```java
public int getAngle()
```

**Return value**

Returns the orientation angle of the barcode.

### getModuleSize

Gets the module size of the barcode.

```java
public int getModuleSize()
```

**Return value**

Returns the module size of the barcode.

### getConfidence

Gets the confidence score of the barcode recognition result.

```java
public int getConfidence()
```

**Return value**

Returns the confidence score of the barcode recognition result.

### getExtendedBarcodeResultsCount

Gets the number of extended barcode results for the decoded barcode.

```java
public int getExtendedBarcodeResultsCount()
```

**Return value**

Returns the number of extended barcode results for the decoded barcode.

### getExtendedBarcodeResult

Gets the extended barcode result at the specified index for the decoded barcode.

```java
public ExtendedBarcodeResult getExtendedBarcodeResult(int index)
```

**Parameters**

`index` The index of the extended barcode result to retrieve.

**Return value**

Returns an `ExtendedBarcodeResult` object at the specified index for the decoded barcode.

**See Also**

[ExtendedBarcodeResult]({{ site.dbr_java_api }}extended-barcode-result.html)

### getExtendedBarcodeResults

Gets all extended barcode results for the decoded barcode.

```java
public ExtendedBarcodeResult[] getExtendedBarcodeResults()
```

**Return value**

Returns an array of `ExtendedBarcodeResult` objects for the decoded barcode.

**See Also**

[ExtendedBarcodeResult]({{ site.dbr_java_api }}extended-barcode-result.html)

### setFormat

Sets the format of the barcode.

```java
public void setFormat(@EnumBarcodeFormat long format)
```

**Parameters**

`format` The format of the barcode. This is one of the values of the `EnumBarcodeFormat` enumeration.

**See Also**

[EnumBarcodeFormat]({{ site.dbr_java_api }}enum-barcode-format.html)

### setText

Sets the text of the barcode.

```java
public void setText(String text)
```

**Parameters**

`text` The text of the barcode.

### setBytes

Sets the raw bytes of the barcode.

```java
public void setBytes(byte[] bytes)
```

**Parameters**

`bytes` The raw bytes of the barcode.

### setConfidence

Sets the confidence of the barcode.

```java
public void setConfidence(int confidence)
```

**Parameters**

`confidence` The confidence of the barcode.

### setLocation

Sets the location of the decoded barcode.

```java
public void setLocation(Quadrilateral location) throws BarcodeReaderException
```

**Parameters**

`location` The location of the decoded barcode.

**Exceptions**

`BarcodeReaderException` If an error occurs while setting the location.

**See Also**

[Quadrilateral]({{ site.dcvb_java_api }}core/basic-classes/quadrilateral.html)

[BarcodeReaderException]({{ site.dbr_java_api }}barcode-reader-exception.html)

### getECISegments

Gets all the ECI segments in the barcode.

```java
public ECISegment[] getECISegments()
```

**Return Value**

Returns an array of [`ECISegment`]({{ site.dbr_java_api }}eci-segment.html) objects. Returns an empty array if no ECI information is present.

**See Also**

[ECISegment]({{ site.dbr_java_api }}eci-segment.html)

**Remarks**

Introduced in Dynamsoft Barcode Reader SDK version 11.4.1000 and Dynamsoft Capture Vision version 3.4.1000.

