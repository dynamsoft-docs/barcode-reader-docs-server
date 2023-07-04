---
layout: default-layout
title: IntermediateResultCallBack Class - Dynamsoft Barcode Reader SDK Python Edition API Reference
description: This page shows the IntermediateResultCallBack Class of Dynamsoft Barcode Reader SDK Python Edition.
keywords: IntermediateResultCallBack, class, api reference, python
needAutoGenerateSidebar: false
permalink: /programming/python/api-reference/class/IntermediateResultCallBack.html
---


# IntermediateResultCallBack
An abstract class that contains an abstract method `intermediate_results_callback_func`.

```python
class IntermediateResultCallBack(ABC)
```  
    

## Abstract Method
  
### intermediate_results_callback_func

Sets callback function to process intermediate results which is triggered when the library finishes decoding a frame. You need to implement it in the subclass. 

**Parameters**  
`[in] frame_id <int>` : The ID of the frame.
  
`[in] results <list[dict]>` : The intermediate results of the frame. You can convert every item of the results to `IntermediateResult` Object by using IntermediateResult's constructor.  
  
`[in] user_data <object>` : Customized arguments passed to your function.  
        

```python
IntermediateResultCallBack.intermediate_results_callback_func(frame_id, results, user_data)
```
