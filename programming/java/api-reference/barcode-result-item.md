---
layout: default-layout
title: BarcodeResultItem Class - Dynamsoft Barcode Reader Java Edition API Reference
description: Definition of BarcodeResultItem class in Dynamsoft Barcode Reader Java Edition.
keywords: getFormat, getText, getLocation, getConfidence, getModuleSize, BarcodeResultItem, api reference
---

# BarcodeResultItem Class

The `BarcodeResultItem` class represents a barcode result item decoded by barcode reader engine. It is derived from `CapturedResultItem`.

## Definition

*Package:* com.dynamsoft.dbr

*Inheritance:* [CapturedResultItem]({{ site.dcvb_java_api }}core/basic-classes/captured-result-item.html) -> BarcodeResultItem

```java
public class BarcodeResultItem extends CapturedResultItem
```

## Methods

| Method               | Description |
|----------------------|-------------|
| [`getFormat`](#getformat) | Gets the format of the decoded barcode result. |
| [`getFormatString`](#getformatstring) | Gets the format string of the decoded barcode result. |
| [`getText`](#gettext) | Gets the text result of the decoded barcode. |
| [`getBytes`](#getbytes) | Gets the text bytes of the decoded barcode result. |
| [`getLocation`](#getlocation) | Gets the location of the decoded barcode in a quadrilateral. |
| [`getConfidence`](#getconfidence) | Gets the confidence of the decoded barcode result. |
| [`getAngle`](#getangle) | Gets the angle of the decoded barcode result. |
| [`getModuleSize`](#getmodulesize) | Gets the module size of the decoded barcode result. |
| [`getDetails`](#getdetails) | Gets the details of the decoded barcode result. |
| [`isDPM`](#isdpm) | Gets whether the decoded barcode is a DPM code. |
| [`isMirrored`](#ismirrored) | Gets whether the decoded barcode is a mirrored barcode. |
| [`setLocation`](#setlocation) | Sets the location of the decoded barcode. |
| [`setText`](#settext) | Sets the text of the decoded barcode. |
| [`setBytes`](#setbytes) | Sets the bytes of the decoded barcode. |

## Method Details

### getFormat

Gets the format of the decoded barcode result.

```java
public @EnumBarcodeFormat long getFormat()
```

**Return Value**

Returns the format of the decoded barcode result which is a value of the `EnumBarcodeFormat` enumeration.

**See Also**

[EnumBarcodeFormat]({{ site.dbr_java_api }}enum-barcode-format.html)

### getFormatString

Gets the format string of the decoded barcode result.

```java
public String getFormatString()
```

**Return Value**

Returns the format string of the decoded barcode result.

### getText

Gets the text result of the decoded barcode.

```java
public String getText()
```

**Return Value**

Returns the text result of the decoded barcode.

### getBytes

Gets the text bytes of the decoded barcode result.

```java
public byte[] getBytes()
```

**Return Value**

Returns the text bytes of the decoded barcode result.

### getLocation

Gets the location of the decoded barcode in a quadrilateral.

```java
public Quadrilateral getLocation()
```

**Return Value**

Returns the location of the decoded barcode in a quadrilateral.

**See Also**

[Quadrilateral]({{ site.dcvb_java_api }}core/basic-classes/quadrilateral.html)

### getConfidence

Gets the confidence of the decoded barcode result.

```java
public int getConfidence()
```

**Return Value**

Returns the confidence of the decoded barcode result.

### getAngle

Gets the angle of the decoded barcode result.

```java
public int getAngle()
```

**Return Value**

Returns the angle of the decoded barcode result.

**See Also**

[How the angle is calculated for different barcode types]({{site.features}}get-confidence-rotation.html?lang=java#barcode-rotation-angle)

### getModuleSize

Gets the module size of the decoded barcode result.

```java
public int getModuleSize()
```

**Return Value**

Returns the module size of the decoded barcode result.

### getDetails

Gets the details of the decoded barcode result.

```java
public BarcodeDetails getDetails()
```

**Return Value**

Returns the details of the decoded barcode result.

**See Also**

- [AztecDetails]({{ site.dbr_java_api }}aztec-details.html)
- [BarcodeDetails]({{ site.dbr_java_api }}barcode-details.html)
- [DataMatrixDetails]({{ site.dbr_java_api }}datamatrix-details.html)
- [OneDCodeDetails]({{ site.dbr_java_api }}oned-code-details.html)
- [PDF417Details]({{ site.dbr_java_api }}pdf417-details.html)
- [QRCodeDetails]({{ site.dbr_java_api }}qr-code-details.html)

### isDPM

Gets whether the decoded barcode is a DPM code.

```java
public boolean isDPM()
```

**Return Value**

Returns whether the decoded barcode is a DPM code.

### isMirrored

Gets whether the decoded barcode is mirrored.

```java
public boolean isMirrored()
```

**Return Value**

Returns whether the decoded barcode is mirrored.

### setLocation

Sets the location of the decoded barcode.

```java
public void setLocation(Quadrilateral location) throws BarcodeReaderException
```

**Parameters**

`location`: The location of the decoded barcode in a quadrilateral.

**Exceptions**

`BarcodeReaderException`: Thrown when an error occurs during the operation.

**See Also**

[BarcodeReaderException]({{ site.dbr_java_api }}barcode-reader-exception.html)

### setText

Sets the text of the decoded barcode.

```java
public void setText(String text)
```

**Parameters**

`text`: The text of the decoded barcode.

### setBytes

Sets the bytes of the decoded barcode.

```java
public void setBytes(byte[] bytes)
```

**Parameters**

`bytes`: The bytes of the decoded barcode.

