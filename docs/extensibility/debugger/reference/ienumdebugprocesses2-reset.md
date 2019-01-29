---
title: "IEnumDebugProcesses2::Reset | Microsoft Docs"
ms.date: "11/04/2016"
ms.topic: "conceptual"
f1_keywords: 
  - "IEnumDebugProcesses2::Reset"
helpviewer_keywords: 
  - "IEnumDebugProcesses2::Reset"
ms.assetid: 31cbde4f-0bba-497a-9969-d2c342ef4a7b
author: "gregvanl"
ms.author: "gregvanl"
manager: jillfra
ms.workload: 
  - "vssdk"
---
# IEnumDebugProcesses2::Reset
Resets the enumeration to the first element.  
  
## Syntax  
  
```cpp  
HRESULT Reset(  
   void  
);  
```  
  
```csharp  
int Reset();  
```  
  
## Return Value  
 If successful, returns `S_OK`; otherwise, returns an error code.  
  
## Remarks  
 After this method is called, the next call to the [Next](../../../extensibility/debugger/reference/ienumdebugprocesses2-next.md) method returns the first element of the enumeration.  
  
## See Also  
 [IEnumDebugProcesses2](../../../extensibility/debugger/reference/ienumdebugprocesses2.md)