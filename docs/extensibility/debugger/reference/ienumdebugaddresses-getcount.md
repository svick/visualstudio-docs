---
title: "IEnumDebugAddresses::GetCount | Microsoft Docs"
ms.date: "11/04/2016"
ms.topic: "conceptual"
f1_keywords: 
  - "IEnumDebugAddresses::GetCount"
helpviewer_keywords: 
  - "IEnumDebugAddresses::GetCount method"
ms.assetid: f2ca8ff8-539f-457c-83f8-9bbf97618065
author: "gregvanl"
ms.author: "gregvanl"
manager: jillfra
ms.workload: 
  - "vssdk"
---
# IEnumDebugAddresses::GetCount
This method returns the number of elements in the enumeration.  
  
## Syntax  
  
```cpp  
HRESULT GetCount(  
   [out] ULONG* pcelt  
);  
```  
  
```csharp  
int GetCount(  
   out uint pcelt  
);  
```  
  
#### Parameters  
 `pcelt`  
 [out] Returns the number of elements in the enumeration.  
  
## Return Value  
 If successful, returns `S_OK`; otherwise, returns an error code.  
  
## Remarks  
 This method is not part of the customary COM enumeration interface which specifies that only Next, Clone, Skip, and Reset need to be implemented.  
  
## See Also  
 [IEnumDebugAddresses](../../../extensibility/debugger/reference/ienumdebugaddresses.md)