---
title: "IDebugPortNotify2::AddProgramNode | Microsoft Docs"
ms.date: "11/04/2016"
ms.topic: "conceptual"
f1_keywords: 
  - "IDebugPortNotify2::AddProgramNode"
helpviewer_keywords: 
  - "IDebugPortNotify2::AddProgramNode"
ms.assetid: 34c0e949-1eb9-4108-9cb8-a3eb87fcf190
author: "gregvanl"
ms.author: "gregvanl"
manager: jillfra
ms.workload: 
  - "vssdk"
---
# IDebugPortNotify2::AddProgramNode
Registers a program that can be debugged with the port it is running on.  
  
## Syntax  
  
```cpp  
HRESULT AddProgramNode(   
   IDebugProgramNode2* pProgramNode  
);  
```  
  
```csharp  
int AddProgramNode(   
   IDebugProgramNode2 pProgramNode  
);  
```  
  
#### Parameters  
 `pProgramNode`  
 [in] An [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) object that represents the program to be registered.  
  
## Return Value  
 If successful, returns `S_OK`; otherwise, returns an error code.  
  
## Remarks  
 A program node can be unregistered from the port by calling the [RemoveProgramNode](../../../extensibility/debugger/reference/idebugportnotify2-removeprogramnode.md) method.  
  
## See Also  
 [IDebugPortNotify2](../../../extensibility/debugger/reference/idebugportnotify2.md)   
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)   
 [RemoveProgramNode](../../../extensibility/debugger/reference/idebugportnotify2-removeprogramnode.md)