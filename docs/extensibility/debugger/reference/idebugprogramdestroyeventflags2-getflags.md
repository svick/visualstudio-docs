---
title: "IDebugProgramDestroyEventFlags2::GetFlags | Microsoft Docs"
ms.date: "11/04/2016"
ms.topic: "conceptual"
helpviewer_keywords: 
  - "GetFlags"
  - "IDebugProgramDestroyEventFlags2::GetFlags"
ms.assetid: dd53bd0c-459a-4077-ba81-780defb71e87
author: "gregvanl"
ms.author: "gregvanl"
manager: jillfra
ms.workload: 
  - "vssdk"
---
# IDebugProgramDestroyEventFlags2::GetFlags
Retrieves the program destroy flags.  
  
## Syntax  
  
```cpp  
HRESULT GetFlags(  
   PROGRAM_DESTROY_FLAGS* pdwFlags  
);  
```  
  
```csharp  
public int GetFlags(  
   out enum_PROGRAM_DESTROY_FLAGS pdwFlags  
);  
```  
  
#### Parameters  
 `pdwFlags`  
 [out] Represents the program destroy flags.  
  
## Return Value  
 If successful, returns `S_OK`; otherwise, returns an error code.  
  
## See Also  
 [IDebugProgramDestroyEventFlags2](../../../extensibility/debugger/reference/idebugprogramdestroyeventflags2.md)   
 [PROGRAM_DESTROY_FLAGS](../../../extensibility/debugger/reference/program-destroy-flags.md)