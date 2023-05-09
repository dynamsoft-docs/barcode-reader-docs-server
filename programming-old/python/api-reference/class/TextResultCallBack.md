---
layout: default-layout
title: TextResultCallBack Class - Dynamsoft Barcode Reader SDK Python Edition API Reference
description: This page shows the TextResultCallBack Class of Dynamsoft Barcode Reader SDK Python Edition.
keywords: TextResultCallBack, class, api reference, python
needAutoGenerateSidebar: false
permalink: /programming/python/api-reference/class/TextResultCallBack.html
---


# TextResultCallBack
An abstract class that contains an abstract method `text_results_callback_func`.

```python
class TextResultCallBack(ABC)
```  
  
  

## Abstract Method
  
### text_results_callback_func
Sets callback function to process text results which is triggered when the library finishes decoding a frame. You need to implement it in the subclass.

**Parameters**  
`[in] frame_id <int>` : The ID of the frame.  
`[in] results <list[dict]>` : Recognized barcode results of the frame. You can convert every item of the results to TextResult Object by using TextResult's constructor.  
`[in] user_data <object>` : Customized arguments passed to your function.  
        

```python
TextResultCallBack.text_results_callback_func(frame_id, results, user_data)
```
