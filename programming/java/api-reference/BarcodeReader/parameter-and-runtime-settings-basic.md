---
layout: default-layout
title: Basic Settings Methods - Dynamsoft Barcode Reader SDK Java Edition API Reference
description: This page shows basic Runtime Settings methods of Dynamsoft Barcode Reader SDK Java Edition API Reference.
keywords: setModeArgument, getModeArgument, getRuntimeSettings, updateRuntimeSettings, resetRuntimeSettings, Basic Settings Methods, BarcodeReader, api reference, java
needAutoGenerateSidebar: true
permalink: /programming/java/api-reference/BarcodeReader/parameter-and-runtime-settings-basic.html
---


# Basic Settings Methods

  | Method               | Description |
  |----------------------|-------------|
  | [`setModeArgument`](#setmodeargument) | Set argument value for the specified mode parameter. |
  | [`getModeArgument`](#getmodeargument) | Get argument value for the specified mode parameter. |
  | [`getRuntimeSettings`](#getruntimesettings) | Get current runtime settings. |
  | [`updateRuntimeSettings`](#updateruntimesettings) | Modify and update the current runtime settings. |
  | [`resetRuntimeSettings`](#resetruntimesettings) | Reset runtime settings to default. |




  
## setModeArgument

Sets the optional argument for a specified mode in Modes parameters.


```java
void com.dynamsoft.dbr.BarcodeReader.setModeArgument(String modesName, int index, String argumentName, String argumentValue)	throws BarcodeReaderException
```   
**Parameters**  
`modesName` The mode parameter name to set argument.  
`index` The array index of mode parameter to indicate a specific mode.  
`argumentName` The name of the argument to set.  
`argumentValue` The value of the argument to set. 

**Exception**  
[`BarcodeReaderException`](../class/BarcodeReaderException.md)



**Code Snippet**  
```java
BarcodeReader.initLicense("YOUR-LICENSE-KEY");
BarcodeReader reader = BarcodeReader.getInstance();
if(reader != null)
{
    PublicRuntimeSettings settings = reader.getRuntimeSettings();
    settings.binarizationModes[0] = EnumBinarizationMode.BM_LOCAL_BLOCK;
    reader.updateRuntimeSettings(settings);
    reader.setModeArgument("BinarizationModes", 0, "EnableFillBinaryVacancy", "1");
    // add further process
    reader.recycle();
}
```

**Remarks**  
Check follow link for available modes and arguments:
- [`BarcodeColourModes`]({{ site.dbr_parameters_reference }}barcode-colour-modes.html#barcodecolourmodes)
- [`BinarizationModes`]({{ site.dbr_parameters_reference }}binarization-modes.html#binarizationmodes)
- [`ColourClusteringModes`]({{ site.dbr_parameters_reference }}colour-clustering-modes.html#colourclusteringmodes)
- [`ColourConversionModes`]({{ site.dbr_parameters_reference }}colour-conversion-modes.html#colourconversionmodes)
- [`DeformationResistingModes`]({{ site.dbr_parameters_reference }}deformation-resisting-modes.html#deformationresistingmodes)
- [`ImagePreprocessingModes`]({{ site.dbr_parameters_reference }}image-preprocessing-modes.html#imagepreprocessingmodes)
- [`IntermediateResultSavingMode`]({{ site.dbr_parameters_reference }}intermediate-result-saving-mode.html#intermediateresultsavingmode)
- [`LocalizationModes`]({{ site.dbr_parameters_reference }}localization-modes.html#localizationmodes)
- [`RegionPredetectionModes`]({{ site.dbr_parameters_reference }}region-predetection-modes.html#regionpredetectionmodes)
- [`ScaleUpModes`]({{ site.dbr_parameters_reference }}scale-up-modes.html#scaleupmodes)
- [`TextFilterModes`]({{ site.dbr_parameters_reference }}text-filter-modes.html#textfiltermodes)
- [`TextureDetectionModes`]({{ site.dbr_parameters_reference }}texture-detection-modes.html#texturedetectionmodes) 






## getModeArgument

Gets the optional argument for a specified mode in Modes parameters.

```java
String com.dynamsoft.dbr.BarcodeReader.getModeArgument(String modesName, int index, String argumentName) throws BarcodeReaderException
```   
   
**Parameters**    
`modesName` The mode parameter name to get argument.  
`index` The array index of mode parameter to indicate a specific mode.  
`argumentName` The name of the argument to get.

**Return Value**  
the optional argument for a specified mode in Modes parameters.

**Exception**  
[`BarcodeReaderException`](../class/BarcodeReaderException.md)


**Code Snippet**  
```java
BarcodeReader.initLicense("YOUR-LICENSE-KEY");
BarcodeReader reader = BarcodeReader.getInstance();
if(reader != null)
{
	PublicRuntimeSettings settings = reader.getRuntimeSettings();
	settings.binarizationModes[0] = EnumBinarizationMode.BM_LOCAL_BLOCK;
	reader.updateRuntimeSettings(settings);
	reader.setModeArgument("BinarizationModes", 0, "EnableFillBinaryVacancy", "1");
	String argumentValue = reader.getModeArgument("BinarizationModes", 0, "EnableFillBinaryVacancy");
    // add further process
    reader.recycle();
}
```

**Remarks**  
Check follow link for available modes and arguments:
- [`BarcodeColourModes`]({{ site.dbr_parameters_reference }}barcode-colour-modes.html#barcodecolourmodes)
- [`BinarizationModes`]({{ site.dbr_parameters_reference }}binarization-modes.html#binarizationmodes)
- [`ColourClusteringModes`]({{ site.dbr_parameters_reference }}colour-clustering-modes.html#colourclusteringmodes)
- [`ColourConversionModes`]({{ site.dbr_parameters_reference }}colour-conversion-modes.html#colourconversionmodes)
- [`DeformationResistingModes`]({{ site.dbr_parameters_reference }}deformation-resisting-modes.html#deformationresistingmodes)
- [`ImagePreprocessingModes`]({{ site.dbr_parameters_reference }}image-preprocessing-modes.html#imagepreprocessingmodes)
- [`IntermediateResultSavingMode`]({{ site.dbr_parameters_reference }}intermediate-result-saving-mode.html#intermediateresultsavingmode)
- [`LocalizationModes`]({{ site.dbr_parameters_reference }}localization-modes.html#localizationmodes)
- [`RegionPredetectionModes`]({{ site.dbr_parameters_reference }}region-predetection-modes.html#regionpredetectionmodes)
- [`ScaleUpModes`]({{ site.dbr_parameters_reference }}scale-up-modes.html#scaleupmodes)
- [`TextFilterModes`]({{ site.dbr_parameters_reference }}text-filter-modes.html#textfiltermodes)
- [`TextureDetectionModes`]({{ site.dbr_parameters_reference }}texture-detection-modes.html#texturedetectionmodes)    






## getRuntimeSettings

Get current settings and save them into a [`PublicRuntimeSettings`](../class/PublicRuntimeSettings.md) struct.

```java
PublicRuntimeSettings com.dynamsoft.dbr.BarcodeReader.getRuntimeSettings() throws BarcodeReaderException	
```   
 
**Return Value**  
A [`PublicRuntimeSettings`](../class/PublicRuntimeSettings.md) with current settings.

**Exception**  
[`BarcodeReaderException`](../class/BarcodeReaderException.md)

**Code Snippet**  
```java
BarcodeReader.initLicense("YOUR-LICENSE-KEY");
BarcodeReader reader = BarcodeReader.getInstance();
if(reader != null)
{
	PublicRuntimeSettings settings = reader.getRuntimeSettings();
    // add further process
    reader.recycle();
}
```







## updateRuntimeSettings

Update runtime settings with a given [`PublicRuntimeSettings`](../class/PublicRuntimeSettings.md) struct.

```java
void com.dynamsoft.dbr.BarcodeReader.updateRuntimeSettings(PublicRuntimeSettings settings) throws BarcodeReaderException
```   
   
**Parameters**  
`settings`	The struct of template settings.

**Exception**  
[`BarcodeReaderException`](../class/BarcodeReaderException.md)

**Code Snippet**  
```java
BarcodeReader.initLicense("YOUR-LICENSE-KEY");
BarcodeReader reader = BarcodeReader.getInstance();
if(reader != null)
{
	PublicRuntimeSettings settings = reader.getRuntimeSettings();
	settings.deblurLevel = 9;
	reader.updateRuntimeSettings(settings);
    // add further process
    reader.recycle();
}
```







## resetRuntimeSettings

Reset all parameters to default values.

```java
void com.dynamsoft.dbr.BarcodeReader.resetRuntimeSettings()	throws BarcodeReaderException

```   

**Exception**  
[`BarcodeReaderException`](../class/BarcodeReaderException.md)

**Code Snippet**  
```java
BarcodeReader.initLicense("YOUR-LICENSE-KEY");
BarcodeReader reader = BarcodeReader.getInstance();
if(reader != null)
{
	PublicRuntimeSettings settings = reader.getRuntimeSettings();
	settings.deblurLevel = 9;
	reader.updateRuntimeSettings(settings);
	reader.resetRuntimeSettings();
    // add further process
    reader.recycle();
}
```
