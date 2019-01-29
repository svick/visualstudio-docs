---
title: "IDebugMemoryBytes2::GetSize | Microsoft Docs"
ms.date: "11/04/2016"
ms.topic: "conceptual"
f1_keywords: 
  - "IDebugMemoryBytes2::GetSize"
helpviewer_keywords: 
  - "IDebugMemoryBytes2::GetSize method"
  - "GetSize method"
ms.assetid: dae64c5f-5b54-40c3-b32f-ec3b16c093f7
author: "gregvanl"
ms.author: "gregvanl"
manager: jillfra
ms.workload: 
  - "vssdk"
---
# IDebugMemoryBytes2::GetSize
Retrieves the size, in bytes, of the memory represented by this [IDebugMemoryBytes2](../../../extensibility/debugger/reference/idebugmemorybytes2.md) object.  
  
## Syntax  
  
```cpp  
HRESULT GetSize(   
   UINT64* pqwSize  
);  
```  
  
```csharp  
int GetSize(  
   out ulong pqwSize  
);  
```  
  
#### Parameters  
 `pqwSize`  
 [out] Returns the size, in bytes of the memory space.  
  
## Return Value  
 If successful, returns `S_OK`; otherwise, returns an error code.  
  
## See Also  
 [IDebugMemoryBytes2](../../../extensibility/debugger/reference/idebugmemorybytes2.md)