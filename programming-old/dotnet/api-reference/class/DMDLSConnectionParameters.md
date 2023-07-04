---
layout: default-layout
title: DMDLSConnectionParameters Class - Dynamsoft Barcode Reader SDK .NET Edition API Reference
description: This page shows the DMDLSConnectionParameters Class of Dynamsoft Barcode Reader SDK .NET Edition.
keywords: DMDLSConnectionParameters, class, api reference, .Net
needAutoGenerateSidebar: false
pageStartVer: 8.6
permalink: /programming/dotnet/api-reference/class/DMDLSConnectionParameters.html
---


# DMDLSConnectionParameters
Defines a struct to configure the parameters to connect to license server.  

```csharp
public class DMDLSConnectionParameters
```  


## Attributes
    
| Attribute | Type |
|---------- | ---- |
| [`MainServerURL`](#mainserverurl) | *string* |
| [`StandbyServerURL`](#standbyserverurl) | *string* |
| [`HandshakeCode`](#handshakecode) | *string* |
| [`SessionPassword`](#sessionpassword) | *string* |
| [`DeploymentType`](#deploymenttype) | *EnumDMDeploymentType* |
| [`ChargeWay`](#chargeway) | *EnumDMChargeWay* |
| [`UUIDGenerationMethod`](#uuidgenerationmethod) | *EnumDMUUIDGenerationMethod* |
| [`MaxBufferDays`](#maxbufferdays) | *int* |
| [`LimitedLicenseModules`](#limitedlicensemodules) | *EnumDMLicenseModule[]* |
| [`MaxConcurrentInstanceCount`](#maxconcurrentinstancecount) | *int* |
| [`OrganizationID`](#organizationid) | *string* |
| [`Products`](#products) | *int* |


### MainServerURL

The URL of the license server.

```csharp
string Dynamsoft.DMDLSConnectionParameters.MainServerURL
```

**Value Range**     
    Any string value   
      
**Default Value**     
    null
    
**Remarks**      
    If you choose "Dynamsoft-hosting", then no need to change the value of MainServerURL and StandbyServerURL. When both are set to null (default value), it will connect to Dynamsoft's license servers for online verification.


### StandbyServerURL

The URL of the standby license server.

```csharp
string Dynamsoft.DMDLSConnectionParameters.StandbyServerURL
```

**Value Range**     
    Any string value   
      
**Default Value**     
    null
    
**Remarks**      
    If you choose "Dynamsoft-hosting", then no need to change the value of MainServerURL and StandbyServerURL. When both are set to null (default value), it will connect to Dynamsoft's license servers for online verification.


### HandshakeCode

The handshake code.

```csharp
string Dynamsoft.DMDLSConnectionParameters.HandshakeCode
```

**Value Range**     
    Any string value   
      
**Default Value**     
    null

### SessionPassword

The session password of the handshake code set in license server.

```csharp
string Dynamsoft.DMDLSConnectionParameters.SessionPassword
```

**Value Range**     
    Any string value   
      
**Default Value**     
    null


### DeploymentType

Sets the deployment type.

```csharp
EnumDMDeploymentType Dynamsoft.DMDLSConnectionParameters.DeploymentType
```

**Value Range**     
    Any one of the [`EnumDMDeploymentType`]({{ site.dotnet_enumerations }}other-enums.html#dm_deploymenttype) Enumeration items.   
      
**Default Value**     
    DM_DT_DESKTOP   
    
**See Also**      
    [`EnumDMDeploymentType`]({{ site.dotnet_enumerations }}other-enums.html#dm_deploymenttype)    

### ChargeWay

Sets the charge way.

```csharp
EnumDMChargeWay Dynamsoft.DMDLSConnectionParameters.ChargeWay
```

**Value Range**     
    Any one of the [`EnumDMChargeWay`]({{ site.dotnet_enumerations }}other-enums.html#dm_chargeWay) Enumeration items.   
      
**Default Value**     
    DM_CW_AUTO   
    
**See Also**      
    [`EnumDMChargeWay`]({{ site.dotnet_enumerations }}other-enums.html#dm_chargeWay)    


### UUIDGenerationMethod

Sets the method to generate UUID.

```csharp
EnumDMUUIDGenerationMethod Dynamsoft.DMDLSConnectionParameters.UUIDGenerationMethod
```

**Value Range**     
    Any one of the [`EnumDMUUIDGenerationMethod`]({{ site.dotnet_enumerations }}other-enums.html#dm_uuidgenerationmethod) Enumeration items.   
      
**Default Value**     
    DM_UUIDGM_RANDOM   
    
**See Also**      
    [`EnumDMUUIDGenerationMethod`]({{ site.dotnet_enumerations }}other-enums.html#dm_uuidgenerationmethod)    

### MaxBufferDays

Sets the max days to buffer the license info.

```csharp
int Dynamsoft.DMDLSConnectionParameters.MaxBufferDays
```

**Value Range**     
    [7,0x7fffffff]  
      
**Default Value**     
    7  
    

### LimitedLicenseModules

Sets the license modules to use.

```csharp
EnumDMLicenseModule[] Dynamsoft.DMDLSConnectionParameters.LimitedLicenseModules
```

**Value Range**     
    Each array item can be any one of the [`EnumDMLicenseModule`]({{ site.dotnet_enumerations }}other-enums.html#dm_licensemodule) Enumeration items.   
      
**Default Value**     
    null   
    
**See Also**      
    [`EnumDMLicenseModule`]({{ site.dotnet_enumerations }}other-enums.html#dm_licensemodule)    


### MaxConcurrentInstanceCount
Sets the max concurrent instance count.
```csharp
int Dynamsoft.DMDLSConnectionParameters.MaxConcurrentInstanceCount
```
**Value Range**     
    [1,0x7fffffff]   
      
**Default Value**     
    1
**Remarks**       
    It works only when [ChargeWay](#chargeway) is setting to DM_CW_CONCURRENT_INSTANCE_COUNT
    It is the total number of instances used by multiple processes. For example, if there are two .EXE are running on the server and each .EXE may have 10 instances at most, then you should set maxConcurrentInstanceCount to 20.


### OrganizationID
The organization ID got from Dynamsoft.

```csharp
string Dynamsoft.DMDLSConnectionParameters.OrganizationID
```

**Value Range**     
    Any string value   
      
**Default Value**     
    null


### Products
Sets the products to get the license for. Product values can be combined.
```csharp
int Dynamsoft.DMDLSConnectionParameters.Products
```
**Value Range**     
    A combined value of [`Product`]({{ site.dotnet_enumerations }}other-enums.html#product) Enumeration items
      
**Default Value**     
    `PROD_ALL`
