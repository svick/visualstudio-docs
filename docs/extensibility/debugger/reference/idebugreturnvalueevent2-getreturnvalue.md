---
title: "IDebugReturnValueEvent2::GetReturnValue | Microsoft Docs"
ms.date: "11/04/2016"
ms.topic: "conceptual"
f1_keywords: 
  - "IDebugReturnValueEvent2::GetReturnValue"
helpviewer_keywords: 
  - "IDebugReturnValueEvent2::GetReturnValue"
ms.assetid: 86c50d5a-6df6-4798-818a-c587a8741f90
author: "gregvanl"
ms.author: "gregvanl"
manager: jillfra
ms.workload: 
  - "vssdk"
---
# IDebugReturnValueEvent2::GetReturnValue
Gets the value returned on stepping out of or over a function.  
  
## Syntax  
  
```cpp  
HRESULT GetReturnValue (   
   IDebugProperty2** ppReturnValue  
);  
```  
  
```csharp  
int GetReturnValue (   
   out IDebugProperty2 ppReturnValue  
);  
```  
  
#### Parameters  
 `ppReturnValue`  
 [out] Returns an [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) object that represents the value to be retrieved.  
  
## Return Value  
 If successful, returns `S_OK`; otherwise, returns an error code.  
  
## See Also  
 [IDebugReturnValueEvent2](../../../extensibility/debugger/reference/idebugreturnvalueevent2.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)