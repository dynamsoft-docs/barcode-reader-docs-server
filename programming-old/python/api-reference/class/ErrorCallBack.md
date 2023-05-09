---
layout: default-layout
title: ErrorCallBack Class - Dynamsoft Barcode Reader SDK Python Edition API Reference
description: This page shows the ErrorCallBack Class of Dynamsoft Barcode Reader SDK Python Edition.
keywords: ErrorCallBack, class, api reference, python
needAutoGenerateSidebar: false
permalink: /programming/python/api-reference/class/ErrorCallBack.html
---


# ErrorCallBack
An abstract class that contains an abstract method `error_callback_func`.

```python
class ErrorCallBack(ABC)
```  
 

## Abstract Method
  
### error_callback_func

Sets callback function to process errors which is triggered when the library finishes decoding a frame. You need to implement it in the subclass.

**Parameters**  
`[in] frame_id <int>` : The ID of the frame.  
`[in] error <int>` : Error code generated when decoding the frame.  
`[in] user_data <object>` : Customized arguments passed to your function.  
        

```python
ErrorCallBack.error_callback_func(frame_id, error, user_data)
```
