---
layout: default-layout
title: Basic Settings Methods - Dynamsoft Barcode Reader SDK .NET Edition API Reference
description: This page shows basic Runtime Settings methods of Dynamsoft Barcode Reader SDK .NET Edition.
keywords: SetModeArgument, GetModeArgument, GetRuntimeSettings, UpdateRuntimeSettings, ResetRuntimeSettings, Basic Settings Methods, BarcodeReader, api reference, .Net
needAutoGenerateSidebar: true
permalink: /programming/dotnet/api-reference/BarcodeReader/parameter-and-runtime-settings-basic.html
---


# Basic Settings Methods

  | Method               | Description |
  |----------------------|-------------|
  | [`SetModeArgument`](#setmodeargument) | Sets the optional argument for a specified mode in Modes parameters. |
  | [`GetModeArgument`](#getmodeargument) | Gets the optional argument for a specified mode in Modes parameters.  |
  | [`GetRuntimeSettings`](#getruntimesettings) | Get current runtime settings. |
  | [`UpdateRuntimeSettings`](#updateruntimesettings) | Update runtime settings with a given struct. |
  | [`ResetRuntimeSettings`](#resetruntimesettings) | Resets all parameters to default values. |




## SetModeArgument

Sets the optional argument for a specified mode in Modes parameters. 


```csharp
EnumErrorCode Dynamsoft.DBR.BarcodeReader.SetModeArgument(string modesName, int index, string argumentName, string argumentValue, out string errorMessage)
```   
**Parameters**  
`[in]	modesName` <*string*> : The mode parameter name to set argument.  
`[in]	index` <*int*> : The array index of mode parameter to indicate a specific mode.  
`[in]	argumentName` <*string*> : The name of the argument to set.  
`[in]	argumentValue` <*string*> : The value of the argument to set.  
`[in,out]	errorMessage` <*string*> : The error message.

**Return Value**  
Returns error code.


**Code Snippet**  
```csharp
string errorMsg;
BarcodeReader.InitLicense("YOUR-LICENSE-KEY", out errorMsg);
BarcodeReader reader = BarcodeReader.GetInstance();
if (reader != null)
{
    PublicRuntimeSettings settings =  reader.GetRuntimeSettings();
    pSettings.BinarizationModes[0] = BM_LOCAL_BLOCK;
    string errorMessage;
    reader.UpdateRuntimeSettings(pSettings);
    EnumErrorCode error = reader.SetModeArgument("BinarizationModes", 0, "EnableFillBinaryVacancy", "1", out errorMessage);
	//... add further process
    reader.Recycle();
}
```

**Remarks**  
Check follow link for available modes and arguments:
- [`EnumBarcodeColourModes`]({{ site.dbr_parameters_reference }}barcode-colour-modes.html#barcodecolourmodes)
- [`EnumBinarizationModes`]({{ site.dbr_parameters_reference }}binarization-modes.html#binarizationmodes)
- [`EnumColourClusteringModes`]({{ site.dbr_parameters_reference }}colour-clustering-modes.html#colourclusteringmodes)
- [`EnumColourConversionModes`]({{ site.dbr_parameters_reference }}colour-conversion-modes.html#colourconversionmodes)
- [`EnumDeformationResistingModes`]({{ site.dbr_parameters_reference }}deformation-resisting-modes.html#deformationresistingmodes)
- [`EnumImagePreprocessingModes`]({{ site.dbr_parameters_reference }}image-preprocessing-modes.html#imagepreprocessingmodes)
- [`EnumIntermediateResultSavingMode`]({{ site.dbr_parameters_reference }}intermediate-result-saving-mode.html#intermediateresultsavingmode)
- [`EnumLocalizationModes`]({{ site.dbr_parameters_reference }}localization-modes.html#localizationmodes)
- [`EnumRegionPredetectionModes`]({{ site.dbr_parameters_reference }}region-predetection-modes.html#regionpredetectionmodes)
- [`EnumScaleUpModes`]({{ site.dbr_parameters_reference }}scale-up-modes.html#scaleupmodes)
- [`EnumTextFilterModes`]({{ site.dbr_parameters_reference }}text-filter-modes.html#textfiltermodes)
- [`EnumTextureDetectionModes`]({{ site.dbr_parameters_reference }}texture-detection-modes.html#texturedetectionmodes) 




## GetModeArgument

Get argument value for the specified mode parameter.

```csharp
EnumErrorCode Dynamsoft.DBR.BarcodeReader.GetModeArgument(string modesName, int index, string argumentName, out string argumentValue, out string errorMessage)
```   
   
**Parameters**    
`[in]	modesName` <*string*> : The mode parameter name to get argument.  
`[in]	index` <*int*> : The array index of mode parameter to indicate a specific mode.  
`[in]	argumentName` <*string*> : The name of the argument to get.  
`[in,out]	argumentValue` <*string*> : The value of the argument to get.  
`[in,out]	errorMessage` <*string*> : The error message.

**Return Value**  
Returns error code.



**Code Snippet**  
```csharp
string errorMsg;
BarcodeReader.InitLicense("YOUR-LICENSE-KEY", out errorMsg);
BarcodeReader reader = BarcodeReader.GetInstance();
if (reader != null)
{
	PublicRuntimeSettings settings =  reader.GetRuntimeSettings();
	pSettings.BinarizationModes[0] = BM_LOCAL_BLOCK;
	string errorMessage;
	reader.UpdateRuntimeSettings(pSettings);
	EnumErrorCode error = reader.SetModeArgument("BinarizationModes", 0, "EnableFillBinaryVacancy", "1", errorMessage);
	string angumentValue;
	EnumErrorCode error = reader.GetModeArgument("BinarizationModes", 0, "EnableFillBinaryVacancy", out angumentValue, out errorMessage);
	//... add further process
    reader.Recycle();
}
```

**Remarks**  
Check follow link for available modes and arguments:
- [`EnumBarcodeColourModes`]({{ site.dbr_parameters_reference }}barcode-colour-modes.html#barcodecolourmodes)
- [`EnumBinarizationModes`]({{ site.dbr_parameters_reference }}binarization-modes.html#binarizationmodes)
- [`EnumColourClusteringModes`]({{ site.dbr_parameters_reference }}colour-clustering-modes.html#colourclusteringmodes)
- [`EnumColourConversionModes`]({{ site.dbr_parameters_reference }}colour-conversion-modes.html#colourconversionmodes)
- [`EnumDeformationResistingModes`]({{ site.dbr_parameters_reference }}deformation-resisting-modes.html#deformationresistingmodes)
- [`EnumImagePreprocessingModes`]({{ site.dbr_parameters_reference }}image-preprocessing-modes.html#imagepreprocessingmodes)
- [`EnumIntermediateResultSavingMode`]({{ site.dbr_parameters_reference }}intermediate-result-saving-mode.html#intermediateresultsavingmode)
- [`EnumLocalizationModes`]({{ site.dbr_parameters_reference }}localization-modes.html#localizationmodes)
- [`EnumRegionPredetectionModes`]({{ site.dbr_parameters_reference }}region-predetection-modes.html#regionpredetectionmodes)
- [`EnumScaleUpModes`]({{ site.dbr_parameters_reference }}scale-up-modes.html#scaleupmodes)
- [`EnumTextFilterModes`]({{ site.dbr_parameters_reference }}text-filter-modes.html#textfiltermodes)
- [`EnumTextureDetectionModes`]({{ site.dbr_parameters_reference }}texture-detection-modes.html#texturedetectionmodes)  




## GetRuntimeSettings

Gets current settings and save it into a struct. 

```csharp
PublicRuntimeSettings Dynamsoft.DBR.BarcodeReader.GetRuntimeSettings()
```


**Return Value**  
The struct of template settings.


**Exception**  
[`BarcodeReaderException`](../class/BarcodeReaderException.md) The exception thrown by Dynamsoft Barcode Reader.  

**Code Snippet**  
```csharp
string errorMsg;
BarcodeReader.InitLicense("YOUR-LICENSE-KEY", out errorMsg);
BarcodeReader reader = BarcodeReader.GetInstance();
if (reader != null)
{
	PublicRuntimeSettings settings =  reader.GetRuntimeSettings();
	//... add further process
    reader.Recycle();
}
```

**See Also**  
[`PublicRuntimeSettings`](../struct/PublicRuntimeSettings.md)





## UpdateRuntimeSettings

Update runtime settings with a given struct. 

```csharp
void Dynamsoft.DBR.BarcodeReader.UpdateRuntimeSettings(PublicRuntimeSettings settings)
```   
   
**Parameters**  
`[in]	settings` <*[PublicRuntimeSettings](../struct/PublicRuntimeSettings.md)*> : The struct of template settings.    
 
**Exception**  
[`BarcodeReaderException`](../class/BarcodeReaderException.md) The exception thrown by Dynamsoft Barcode Reader.  

**Code Snippet**  
```csharp
string errorMsg;
BarcodeReader.InitLicense("YOUR-LICENSE-KEY", out errorMsg);
BarcodeReader reader = BarcodeReader.GetInstance();
if (reader != null)
{
	PublicRuntimeSettings settings =  reader.GetRuntimeSettings();
	settings.Timeout = 10000;
	settings.MaxAlgorithmThreadCount = 3;
	reader.UpdateRuntimeSettings(settings);
	//... add further process
    reader.Recycle();
}
```

**See Also**  
[`PublicRuntimeSettings`](../struct/PublicRuntimeSettings.md)





## ResetRuntimeSettings

Reset all parameters to default values.

```csharp
void Dynamsoft.DBR.BarcodeReader.ResetRuntimeSettings() 
```   

**Code Snippet**  
```csharp
string errorMsg;
BarcodeReader.InitLicense("YOUR-LICENSE-KEY", out errorMsg);
BarcodeReader reader = BarcodeReader.GetInstance();
if (reader != null)
{
	PublicRuntimeSettings settings =  reader.GetRuntimeSettings();
	settings.Timeout = 10000;
	settings.MaxAlgorithmThreadCount = 3;
	reader.UpdateRuntimeSettings(settings);
	reader.ResetRuntimeSettings();
	//... add further process
    reader.Recycle();
}

```
