---
layout: default-layout
title: BarcodeReader License Methods - Dynamsoft Barcode Reader SDK Python Edition API Reference
description: This page shows BarcodeReader License Methods of Dynamsoft Barcode Reader SDK Python Edition.
keywords: init_license, init_license_from_server, init_license_from_license_content, output_license_to_string, license methods, BarcodeReader, api reference, python
needAutoGenerateSidebar: true
---


# Python API Reference - BarcodeReader License Methods

  | Method               | Description |
  |----------------------|-------------|
  | [`init_license`](#init_license) | Reads product key and activates the SDK.  |
  | [`is_instance_valid`](#is_instance_valid) | Gets whether the instance is valid when charging by concurrent instances count. |
  | [`get_idle_instances_count`](#get_idle_instances_count) | Gets available instances count when charging by concurrent instances count. |
  | [`set_device_friendly_name`](#set_device_friendly_name) | Sets a human-readable name that identifies the device. |
  | [`set_max_concurrent_instance_count`](#set_max_concurrent_instance_count) | Sets the max concurrent instance count used for current device and process. |
  | [`init_license_from_server`](#init_license_from_server) | `Deprecated` |
  | [`init_license_from_license_content`](#init_license_from_license_content) | `Deprecated` |
  | [`output_license_to_string`](#output_license_to_string) | `Deprecated` |
  | [`init_dls_connection_parameters`](#init_dls_connection_parameters) | `Deprecated` |
  | [`init_license_from_dls`](#init_license_from_dls) | `Deprecated` |
  | [`init_lts_connection_parameters`](#init_lts_connection_parameters) | `Deprecated` |
  | [`init_license_from_lts`](#init_license_from_lts) | `Deprecated` |
  

## init_license

Reads product key and activates the SDK.

```python
BarcodeReader.init_license(dbr_license)
```

**Parameters**  

`[in]	dbr_license` <*str*> : The license key.

**Return Value**  

`error` <*tuple*> : error_code = error[0], error_message = error[1], if error_code != EnumErrorCode.DBR_OK, you can get the detailed error message by error_message.

## is_instance_valid

Gets whether the instance is valid when charging by concurrent instances count.

```python
BarcodeReader.is_instance_valid()
```

**Return Value**

Returns an int value indicating whether the instance is valid for running on concurrent instance mode.

- 0: The instance is not valid for running on concurrent instance mode.
- 1: The instance is valid for running on concurrent instance mode.

**Remarks**

This method is meaningful only when using a license charged by concurrent instances count.

## get_idle_instances_count
Gets available instances count when charging by concurrent instances count.

```python
BarcodeReader.get_idle_instances_count()
```   

**Return Value**  
`count` <*int*> : Returns available instances count.    
- 0: There is no space for new instance  
- -1: The available count needs to be updated from server by calling initLicense.
- N ( N > 0 ): N more instances can be created.

## set_device_friendly_name

Sets a human-readable name that identifies the device.

```python
BarcodeReader.set_device_friendly_name(name)
```

**Parameters**  

`[in] name` <*str*> : The device alias.

**Return Value**  

`error` <*int*> :  EnumErrorCode.

## set_max_concurrent_instance_count

Sets the max concurrent instance count used for current device and process.

```python
BarcodeReader.set_max_concurrent_instance_count(count_for_this_device, count_for_this_process = 0)
```

**Parameters**

`[in] count_for_this_device` The maximum number of concurrent instances that the current device can run.

`[in] count_for_this_process` <sub>Optional</sub> The maximum number of concurrent instances that the current process can run.

**Code Snippet**

```python
license_key = 'YOUR-LICENSE-KEY'
BarcodeReader.set_max_concurrent_instance_count(1,1) # The count value should be set based on your purchased license count
BarcodeReader.init_license(license_key)
barcode_reader = BarcodeReader.get_instance()
# Add your code here to call decoding method, process barcode results and so on
# ...
# Recycle the barcode_reader instance to make it idle for other concurrent tasks
barcode_reader.recycle()
```

## init_license_from_server

`Deprecated`. It still works in this version but could be removed in the near future.

```python
BarcodeReader.init_license_from_server(license_server, license_key)
```

## init_license_from_license_content

`Deprecated`. It still works in this version but could be removed in the near future.

```python
BarcodeReader.init_license_from_license_content(license_key, license_content)
```

## output_license_to_string

`Deprecated`. It still works in this version but could be removed in the near future.

```python
BarcodeReader.output_license_to_string()
```

## init_dls_connection_parameters

`Deprecated`. It still works in this version but could be removed in the near future.

```python
BarcodeReader.init_dls_connection_parameters()
```

## init_license_from_dls

`Deprecated`. It still works in this version but could be removed in the near future.

```python
BarcodeReader.init_license_from_dls(dls_connection_parameters)
```

## init_lts_connection_parameters
`Deprecated`. It still works in this version but could be removed in the near future.

## init_license_from_lts
`Deprecated`. It still works in this version but could be removed in the near future.
