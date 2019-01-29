---
title: "BeginCapture | Microsoft Docs"
ms.date: "11/04/2016"
ms.topic: "conceptual"
ms.assetid: 9edbb52d-ee0b-4cc4-a382-972bcee067d3
author: "mikejo5000"
ms.author: "mikejo"
manager: jillfra
ms.workload: 
  - "multiple"
---
# BeginCapture
Begins a capture interval that will end with `EndCapture`.  
  
## Syntax  
  
```C++  
void BeginCapture();  
```  
  
## Remarks  
 A capture interval typically spans a subset of one frame, such as when you want to capture graphics information only about a certain kind of draw call. If the capture interval spans a call to present, then two frames of graphics information are captured. The first frame spans the interval between the call to `BeginCapture` and the call to present; the second frame spans the interval between the first Direct3D event after the call to present and the call to `EndCapture`.  
  
 To capture an interval, you must prepare your app to capture and record graphics information—that is, you must have called [Init](init.md) through an instance of the `VsgDbg` class before you call `BeginCapture` or `EndCapture`.  
  
## See Also  
 [EndCapture](endcapture.md)   
 [CaptureCurrentFrame](capturecurrentframe.md)